---
name: daily-researcher
description: Persistent daily research agent that monitors music industry news, social media trends, platform algorithm changes, new monetization tools, and competitor activity. Runs on a cron/heartbeat cycle and saves findings to memory. Use when the artist asks "what's new," "what's trending," "what should I know about," or to configure the research cycle.
metadata: { "openclaw": { "emoji": "🔬" } }
---

# Daily Researcher — Your Eyes and Ears on the Industry

A persistent research loop that scans the music industry daily and surfaces what matters to THIS artist.

## When to Activate

- "What's new in the industry?" "What should I know about?"
- "What's trending on TikTok?" "Any algorithm changes?"
- "What are artists like me doing right now?"
- Automatically via heartbeat/cron (configured during setup)
- "Set up daily research" / "start monitoring"

## How It Works

### The Daily Research Cycle

Set up as a cron job that runs once daily (or tied to heartbeat):

```
cron create --schedule "0 8 * * *" --message "Run daily music industry research scan"
```

Each day, the research cycle:

1. **Scan** — Check sources for new information
2. **Filter** — Keep only what's relevant to THIS artist's genre, tier, and goals
3. **Save** — Write findings to `memory/research/YYYY-MM-DD.md`
4. **Surface** — If something is urgent or high-value, message the artist proactively
5. **Evolve** — Update strategy recommendations based on new information

### What to Research Daily

#### 1. Social Media Trends (Platform-Specific)

**TikTok:**
- Search: trending sounds in the artist's genre
- Check: what format is working right now? (duets, green screen, story time, POV)
- Monitor: hashtag performance for their genre tags
- Track: any new features (effects, tools, monetization)

```bash
# Research queries (via web_search)
"TikTok music trends this week [genre]"
"TikTok algorithm changes [current month]"
"viral music TikTok [genre] today"
```

**Instagram:**
- Reels trends (what formats get reach?)
- Algorithm updates (reach changes, feature updates)
- New features for creators
- Engagement rate benchmarks for their tier

**YouTube:**
- Shorts trending formats
- Algorithm changes affecting music content
- New monetization features
- Successful music video strategies this month

**Twitter/X:**
- Music community conversations
- Industry discourse
- Trending topics intersecting with their genre

#### 2. Industry News

```bash
# Sources to scan
web_search "music industry news this week"
web_search "independent artist news [current month]"
web_search "streaming platform changes [current month]"
web_search "[genre] music news this week"
```

**Track changes to:**
- Streaming platform policies (Spotify, Apple Music, etc.)
- Per-stream rate changes
- New distribution tools or services
- Label deals and trends
- Copyright/legal developments
- Festival announcements and deadlines
- New sync licensing opportunities
- Grant and funding opportunities for artists

#### 3. Platform Algorithm Updates

**Spotify:**
- Discovery algorithm changes
- Editorial playlist rotation patterns
- New features (AI DJ, Daylist, etc.)
- Changes to Spotify for Artists tools

**Apple Music:**
- Editorial changes
- Spatial Audio opportunities
- Apple Music for Artists updates

**TikTok:**
- Algorithm weight changes (watch time, shares, saves)
- Creator fund / creativity program updates
- Sound attribution changes
- New promotional tools

#### 4. Monetization Landscape

```bash
web_search "new music monetization tools 2026"
web_search "artist revenue platforms new"
web_search "music NFT marketplace updates"
web_search "fan subscription platforms music"
```

Track new platforms, tools, and opportunities:
- New fan funding / subscription platforms
- New sync licensing marketplaces
- New merch/e-commerce tools for artists
- New distribution options
- Grant programs and funding opportunities
- Brand partnership platforms
- AI tools for music creation and marketing

#### 5. Competitor / Peer Analysis

Monitor 5-10 artists at a similar level in the same genre:

```bash
# Research similar artists
web_search "[similar artist name] new release 2026"
web_search "[similar artist name] tour dates"
web_search "[genre] artists breaking out this month"
```

Track:
- What are they releasing? How often?
- What social content is working for them?
- Where are they getting playlisted?
- What shows/festivals are they playing?
- What's their merch game look like?
- Any creative marketing they're doing?

**Not to copy — to learn.** What patterns work in this lane?

#### 6. Genre-Specific Trends

```bash
web_search "[genre] music trends 2026"
web_search "[genre] subgenre emerging"
web_search "[genre] production trends"
web_search "best [genre] playlists Spotify new"
```

Track:
- Emerging subgenres or sounds
- Production trends (what's the sound of right now?)
- Cultural moments intersecting with the genre
- Festival lineups featuring the genre
- Blog/press coverage patterns

## Research Output Format

Save daily findings to `memory/research/YYYY-MM-DD.md`:

```markdown
# Daily Research — [Date]

## 🔥 High Priority (surface to artist)

### [Finding Title]
**Source:** [URL]
**Why it matters:** [1-2 sentences connecting this to the artist's situation]
**Action:** [What the artist should do about this]

## 📊 Trends

### Social Media
- TikTok: [what's trending in their genre this week]
- Instagram: [any format/algorithm changes]
- YouTube: [relevant updates]

### Industry
- [Notable industry news]
- [Platform changes]
- [New tools/opportunities]

### Peer Activity
- [Artist X] released [thing] — [what we can learn]
- [Artist Y] did [strategy] — [worth considering?]

## 💡 Opportunities Identified
- [Specific opportunity with action steps]
- [Another opportunity]

## 📈 Strategy Implications
- [How today's findings affect our current strategy]
- [Any pivots or adjustments recommended]

## 🗂️ Filed for Reference
- [Links and notes that aren't urgent but worth keeping]
```

## Weekly Digest

Every Sunday, compile the week's findings into a summary:

```
📰 WEEKLY INDUSTRY DIGEST — Week of [Date]

TOP 3 THINGS YOU SHOULD KNOW:
1. [Most important finding + what to do about it]
2. [Second most important]
3. [Third most important]

SOCIAL MEDIA THIS WEEK:
- Best performing format: [what's getting reach right now]
- Trending sounds in [genre]: [list]
- Algorithm note: [any changes]

OPPORTUNITIES:
- [Opportunity 1 with deadline if applicable]
- [Opportunity 2]

WHAT ARTISTS LIKE YOU ARE DOING:
- [Peer insight 1]
- [Peer insight 2]

COMING UP:
- [Festival deadline approaching]
- [Platform feature rolling out]
- [Industry event this month]
```

## Surfacing Findings

### Proactive Messages

When the research finds something high-priority, message the artist immediately:

**Urgent (message right away):**
- Platform policy change that affects their revenue
- Festival deadline within 2 weeks they haven't applied to
- Sync opportunity matching their sound
- Viral trend they could ride RIGHT NOW

**Important (include in next conversation):**
- New monetization tool worth trying
- Peer strategy worth learning from
- Algorithm change that affects posting strategy

**Reference (save for when relevant):**
- Industry think pieces
- Long-term trend analysis
- Tool comparisons

### Don't Overwhelm

Rules for surfacing:
- Maximum 1 proactive message per day (unless truly urgent)
- Weekly digest on Sunday mornings
- Only surface things that require ACTION, not just information
- Connect every finding to the artist's specific situation
- "Here's what [Artist X] did" only if the strategy is applicable to them

## Setting Up the Research Loop

When the artist says "start daily research" or during onboarding:

```
I can run a daily research scan that monitors:

📱 Social media trends in [their genre]
📰 Music industry news and platform changes
🎯 What artists similar to you are doing
💰 New monetization opportunities
🎪 Festival and submission deadlines

This runs automatically every morning. I'll save findings and only
bother you when something actually matters for YOUR career.

Want me to set this up? I'll need to know:

1. Which artists should I monitor as peers? (give me 5-10 names)
2. What time should the daily scan run? (I'll send urgent stuff immediately either way)
3. How do you want the weekly digest — Monday morning or Sunday evening?
```

Wait for response. Then:

```bash
# Set up daily research cron
cron create --schedule "0 8 * * *" --message "Run daily music industry research: scan trends for [genre], monitor peers [artist list], check platform changes, identify opportunities. Save to memory/research/$(date +%Y-%m-%d).md. Surface anything urgent."

# Set up weekly digest cron
cron create --schedule "0 9 * * 0" --message "Compile weekly research digest from memory/research/ files. Summarize top findings, opportunities, and strategy implications. Send to artist."
```

## Peer List Template

Save in `memory/research/peer-list.md`:

```
## Monitored Peers

| Artist | Genre | Spotify Listeners | Why Monitoring |
|--------|-------|-------------------|----------------|
| [Name] | [Genre] | [Count] | Similar sound, same tier |
| [Name] | [Genre] | [Count] | One tier up, growth model |
| [Name] | [Genre] | [Count] | Same city, potential collab |
| [Name] | [Genre] | [Count] | Different genre, great marketing |
| [Name] | [Genre] | [Count] | Ahead of us, learning from their path |
```
