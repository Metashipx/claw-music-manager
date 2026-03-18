---
name: royalty-tracker
description: Track and analyze streaming royalties across Spotify, Apple Music, YouTube, and other platforms. Calculate revenue, identify trends, and flag notable changes. Use when the artist asks about earnings, royalties, streaming numbers, or revenue.
metadata: { "openclaw": { "emoji": "💰" } }
---

# Royalty Tracker

Aggregate and analyze streaming revenue across all platforms.

## When to Activate

- "How are my royalties?" "What did I make this month?" "Revenue report"
- "Which songs are earning the most?" "Streaming numbers"
- Proactive: notable spike/drop in streams or revenue

## Per-Stream Rates (2025-2026 estimates)

| Platform | Rate per stream | Notes |
|---|---|---|
| Spotify | $0.003-0.005 | Varies by country, premium vs free |
| Apple Music | $0.007-0.010 | Highest major platform rate |
| YouTube Music | $0.002-0.004 | Music-specific streams |
| YouTube (ad-supported) | $0.001-0.002 | Video views with ads |
| Amazon Music | $0.004-0.006 | Unlimited tier pays more |
| Tidal | $0.008-0.013 | Highest per-stream, smallest user base |
| Deezer | $0.003-0.005 | Similar to Spotify |
| TikTok | $0.003-0.005 | Creator music program |

## Revenue Report Format

When the artist asks about royalties, provide:

```
📊 Revenue Report — [Month/Period]

Streams:         [total] ([+/-X%] vs last period)
Estimated Revenue: $[amount]

Top Tracks:
1. [Track Name]  — [streams] streams — ~$[revenue]
2. [Track Name]  — [streams] streams — ~$[revenue]
3. [Track Name]  — [streams] streams — ~$[revenue]

By Platform:
• Spotify:      [streams] streams — ~$[revenue]
• Apple Music:  [streams] streams — ~$[revenue]
• YouTube:      [views] views — ~$[revenue]
• Other:        [streams] — ~$[revenue]

Notable:
• [Playlist add/removal, viral moment, sync placement]
• [Trend: growing/declining/stable]

Next Payout: ~$[amount] on [date]
```

## Revenue Splits

Ask the artist about their split structure:

| Scenario | Artist Share |
|---|---|
| Self-released, no publishing deal | 100% (minus distributor fee) |
| Co-written (50/50 split) | 50% of publishing, 100% of master |
| Label deal (typical indie) | 50-85% of master, varies on publishing |
| 360 deal | Varies — review contract carefully |

## Key Metrics to Track

- **Monthly listeners** (Spotify) — leading indicator of revenue
- **Save rate** — % of listeners who save the track (>5% is strong)
- **Playlist reach** — total followers across playlists featuring the artist
- **Revenue per 1K streams (RPM)** — varies by platform and geography
- **Revenue trend** — month-over-month, is it growing?

## Flags to Raise

- Stream count drops >20% week-over-week → investigate (playlist removal? algorithm change?)
- Revenue doesn't match stream count → check distributor for delayed payouts
- New track outperforming catalog by 3x+ → potential viral moment, push harder
- Streams from unexpected country → investigate (could be organic growth or bot activity)
