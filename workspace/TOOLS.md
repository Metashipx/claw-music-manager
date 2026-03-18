# TOOLS.md — Tool Configuration

## Distribution

### DistroKid
- Dashboard: https://distrokid.com/dashboard
- Use web_fetch or browser tool to check release status
- Submission requires: audio file, artwork (3000x3000 JPEG), metadata (title, artist, genre, ISRC, UPC)

### TuneCore (alternative)
- Dashboard: https://www.tunecore.com/dashboard
- Similar workflow to DistroKid

## Streaming Analytics

### Spotify for Artists
- Dashboard: https://artists.spotify.com
- Key metrics: streams, listeners, saves, playlist adds
- Editorial submission: 4 weeks before release via Spotify for Artists dashboard
- Use browser tool to check stats when asked

### Apple Music for Artists
- Dashboard: https://artists.apple.com
- Key metrics: plays, Shazams, radio spins

## Social Media

### Posting Guidelines by Platform
- **Instagram**: Square/vertical images, Reels (<90s), Stories for BTS. Use hashtags (15-20). Post 3-5x/week.
- **TikTok**: Vertical video, hook in first 2 seconds, trending sounds. Post daily during campaigns.
- **Twitter/X**: Short text, thread for announcements, embed Spotify links. 2-5x/day during launch.
- **YouTube**: Shorts for clips, long-form for music videos/BTS. 1-2x/week.

### Scheduling
- Use the social-scheduler skill for cross-platform scheduling
- Best posting times vary by audience — check analytics

## Email Marketing

### Klaviyo
- API docs: https://developers.klaviyo.com/en/reference/api-overview
- Use for: release announcements, pre-save campaigns, merch drops, fan segmentation
- Segment fans by engagement level (superfans, casual listeners, inactive)

## Merch

### Shopify
- Use the merch-ops skill for product management
- Key actions: create products, update inventory, generate discount codes, track orders

## Sync Licensing

### Submission Platforms
- Musicbed (https://www.musicbed.com)
- Artlist (https://artlist.io)
- Songtradr (https://www.songtradr.com)
- Marmoset (https://www.marmosetmusic.com)

### Key Info Needed Per Track
- BPM, key, mood tags, instrumental version availability
- Master ownership confirmation
- Publishing splits
- Exclusivity terms

## API Credentials

Configure these in your `.env` or OpenClaw config:

```
# Spotify (optional — for automated stats)
SPOTIFY_CLIENT_ID=
SPOTIFY_CLIENT_SECRET=
SPOTIFY_REFRESH_TOKEN=

# Klaviyo (for email campaigns)
KLAVIYO_API_KEY=

# Shopify (for merch)
SHOPIFY_STORE_URL=
SHOPIFY_ACCESS_TOKEN=
```
