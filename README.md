# Claw Music Manager

**Your AI music manager. Never sleeps. Never forgets a deadline. Doesn't take 20%.**

An OpenClaw skill pack that transforms your agent into a full-service music manager for independent artists. Handles release planning, distribution, royalty tracking, social media, playlist pitching, press, sync licensing, merch, and fan engagement — all through Slack.

## Quick Start

```bash
# Install OpenClaw (if you haven't)
npm install -g openclaw

# Install this skill pack
clawhub install claw-music-manager

# Restart your gateway
openclaw gateway restart
```

Then DM your agent on Slack:
> "Plan the release for my new single dropping May 2nd"

## What's Included

### 14 Skills + Onboarding
| Skill | What It Does |
|-------|-------------|
| **Release Planner** | 6-8 week rollout plans with checklists and deadlines |
| **Distro Manager** | DistroKid/TuneCore submission and status tracking |
| **Royalty Tracker** | Streaming revenue aggregation across all platforms |
| **Social Scheduler** | Platform-optimized content drafting and scheduling |
| **Sample Clearance** | Rights holder research and clearance request drafting |
| **Playlist Pitcher** | Curator discovery, personalized pitches, placement tracking |
| **Press Kit** | EPKs, bios (3 lengths), press releases, one-sheets |
| **Sync Licensing** | Sync opportunity tracking and submission management |
| **Merch Ops** | Shopify product management, merch drops, discount codes |
| **Fan Engagement** | Klaviyo email campaigns, fan segmentation, community building |
| **PRO Registration** | ASCAP/BMI signup, SoundExchange, MLC, publishing admin |
| **Music Lawyer** | Contract red flags, deal structures, copyright, splits, trademark |
| **Tour & Show Booking** | Venue research, booking pitches, tour routing, advancing, settlements |
| **Music Accounting** | Income/expense tracking, tax deductions, P&L, business structure |

**Guided Onboarding** — First-run setup that walks artists through configuring their profile, connecting platforms, and identifying immediate action items in one conversation.

### Workspace Files
- **SOUL.md** — Music manager personality and industry knowledge
- **AGENTS.md** — Operating manual with release cycle awareness
- **TOOLS.md** — Platform credentials and tool configuration
- **USER.md** — Artist profile template (fill in your details)

### Templates
- `release-plan.md` — Release timeline with budget and goals
- `press-release.md` — Music press release template
- `epk.md` — Electronic press kit template

## Who This Is For

Independent artists and small teams who:
- Release 2-12 singles/EPs per year
- Have <500K followers across platforms
- Do their own marketing, distribution, and business ops
- Want a manager that works 24/7 for less than a human one

## Setup

After installation:

1. **Fill in `workspace/USER.md`** with your artist info, platform links, and goals
2. **Add credentials to `workspace/TOOLS.md`** (Spotify, Klaviyo, Shopify — all optional)
3. **Customize `workspace/SOUL.md`** if you want to adjust the manager's personality
4. **Start talking** — "What's my release calendar look like?" / "Draft a press release for my new single"

## Examples

```
You: "I have a single ready. It's an R&B track called 'After Hours'.
      I want to drop it on April 25th."

Claw: Here's your release plan for "After Hours" dropping April 25th:

      📅 This week (T-6): Finalize master + artwork, submit to DistroKid
      📋 Next week (T-5): Submit Spotify editorial pitch
      🔗 March 28 (T-4): Launch pre-save campaign
      📰 April 4 (T-3): Send press release, start playlist outreach
      📱 April 11 (T-2): First social teaser, email fan list
      🚀 April 18 (T-1): Daily content, final push
      🎵 April 25: RELEASE DAY

      Want me to start with the Spotify editorial pitch? I'll need the
      song's story, mood, and 2-3 similar artists.
```

## License

MIT — Built by [Movemint Holdings](https://movemint.co)
