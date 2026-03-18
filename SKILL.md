---
name: claw-music-manager
description: "AI music manager for independent artists. 14 skills covering the full lifecycle: create, distribute, promote, perform, get paid, keep the money. Includes guided onboarding. Your manager that never sleeps."
metadata:
  {
    "openclaw":
      {
        "emoji": "🎵",
        "homepage": "https://github.com/Metashipx/claw-music-manager",
        "version": "1.0.0",
        "author": "Movemint Holdings",
        "license": "MIT",
        "requires": { "bins": ["node"] },
        "tags": ["music", "artist", "manager", "release", "distribution", "royalties", "social-media", "marketing", "legal", "ascap", "bmi", "publishing", "copyright", "touring", "accounting", "tax"],
      },
  }
---

# Claw Music Manager

Your AI music manager. Handles release planning, distribution, royalty tracking, social scheduling, playlist pitching, press kits, sync licensing, merch ops, and fan engagement — all through Slack or any OpenClaw channel.

## Installation

```bash
clawhub install claw-music-manager
```

Then restart your OpenClaw gateway. The agent will load the music manager personality and all 10 skills automatically.

## What It Does

| You say in Slack | Claw does |
|---|---|
| "Plan the release for my new single dropping April 15" | Creates an 8-week rollout plan with asset deadlines, platform submissions, and social calendar |
| "How are my royalties looking this month?" | Pulls data from DistroKid/Spotify/Apple Music and gives you a summary |
| "Schedule my album announcement across all platforms" | Drafts posts for IG, TikTok, Twitter/X with platform-specific formatting and schedules them |
| "Pitch this track to chill playlists on Spotify" | Researches curators, drafts personalized pitches, tracks responses |
| "Generate a press kit for my new EP" | Creates a full EPK with bio, high-res photos, streaming links, press quotes |
| "Check if this sample is clearable" | Researches the original track, identifies rights holders, drafts clearance request |
| "Set up a merch drop for the tour" | Creates Shopify products, sets up Klaviyo email campaign, schedules social teasers |

## Skills Included

1. **Release Planner** — Album/single rollout timelines with deadlines and checklists
2. **Distro Manager** — DistroKid/TuneCore release submission and status tracking
3. **Royalty Tracker** — Aggregate streaming royalties across all platforms
4. **Social Scheduler** — Cross-platform posting (IG, TikTok, Twitter/X, YouTube)
5. **Sample Clearance** — Research sample ownership and draft clearance requests
6. **Playlist Pitcher** — Find curators, draft pitches, track placements
7. **Press Kit** — Generate EPKs, bios, one-sheets, and press releases
8. **Sync Licensing** — Track sync opportunities and manage submissions
9. **Merch Ops** — Shopify store management for artist merchandise
10. **Fan Engagement** — Email campaigns, fan segmentation, direct engagement
11. **PRO Registration** — ASCAP/BMI signup, SoundExchange, MLC, publishing admin, international collection societies
12. **Music Lawyer** — Contract red flags, deal structures, copyright registration, splits agreements, trademark guidance
13. **Tour & Show Booking** — Venue research, booking pitches, tour routing, advancing shows, settlements, budget templates
14. **Music Accounting** — Income/expense tracking, tax deductions, quarterly estimates, P&L reports, business structure guidance

Plus a **guided onboarding flow** that walks new artists through setup in one conversation.

## Who This Is For

Independent artists and small teams (manager + artist) who:
- Release 2-12 singles/EPs per year
- Have <500K followers across platforms
- Currently do their own marketing, distribution, and business ops
- Want a manager that works 24/7 and costs less than a human one

## Setup

After installation, the agent loads workspace files that shape its personality. You can customize:
- `workspace/SOUL.md` — The agent's personality and music industry knowledge
- `workspace/AGENTS.md` — How the agent operates and what it prioritizes
- `workspace/TOOLS.md` — API credentials and tool configurations

See the README for full setup instructions.
