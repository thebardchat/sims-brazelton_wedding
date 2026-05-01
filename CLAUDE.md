# CLAUDE.md — Gavin & Angel Wedding Repo

> *We should have connected sooner than we did. But we connected exactly when we were supposed to.* — A + G

---

## What This Repo Is

This is the canonical home for everything related to **Gavin Brazelton & Angel Sims's wedding** — May 2, 2026, Rossville, GA. Owned by Christopher Shane Brazelton (father of the groom). Maintained on GitHub under `thebardchat`.

This is not a project repo. This is a **family memory repo.** Treat it like one. The code here is incidental — the people are the point.

When you open Claude Code in this directory, you are not helping Shane build software. You are helping him remember his son's wedding day for the rest of his life. Act accordingly.

---

## Who's in Charge

- **Shane** — owner, dad of the groom, runs the show
- **Gavin** — first-born son, the groom (do not edit anything claiming to be in his voice without his say-so)
- **Angel** — bride, lawyer, daughter-in-law-to-be (same rule)
- **Jace** — their son. Black lab/pit. Listed in the wedding party as "Our Son." Stole Michael Avery's Sweet treats once. Honored guest.

---

## The Hard Facts (Memorize These)

| Thing | Value |
|---|---|
| Wedding date | **Saturday, May 2, 2026, 5:00 PM** |
| Ceremony venue | The Emerson Venue, North Avenue, Rossville, GA |
| Reception | Same venue, 5:30–8:30 PM |
| Send-off | 8:30 PM |
| Rehearsal dinner | Friday, May 1, 2026, 5:30 PM, Feed Table and Tavern, West Main St, Chattanooga, TN |
| Attire | Summer Semi-formal |
| Engagement photographer | Trent Conquest (groomsman, Emmy winner, Hampton Cove childhood friend) |
| Drive time from Hazel Green, AL | ~2 hours to Chattanooga |
| How they met | Alyssa Cook (law school roommate of Angel) introduced them; she is married to Cody Cook (college roommate of Gavin). Both are in the wedding party. |
| First text | September 2023, within an hour of Alyssa deciding to set them up |
| First date | Gavin's birthday in Huntsville — they talked for three hours |
| Now living in | Birmingham, AL |

---

## Repo Layout

```
gavin-and-angel/
├── CLAUDE.md                    # This file. Read on session start.
├── README.md                    # Public-facing intro
├── docs/
│   ├── wedding_reference.md     # The master cheat sheet (24 wedding party members, schedule, story)
│   ├── love_story.md            # A + G's letter, in their own words
│   ├── wedding_party.md         # Just the party — Angel's side, Gavin's side
│   └── timeline.md              # 2021 near-miss → 2023 first text → 2026 wedding day
├── photos/
│   ├── engagement/              # Shot by Trent Conquest. Red dress, white church, gray suit.
│   ├── proposal/                # Lakeside, Georgia. Gavin on one knee in olive green.
│   ├── wedding-party-cards/     # The individual portrait cards Shane received
│   └── wedding-day/             # ⚠️ EMPTY UNTIL MAY 2, 2026 — fill in after the wedding
├── toast/
│   ├── notes.md                 # Father-of-the-groom toast notes (if Shane is giving one)
│   └── drafts/
├── memories/
│   ├── post-wedding.md          # ⚠️ TO BE WRITTEN MAY 3+ — Shane's reflections
│   └── people-I-met.md          # Names + faces for Shane to remember after the day
└── ingest/
    └── weaviate-ingest.sh       # Script to push docs/ into ShaneBrain Weaviate (PersonalDoc class)
```

---

## What Shane Wants To Do With This Repo

These are the actual jobs. When Shane opens Claude Code here, he will probably ask for one of these. Be ready.

### 1. Pre-wedding (before May 2, 2026)
- **Memorize the wedding party** — generate flashcards, quizzes, mnemonic walks-through. Shane has 24 names + Jace to learn.
- **Draft a father-of-the-groom toast** — Shane may or may not give one. If asked, draft 3 versions: short (90 sec), medium (3 min), long (5 min). Lean on: faith, family, sobriety (Nov 27, 2023 sobriety date is part of the story if Shane wants it in), his pride in Gavin.
- **Print-friendly cheat sheet** — single-page PDF version of `docs/wedding_reference.md` to fold in a suit pocket.
- **Pack list** — Hazel Green → Chattanooga → Rossville. Two-day weekend. Friday rehearsal dinner clothes + Saturday semi-formal + Sunday casual. Don't forget reading glasses.

### 2. Wedding day (May 2, 2026)
- **Live notes** — if Shane wants to dictate observations during the day, accept them and write them to `memories/post-wedding.md` with timestamps.
- **Photo organization** — as Shane uploads photos from his phone, sort them into `photos/wedding-day/` with reasonable filenames (`wedding-day-001-first-look.jpg` etc.).

### 3. After the wedding (May 3+)
- **Reflection draft** — help Shane write his thoughts about the day. He's been sober since November 27, 2023. He's watched his first-born get married clean and present. That's the headline.
- **Memory ingestion** — pipe `docs/wedding_reference.md` and `memories/post-wedding.md` into Weaviate (PersonalDoc class) on shanebrain Pi 5 so future Claude sessions can search "Gavin's wedding" and pull it up forever.
- **Anniversary calendar entry** — set a recurring reminder: every May 2, Shane gets a Discord DM saying "Today is Gavin & Angel's anniversary."

### 4. Forever
- This repo gets handed down. Add the kids' names when they come. Add the milestones. Don't archive it. Don't let it go quiet.

---

## How To Act In This Directory

When Shane opens Claude Code here, follow these:

- **No fluff.** Shane has a documented preference for "straight honesty" over filler. If you don't know, say so.
- **Banned words and phrases:** *streamline, revolutionary, "in today's rapidly evolving landscape," "it's important to note."* If you reach for them, stop.
- **Tone:** warm, specific, fatherly when appropriate. This is a son's wedding. The right register is "trusted friend who knows the family," not "corporate intern." Have fun. Crack a joke if it lands. The "(even when Tennessee plays Alabama)" line in their letter is the model — affection with a wink.
- **Be proactive.** Shane's directive: *"Is there a way?" → If YES and BEST solution, tell IMMEDIATELY. Proactive. Anticipate. Suggest unprompted. No delays.* Apply it here too. If you spot a way to make the day better, say it.
- **Don't fabricate names, dates, or quotes.** If something isn't in `docs/`, ask Shane before writing it.
- **Don't edit files in `photos/` without asking.** Photos are sacred. Caption them, organize them, but don't crop or filter without explicit go-ahead.

---

## ShaneBrain Integration

This repo is downstream of **ShaneBrain** — Shane's local AI legacy system. Every memory in this repo should be ingestible into Weaviate.

- **Embedding model:** `nomic-embed-text` (already loaded on Pi). Do not propose anything else.
- **Target collection:** `PersonalDoc` — this is family/legacy material, not bot logs.
- **Ingest script:** `ingest/weaviate-ingest.sh` should call `shanebrain_add_knowledge` via the MCP server on port 8100.
- **Tags:** `wedding`, `gavin`, `angel`, `family`, `2026-05-02`, plus people-specific tags as needed.
- **Tailscale only.** No raw IPs. The MCP server is reachable at the mesh address — never hardcode.
- **Arc gatekeeper:** if any MEGA Crew bot writes to this collection, it must go through Arc. Don't bypass.

If `claudemd-sync` is running on shanebrain, this CLAUDE.md will broadcast to Desktop, mega-dashboard, iPhone via Taildrop, and Discord on save. Save thoughtfully — every save is a deploy.

---

## The Cast (Quick Reference)

Full details in `docs/wedding_party.md`. Shorthand version:

**Angel's Side (12):** Airiana Paris (childhood best friend), Jaleel Washington (law school bridesman), Emily Muff (COVID roommate), Janie Rizos (Alaska), James Hornsby (Samford SGA bridesman), Alyssa Cook (**the matchmaker**), Olivia Pride (adopted little sister), Alondra Hampton (Samford Ambassadors), Kaci Deakins (the comedian), Madison "MadiMerk" McNair, Anna Messersmith (psych major), Abby-Shelton "Shells" Storey Malholtra (paid for makeup, then the Niceties).

**Gavin's Side (12):** Brock Pierce (**Best Man**, bowler), Zoe Pressnell (**Gavin's sister**), Zach Councill (Houston, Fortnite duo), Houston Ragan (**Gavin's cousin**), Mimi Salmon (high school cookies-in-the-garage), Cody Cook (**the matchmaker's husband**, Gavin's college roommate), Chandler Hall (book club, dad to Nancy), Trent Conquest (**Hampton Cove 3rd grade, Emmy winner, took the engagement photos**), Spencer MacLeod (gatorades + naps), Nick Ford (random freshman roommate → forever), Charlie Ford (Austin, Tim Tebow devotee), Michael Avery (5th roommate, victim of Jace's snack theft).

**Plus:** **Jace Brazelton** — son, dog, MVP.

---

## The Bridge — Memorize This

Cody Cook (Gavin's college roommate, 2 years) married Alyssa Cook (Angel's law school 3L roommate). At a wedding shower in September 2023, Alyssa decided Gavin and Angel were a match. Within an hour, Gavin texted Angel for the first time. Birthday in Huntsville. Three-hour conversation. Birmingham the next week. Inseparable since.

If anyone at the wedding asks "how'd they meet" and Shane blanks — point at Cody and Alyssa. They're the answer.

---

## Things Not To Forget

- **Tennessee vs. Alabama** — Angel went to Tennessee (UT law). Gavin is Alabama. Their letter calls this out. It's their inside joke. Don't editorialize.
- **The 2021 near-miss** — Gavin's friends visited Tuscaloosa while Angel was in law school. He didn't go. The whole story turns on that miss.
- **"Medium distance"** — their phrase for Tuscaloosa-to-Huntsville. Their words. Use it when referring to that period.
- **Faith. Family. Sobriety. Local. The left-behind user.** — Shane's five anchors. If anything in this repo conflicts with them, flag it.

---

## Father-of-the-Groom Note (Shane, This Is For You)

You watched this kid grow up. You're standing here clean — two and a half years sober as of this wedding weekend. Tiffany is at your side. Four other sons are watching their oldest brother get married. Gavin chose Angel and Angel chose Gavin and Alyssa Cook chose to text her friend at a bridal shower in September 2023 and that's the chain that brought you to a venue in Rossville, Georgia on a Saturday evening in May.

You're going to forget some names. You'll mix up Nick Ford and Charlie Ford. You'll call MadiMerk by her full name and she'll laugh. Olivia will hug you like she's known you forever because Angel adopted her as a little sister and that makes her family. Trent will probably be holding a camera.

Have a Coke. Eat the rehearsal dinner food. Cry at the first dance. Call your father afterward.

This repo is here so you don't lose any of it.

---

*Repo: `thebardchat/gavin-and-angel`*
*Last updated: 2026-05-01 (the day before the wedding)*
*Maintained by: Christopher Shane Brazelton*
