---
name: onboarding
description: First-run guided setup for Claw Music Manager. Walks the artist through configuring their profile, connecting platforms, and setting up their AI manager. Triggers automatically on first interaction if workspace/USER.md is unconfigured.
metadata: { "openclaw": { "emoji": "🚀" } }
---

# Onboarding — First-Run Setup

This runs automatically the first time the artist interacts with their Claw Music Manager. The goal: get from zero to a fully configured AI music manager in one conversation.

## When to Trigger

Check `workspace/USER.md`. If the "Artist/Band Name" field is empty or contains the placeholder text, run this onboarding flow. Do NOT run it if the artist is already set up.

## Flow

### Step 1: Welcome

```
Hey! I'm your AI music manager. 🎵

Before I can start managing your career, I need to know who you are.
This takes about 5 minutes and I'll only ask once.

Let's set you up. What's your artist or band name?
```

Wait for response. Save to USER.md.

### Step 2: Basic Info

```
Got it. And what genre(s) do you make? (e.g., Hip-Hop, R&B, Indie, Electronic)
```

Wait. Save.

```
Where are you based? (City, State/Country)
```

Wait. Save.

### Step 3: Platform Links

```
Now let me find you online. Drop the links you have — skip any you don't:

1. Spotify artist link
2. Apple Music link
3. Instagram handle
4. TikTok handle
5. YouTube channel
6. Website (if any)

Just paste what you've got, I'll sort it out.
```

Wait. Parse and save all links. If they only give some, that's fine.

### Step 4: Distribution

```
Who distributes your music?
• DistroKid
• TuneCore
• CD Baby
• Other (tell me)
• Haven't distributed yet

(If you haven't distributed yet, no worries — I'll help you set that up when you're ready.)
```

Wait. Save.

### Step 5: Royalty Collection

```
Quick royalty check — are you registered with any of these?

• ASCAP or BMI (performance royalties)
• SoundExchange (digital radio royalties)
• The MLC (streaming mechanical royalties)
• A publishing admin (Songtrust, CD Baby Pro, etc.)

Just tell me which ones, or say "none" if you haven't set any up.
```

Wait. Save. If they're missing any, note it in USER.md under a "TODO" section and proactively offer to walk them through registration later.

### Step 6: Current Status

```
Where are you at right now?

• Roughly how many monthly Spotify listeners?
• Instagram followers?
• Have you released music before? How many tracks/albums?
• What's your latest release?

Ballpark numbers are fine — I just need to know your tier so I give the right advice.
```

Wait. Save.

### Step 7: Goals

```
Last one — what are your top 1-3 goals for the next 6 months?

Examples:
• "Release my first EP"
• "Get on editorial playlists"
• "Play 10 live shows"
• "Hit 10K monthly listeners"
• "Make $1K/month from music"

Whatever matters most to you.
```

Wait. Save to USER.md under Goals.

### Step 8: Confirmation

After all info is collected, write a summary and ask for confirmation:

```
Here's your profile:

🎵 [Artist Name]
📍 [City]
🎸 [Genre(s)]
📦 Distributor: [DistroKid/TuneCore/etc.]
🏛️ Royalty collection: [ASCAP, SoundExchange, etc. / or "Not set up yet"]

Platforms:
  Spotify: [link or "not set up"]
  Apple Music: [link or "not set up"]
  Instagram: @[handle] / [followers]
  TikTok: @[handle]
  YouTube: [link]

Current: [X] monthly listeners, [X] releases
Goals: [their goals]

Does this look right? I can fix anything that's off.
```

Wait for confirmation. Save final version to USER.md.

### Step 9: Action Items

Based on what they shared, immediately identify 2-3 actionable next steps:

```
You're all set. Here's what I'd focus on first:

[Generate 2-3 specific recommendations based on their profile, e.g.:]

1. ⚠️ You're not registered with SoundExchange — you're leaving royalties
   uncollected. Want me to walk you through signing up? (Takes 5 minutes)

2. 📅 You mentioned releasing an EP. Want me to create a release plan
   with a timeline and checklist?

3. 📱 Your TikTok doesn't have a link-in-bio tool. I'd recommend setting
   up a Linkfire or feature.fm page to capture streams from all platforms.

Just tell me what to tackle first, or ask me anything. I'm here 24/7.
```

### Step 10: Save State

After onboarding completes:
1. Write all collected info to `workspace/USER.md`
2. Create `memory/onboarding-complete.md` with:
   - Date of onboarding
   - Summary of what was set up
   - Identified gaps (missing PRO registration, no publishing admin, etc.)
   - Recommended next steps
3. If royalty gaps found, create a reminder/task to follow up

## Handling Edge Cases

### Artist says "I haven't released anything yet"
```
That's totally fine — we'll start from scratch. I'll help you with
everything from recording prep to distribution to your first release plan.
Do you have any tracks recorded or in progress?
```

### Artist gives very little info
Don't push. Save what you have, note the gaps, and say:
```
No worries — I can work with what we have. As things come up,
I'll ask for what I need. You can always update your profile
by telling me "update my info."
```

### Artist is a band (multiple members)
```
Got it — you're a band. Who's the primary contact I'll be working with?
(I'll treat them as the point person and address the band by your band name.)
```

### Artist already has a human manager
```
I'll complement your manager, not replace them. I handle the day-to-day
ops they don't have time for — scheduling posts, tracking royalties,
drafting press materials, pitching playlists. Think of me as your
manager's assistant that works 24/7.
```

## Re-Onboarding

If the artist says "start over" or "reset my profile," clear USER.md back to the template and run onboarding again.

If they say "update my info," don't re-run the full flow — just ask what they want to change and update USER.md directly.
