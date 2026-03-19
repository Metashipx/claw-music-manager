---
name: strategy-engine
description: Evolving career strategy engine that analyzes the artist's current data, research findings, and market conditions to produce actionable strategy updates. Runs monthly, adjusts tactics based on what's working and what's not, and maintains a living strategy document. Use when the artist asks "what should I focus on," "what's my strategy," "is this working," or for monthly strategy reviews.
metadata: { "openclaw": { "emoji": "🧭" } }
---

# Strategy Engine — Adaptive Career Intelligence

A living strategy that evolves monthly based on data, research, and results.

## When to Activate

- "What should I focus on?" "What's my strategy?" "Is this working?"
- "Monthly review" "Quarterly check-in" "Am I on track?"
- "What should I change?" "Something's not working"
- Monthly cron trigger for strategy review
- After significant events (viral moment, playlist add, show milestone)

## How It Works

The strategy engine maintains a living document at `memory/strategy/current-strategy.md` that gets updated monthly based on:

1. **Data** — What the numbers say (streams, followers, revenue, engagement)
2. **Research** — What the daily researcher found (trends, opportunities, peer activity)
3. **Results** — What worked and didn't work last month
4. **Goals** — Progress toward the artist's stated goals
5. **Market** — Changes in the landscape that affect strategy

## The Living Strategy Document

Maintained at `memory/strategy/current-strategy.md`:

```markdown
# CAREER STRATEGY — [Artist Name]
Last updated: [Date]
Next review: [Date + 1 month]

## Current Position
- Tier: [Emerging / Growing / Established / Full-Time]
- Monthly listeners: [X] (trend: ↑/↓/→)
- Monthly revenue: $[X] (trend: ↑/↓/→)
- Follower growth rate: [X]%/month
- Release cadence: [X] tracks per [period]
- Live show frequency: [X] per month
- Revenue concentration: [top source at X%]

## Active Strategy (this month)

### Priority 1: [Biggest Lever]
What: [Specific strategy]
Why: [Based on data/research/goals]
Actions this month:
- [ ] [Action 1]
- [ ] [Action 2]
- [ ] [Action 3]
Success metric: [How we'll know it worked]

### Priority 2: [Second Lever]
What: [Specific strategy]
Why: [Reason]
Actions:
- [ ] [Action]
Success metric: [Metric]

### Priority 3: [Third Lever]
What: [Specific strategy]
Why: [Reason]
Actions:
- [ ] [Action]
Success metric: [Metric]

## What's Working (keep doing)
- [Thing 1] — evidence: [data]
- [Thing 2] — evidence: [data]

## What's Not Working (stop or change)
- [Thing 1] — evidence: [data] — pivot to: [new approach]
- [Thing 2] — evidence: [data] — pivot to: [new approach]

## Experiments Running
- [Experiment]: [hypothesis] — measuring: [metric] — until: [date]

## Upcoming Opportunities
- [Opportunity 1] — deadline: [date] — action needed: [what]
- [Opportunity 2] — deadline: [date]

## 6-Month Trajectory
If current trends continue:
- Listeners: [projected]
- Revenue: [projected]
- Goal progress: [on track / behind / ahead]
- Key risk: [biggest threat to progress]
```

## Monthly Strategy Review Process

Run on the 1st of each month (via cron):

```bash
cron create --schedule "0 10 1 * *" --message "Run monthly strategy review for [Artist Name]. Read current strategy, analyze last month's data, review research findings, update strategy document, and message artist with review summary."
```

### Step 1: Gather Data

Pull from all available sources:
- Streaming numbers (Spotify for Artists, distributor dashboard)
- Social media metrics (follower counts, engagement rates, growth)
- Revenue data (streaming payouts, show guarantees, merch sales)
- Content performance (which posts/videos performed best)
- Research findings (from `memory/research/` files)
- Show/event results
- New connections made

### Step 2: Analyze Trends

```
MONTHLY DATA REVIEW — [Month Year]

GROWTH:
  Spotify listeners:    [X] → [X] ([+/-X]%, [+/-X] absolute)
  Instagram followers:  [X] → [X] ([+/-X]%)
  TikTok followers:     [X] → [X] ([+/-X]%)
  Email list:           [X] → [X] ([+/-X]%)

REVENUE:
  Total:                $[X] → $[X] ([+/-X]%)
  By stream:            [breakdown with changes]

CONTENT:
  Best performing post: [what + why it worked]
  Worst performing:     [what + why it didn't]
  Engagement rate:      [X]% (benchmark: [X]% for their tier)

RELEASES:
  Released this month:  [what]
  Performance vs expected: [above/below/on target]

LIVE:
  Shows played:         [X]
  Total attendance:     [X]
  Revenue from live:    $[X]
  Best show:            [which + why]
```

### Step 3: Evaluate Current Strategy

For each active priority from last month:
- Did we execute the actions? (yes/no/partial)
- Did we hit the success metric? (yes/no/partial)
- What did we learn?
- Should this continue, evolve, or stop?

### Step 4: Identify Pivots

Based on the data, determine:

**Keep doing** (evidence of working):
- Actions with positive trend correlation
- Content formats with above-average engagement
- Revenue streams that are growing

**Stop doing** (evidence of not working):
- Actions with no measurable impact after 60 days
- Content formats with declining engagement
- Strategies that cost more than they return

**Start doing** (new opportunities):
- Trends identified by daily researcher
- Revenue streams not yet activated
- Platforms or formats not yet tested
- Connections or opportunities not yet pursued

### Step 5: Update Strategy Document

Rewrite `memory/strategy/current-strategy.md` with:
- Updated current position (new numbers)
- New priorities for this month
- Moved working items to "keep doing"
- Moved failing items to "stop or change"
- New experiments to run

### Step 6: Message the Artist

Send a monthly strategy update:

```
📊 MONTHLY STRATEGY REVIEW — [Month]

THE NUMBERS:
  Listeners: [X] ([trend])
  Revenue: $[X] ([trend])
  Best win: [specific achievement]

WHAT WORKED:
  ✅ [Strategy 1] — [result with data]
  ✅ [Strategy 2] — [result]

WHAT DIDN'T:
  ❌ [Strategy] — [why, and what we're changing]

THIS MONTH'S FOCUS:
  1. [New priority 1] — because [reason]
  2. [New priority 2] — because [reason]
  3. [New priority 3] — because [reason]

OPPORTUNITY ALERT:
  🎯 [Time-sensitive opportunity]

6-MONTH PROJECTION:
  If we keep this trajectory: [projection]
  To hit your goal of [goal]: we need [specific metric]

Questions? Want to adjust anything?
```

## Strategy Playbooks by Situation

### "I Just Released and It's Not Getting Streams"

```
Week 1 post-release is NOT when to panic. Here's the real timeline:

Day 1-3: Friends, family, existing fans stream
Day 4-7: Algorithm starts testing (Release Radar, Discover Weekly)
Day 7-14: Playlist curators respond (or don't)
Day 14-30: Organic discovery begins (if algorithmic signals are good)

What to do right now:
1. Check your save rate on Spotify for Artists. Above 5% = the song is connecting.
   Below 2% = might need a different marketing angle.
2. Push the content that's getting the most engagement. Double down.
3. Don't spam "go stream my song." Create content USING the song.
4. Reach out to 10 more playlist curators with personalized pitches.
5. Wait 30 days before calling it. Most sleeper hits emerge in week 3-4.
```

### "I'm Stuck at [X] Monthly Listeners"

```
Plateaus are normal. They break through one of these ways:

If stuck at <1K: Release cadence problem. You need more music out.
  → Release a track every 4-6 weeks for 6 months straight.

If stuck at 1K-10K: Discovery problem. People who hear you like you,
  but not enough people are hearing you.
  → TikTok content strategy (3x/week minimum)
  → Playlist pitching (20 curators per release)
  → Collaborate with artists at 10K-50K level

If stuck at 10K-50K: Conversion problem. People stream but don't follow/save.
  → Focus on save rate (ask fans to save, not just stream)
  → Build email list (convert streamers to owned audience)
  → Release playlists with your music + similar artists

If stuck at 50K+: Attention problem. You need a moment.
  → Sync placement
  → Festival slot
  → Collaboration with bigger artist
  → Viral content attempt (authentic, not forced)
```

### "Everything Is Going Right — What Now?"

```
Momentum is the rarest thing in music. When you have it:

1. RELEASE. Don't sit on music. Feed the algorithm while it's paying attention.
2. BOOK SHOWS in new markets. Your streaming data shows where your fans are.
3. PITCH SYNC. Your streaming numbers are social proof for music supervisors.
4. APPROACH BRANDS. Growing numbers = leverage for partnerships.
5. DON'T CHANGE YOUR SOUND. Whatever you did to get here, do more of it.
6. DOCUMENT EVERYTHING. This is your case study for press, grants, and future deals.
7. SAVE MONEY. Momentum doesn't last forever. Build the war chest now.
```

### "I'm Thinking About Signing a Deal"

```
Before you sign ANYTHING:

1. What exactly are you getting? (advance, marketing, distribution, sync?)
2. What are you giving up? (masters, publishing, term length, options?)
3. Is the advance recoupable? From what? (all sources or just recording?)
4. What's the reversion clause? (how do you get your rights back?)
5. Can you achieve the same result independently? (honestly assess)
6. Have a LAWYER review it. Not your friend. Not ChatGPT. A music lawyer.

The question isn't "is this a good deal." The question is "is this deal
better than what I can do on my own in the next [term length] years?"

If your current trajectory gets you to the same place in 2 years without
giving up ownership — don't sign. If the deal genuinely accelerates you
in a way you can't replicate — consider it seriously.
```

## Setting Up the Strategy Engine

During onboarding or when the artist says "set up strategy":

1. Create initial strategy document based on intake data
2. Set up monthly review cron
3. Connect to daily researcher output
4. Establish baseline metrics
5. Define first month's priorities based on goals and gaps

```bash
# Monthly strategy review
cron create --schedule "0 10 1 * *" --message "Monthly strategy review: analyze data, review research, update strategy, message artist with review."

# Quarterly deep review
cron create --schedule "0 10 1 */3 *" --message "Quarterly deep strategy review: comprehensive data analysis, goal progress assessment, revenue review, 6-month projection update."
```
