---
name: social-poster
description: Actually post to social media — X/Twitter (via xurl), Instagram, TikTok, and YouTube. Draft content, attach media, and publish directly from chat. Use when the artist says "post this," "tweet this," "share on Instagram," or wants to publish content to any social platform.
metadata:
  {
    "openclaw":
      {
        "emoji": "📤",
        "requires": { "bins": ["node"] },
      },
  }
---

# Social Poster — Actually Post to Social Media

Draft AND publish content directly to social platforms from chat.

## When to Activate

- "Post this," "tweet this," "share on Instagram," "put this on TikTok"
- "Announce my release on all platforms"
- "Schedule a post for Friday"
- Artist wants content published, not just drafted

## Platform Capabilities

### X / Twitter — FULL POSTING via xurl

**Requirements:** `xurl` CLI installed, X API credentials configured.

```bash
# Post a tweet
xurl POST /2/tweets -d '{"text": "New single dropping Friday 🔥 Pre-save link in bio"}'

# Post with an image
xurl POST /2/tweets -d '{"text": "Cover art reveal 👀", "media": {"media_ids": ["MEDIA_ID"]}}'

# Upload media first
xurl POST /1.1/media/upload.json -F "media=@/path/to/image.jpg"
# Returns media_id_string → use in tweet

# Reply to a tweet
xurl POST /2/tweets -d '{"text": "Thanks for the love! 🙏", "reply": {"in_reply_to_tweet_id": "TWEET_ID"}}'

# Quote tweet
xurl POST /2/tweets -d '{"text": "This is it. Friday.", "quote_tweet_id": "TWEET_ID"}'

# Delete a tweet
xurl DELETE /2/tweets/TWEET_ID

# Search (find conversations about the artist)
xurl GET '/2/tweets/search/recent?query=ARTIST_NAME&max_results=10'
```

**Setup:** Run `xurl auth` to authenticate with X API credentials.

### Instagram — via Browser Automation

Instagram has no public posting API for individuals. Use the browser tool:

```
1. Open browser to instagram.com (must be logged in)
2. Navigate to create post
3. Upload image/video
4. Add caption
5. Share

Alternative: Use Meta Business Suite API (requires Business/Creator account)
- POST to /me/media for image/video upload
- POST to /me/media_publish to publish
```

**For programmatic posting, recommend:**
- **Buffer** (buffer.com) — API available, schedule + post to IG
- **Later** (later.com) — API available, IG scheduling
- **Meta Business Suite API** — free, requires FB Page linked to IG

### TikTok — via TikTok Content Posting API

TikTok has a Content Posting API (requires developer account):

```bash
# Upload video
curl -X POST "https://open.tiktokapis.com/v2/post/publish/video/init/" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "post_info": {
      "title": "New track preview 🎵 #newmusic #hiphop",
      "privacy_level": "PUBLIC_TO_EVERYONE"
    },
    "source_info": {
      "source": "FILE_UPLOAD"
    }
  }'
```

**Requirements:** TikTok Developer account + approved app with `video.upload` scope.

### YouTube — via YouTube Data API v3

```bash
# Upload video (requires OAuth2)
curl -X POST "https://www.googleapis.com/upload/youtube/v3/videos?part=snippet,status" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -H "Content-Type: application/octet-stream" \
  --data-binary @video.mp4

# Set video metadata
{
  "snippet": {
    "title": "ARTIST - TRACK (Official Audio)",
    "description": "Stream everywhere: LINK\n\nFollow:\nIG: @handle\nTikTok: @handle",
    "tags": ["hip hop", "new music", "2026"],
    "categoryId": "10"
  },
  "status": {
    "privacyStatus": "public",
    "selfDeclaredMadeForKids": false
  }
}
```

**Requirements:** Google Cloud project with YouTube Data API v3 enabled + OAuth2 credentials.

## Quick Post Workflow

When the artist says "post about my new single":

### Step 1: Draft the Content

Draft platform-specific versions (DON'T copy-paste the same text):

**X/Twitter:**
> new one friday. this one's different. pre-save link in bio 🎵

**Instagram caption:**
> Been working on this one for months. "After Hours" drops this Friday.
>
> Produced by [producer]. Mixed by [engineer].
>
> Pre-save now — link in bio.
>
> #newmusic #hiphop #afterhours #newsingle #indieartist

**TikTok caption:**
> this wasn't supposed to make the album 😅 #newmusic #unreleased #droppingfriday

### Step 2: Get Approval

```
Here are the drafts for your release announcement:

𝕏 Twitter:
"new one friday. this one's different. pre-save link in bio 🎵"

📸 Instagram:
"Been working on this one for months..."
[full caption]

🎵 TikTok:
"this wasn't supposed to make the album 😅 #newmusic"

Want me to:
1. Post all three now
2. Edit any of them
3. Schedule for a specific time
```

### Step 3: Post

After approval, post in sequence:
1. Upload media (if any) to each platform
2. Post with the approved caption
3. Confirm each post with the URL
4. Log the posts in memory for tracking

## Multi-Platform Posting Flow

For a release announcement across all platforms:

```bash
# 1. Post to X/Twitter
xurl POST /2/tweets -d '{"text": "APPROVED_TEXT"}'
# → Returns tweet URL

# 2. Post to Instagram
# Use browser tool or Buffer API

# 3. Post to TikTok (if video)
# Use TikTok Content Posting API

# 4. Post to YouTube (if video)
# Use YouTube Data API
```

After posting, report back:
```
Posted your release announcement:

✅ X/Twitter: https://x.com/handle/status/123456
✅ Instagram: Posted (check @handle)
⏳ TikTok: Uploaded, processing
✅ YouTube: https://youtu.be/abc123

All platforms done. Want me to monitor engagement?
```

## API Credentials Needed

Add to `.env` or `workspace/TOOLS.md`:

```bash
# X / Twitter (via xurl)
# Run: xurl auth

# Instagram (via Meta Business Suite)
META_ACCESS_TOKEN=
META_IG_BUSINESS_ACCOUNT_ID=

# TikTok Content Posting API
TIKTOK_CLIENT_KEY=
TIKTOK_CLIENT_SECRET=
TIKTOK_ACCESS_TOKEN=

# YouTube Data API v3
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
YOUTUBE_REFRESH_TOKEN=

# Buffer (alternative — posts to all platforms)
BUFFER_ACCESS_TOKEN=
```

## Scheduling

For scheduled posts, use the cron tool:

```
cron create --at "2026-04-25T09:00:00" --message "Post release announcement to all platforms"
```

Or use Buffer/Later APIs for native scheduling on each platform.

## Safety Rules

1. **ALWAYS show the draft and get approval before posting** (unless given standing permission)
2. **Never post the same text to all platforms** — each platform has its own language
3. **Double-check media attachments** before posting (wrong image = disaster)
4. **Log every post** in memory for tracking and analytics
5. **Never delete a post** without explicit approval
6. **Handle errors gracefully** — if one platform fails, still post to the others
