# MVU Game Maker

A companion system that works with the **[MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder)**.

MVU Game Maker is a converter that transforms SillyTavern character cards into **MVU-based character cards** with persistent stat tracking, real game mechanics, and customizable GUIs.

**Two genres supported:**
- ⚔️ **RPG / Fantasy Adventure** — Full battle system, equipment, familiars, quests
- 💕 **Slice of Life / Dating Simulation** — Trait-driven partners, D20 social checks, relationship progression, multi-partner support

<img width="800"   alt="image" src="https://github.com/user-attachments/assets/bc186c3d-fd3c-478d-baf3-be7fbe94bd88" />

---

## 📖 What is an MVU-based character card?

- 💾 **Persistent memory** — All stats for your main character, familiars, and partners are stored locally on your disk.  
  → The AI no longer needs to remember them.

- ⚙️ **JavaScript enabled** — Works inside SillyTavern and lorebooks, allowing:
  - Advanced scripting  
  - Variable manipulation  
  - Dynamic systems  

- 🎲 **Real game mechanics** — D20 rolls, stat-driven outcomes, formula-based calculations.  
  → AI cannot hand-wave away results. Failures stay failures. Success has to be earned.

---

## 🧑‍🏫 Simple explanation

> It converts your SillyTavern character into a system where stats are **always remembered** with **multi-character tracking** support.

Whether you're hunting dragons or trying to win her heart, **everything stays consistent** — EXP and HP for RPG, Trust and Affection for Dating — across every member, every reply, no matter how long the session runs.

Because real game mechanics drive the simulation:
- In RPG: your character WILL die if you fight monsters way above your party's level. AI will NOT magically save you.
- In Dating: a failed flirt stays failed. Repeated rejection is a real consequence. The AI cannot fudge a critical failure into a win.

---

## ⚔️ RPG / Fantasy Adventure Genre

Convert existing **SillyTavern RPG character cards** into MVU format and play with a full game system.

### Highlights

- 🎮 **Character creation panel** at game start
- 📊 Automatically generated **Stats Menu GUI** for Main Character and Familiars (team members)
- 🧰 **Equip / unequip** weapons and armor via GUI
- 📦 **Inventory management** (including deleting items)
- ⚔️ **Full battle system**
  - Formula-based (scales up to level 150)
  - No random damage generation by AI
- 🛡️ **Real equipment system**
  - Gear carries real weight in damage calculations
  - Five rarity grades supported: Common, Fine, Rare, Epic, Legendary
  - Weapons, armor, and accessories
- 🧠 **Points allocation panel** when leveling up
- 🖼️ **Full picture support** on Familiars — use your own picture for each team member
- 📜 **Complete quest system** — every AI-generated quest is recorded and viewable in GUI
- 🌍 **Dynamic World events** saved in variable so AI remembers groundbreaking events
- 🤝 **Familiar / team member system** — recruited NPCs join your party with full stat tracking

---

## 💕 Slice of Life / Dating Simulation Genre

Convert (or create) **SillyTavern Slice of Life / Romance character cards** into a deep dating simulation with persistent personality, real social mechanics, and multi-partner relationship tracking.

### Highlights

#### 🎭 Trait-Driven Personality Engine
- **3-layer stat hierarchy**: static **Traits** (Dominance, Confidence, Shyness, Patience, Curiosity, etc.) form an unbreakable personality ceiling; **Dispositions** (Trust, Comfort, Attraction, Respect, Affection) shift through story patterns; **Pulse** (Mood, Arousal, Excitement) updates every reply.
- Personality is **locked** — repeated story events shape disposition, but who she *is* never changes.
- Archetype templates (e.g. The Pragmatist) are preset trait combinations, not personality overrides.

#### 🎲 D20 Social Check System
- Flirts, persuasion, apologies, confessions, jealousy defusal, boundary pushes — all resolved by a D20 check against a dynamic DC.
- DC is **locked before the roll** — no cheating, no re-rolls, no "let me try again" loops.
- Failed checks **stay failed** — the AI must write the rejection. No hidden warmth, no "she secretly liked it" softening.
- Repeated failure → NPC walks away → grace mechanics make the next approach easier (no dead-end stories).

#### 💋 Intimacy System (DC-Based Physical Contact)
- Five independent act types: Incidental Touch, Sustained Contact, Kiss, Heated Contact, Sexual Encounter.
- DC scales with **relationship stage**, **situation** (privacy, alcohol, mood), **partner traits**, and **disposition**.
- No forced ladder — any act can happen at any time if she's ready for it.

#### 💢 Conflict System
- `ConflictActive` flag triggers on critical failures, trust betrayals, or boundary violations.
- Partner's argument style, escalation speed, and scope-creep are **driven by her Traits** (Dominance, Patience, EmotionalStability).
- Apology checks resolve conflicts. Resolution writes ImportantEvents memory.

#### 🎯 Partner-Initiated Actions (Initiative System)
- Partners autonomously initiate flirts, plans, confessions, physical escalation, or confrontation — without {{user}} prompting.
- Triggered by stat thresholds and trait combinations every reply.
- You don't always make the first move — sometimes she does.

#### 💝 Relationship Progression
- Stages: Stranger → Acquaintance → Friend → Close Friend → Crush → Dating → Girlfriend → Partner / Wife.
- Intimate route: Friend → Friends With Benefits → Stable Sex Partner.
- Each stage has **gate conditions** (Affection + Trust/Comfort/Attraction thresholds) and many require a story milestone (e.g. successful Confession check, marriage event).
- On advancement: Affection resets to 0, Stage Promotion Decay applies (50% reduction to Trust/Comfort/Respect/Attraction) — fresh dynamics for the new stage.

#### 👥 Multi-Partner (Harem) Support
- Each partner is a fully independent entry under `Partner.<EnglishFirstName>`.
- Independent stat pools, memory collections, traits, secrets, and relationship timelines.
- Cross-partner Friends collection — partners can have opinions about each other based on direct interaction.

#### 🧠 Memory & Event System
- **PositiveMemories** (max 5) — written on Critical Success or D20 ≥ 18 with Success.
- **NegativeMemories** (max 5) — written on Critical Failure or D20 ≤ 3 with Failure.
- **ImportantEvents** (max 10) — relationship stage advances, conflict resolutions, milestones.
- FIFO replacement when at capacity (oldest by TimeStamp gets removed).

#### 🌍 World & NPC Tracking
- `World_Calc.NPCs` tracks named non-partner characters (friends, rivals, coworkers) with relationship, occupation, personality, last_seen.
- `World_Calc.Events` logs groundbreaking world events that override stale lorebook information.
- NPC promotion path — recurring named characters can be elevated to full Partner status with romantic intent.

#### 🏠 Friends Collection
- Each partner tracks her own social circle (her friends, your friends she's met, etc.).
- FriendshipScore (0-100) updates **only on direct interaction** between the two characters — not on shared witness or co-presence.
- Partner-to-Partner friendships tracked symmetrically.

#### 💰 Economic System
- Currency: Ɉ JPM (Japon Mark) — fictional currency at JPY scale.
- Monthly salary auto-deposited on the 1st of each month for {{user}} and all employed partners.
- Salary bracket affects social check DC (status modifier).
- Spending tracked through narrative events (gifts, dates, dinners).

#### 📋 Quest System (Dating-Style)
- Quests have `Desc` (stable brief), `Objective` (testable finish condition), `ProgressSummary` (rolling status), `Reward`, `Status`, `LastUpdated`.
- Relative deadlines ("in two weeks") are auto-converted to absolute in-game dates on creation.
- Quest completion grants stat rewards based on quest theme (Trust, Respect, Affection, etc.) and any explicit rewards.

#### 🎮 Character Creation Panel
- Configure {{user}} at game start: Name, Age, Gender, Race, Occupation, Charisma, Social Energy, Monthly Salary.
- Charisma and Social Energy directly affect social check DCs.

#### 📓 Boundaries System
- Partner has a two-part Boundaries text: 1 social/non-sexual + 1 sexual.
- Boundaries can **evolve** through explicit story renegotiation OR de facto supersession (when prior story events render the limit moot).
- Anti-abuse guards prevent the AI from bypassing boundaries that are merely high-DC.

---

## 🛠️ Shared Features (Both Genres)

- 🎨 **Fully customizable GUI** via [MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder) — click and drag, no coding required
- 💾 **Persistent stat storage** in SillyTavern variables
- ⚙️ **Advanced scripting** directly inside lorebook (JavaScript supported)
- 🔧 **JSONPatch-based** variable updates with strict validation
- 🛡️ **Schema enforcement** via Zod — invalid values are rejected before they corrupt your save

---

## 🔗 Compatibility

Works with:

👉 **[MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder)**  
Customize everything in the stats menus by click and drag (No coding required although we do support javascript for advance scripting):
- GUI layout  
- CSS styling  
- Logic & scripting  
- Variable structure  

---

## 🛠️ Installation

_All extensions are open source._

1. Open **SillyTavern → User Settings**
2. Set **Language = English**

<img width="600"  alt="image" src="https://github.com/user-attachments/assets/90d14427-1d01-4585-a1c5-6bfa6289846f" />

<br><br>
3. Install required extensions:  (In case you have difficulty to install first two extensions, you can watch the [video](https://www.youtube.com/watch?v=Jh1ojfiqGXI) here)
   - 🔧 [Tavern Helper](https://github.com/N0VI028/JS-Slash-Runner)
   - 🧩 [ST-Prompt-Template](https://codeberg.org/zonde306/ST-Prompt-Template/)
   - ✨ [Megumin Suite v5+](https://github.com/Arif-salah/Megumin-Suite)  (pick v6 dreamteam lite and COT v6 lite if you are using v6)
     > Thanks Kazuma for helping troubleshoot MVU compatibility!
   - ✨ [Izumi English Preset](https://discord.gg/C6HabNwzn7) - If you don't want to use Megumin Suite, you can use this simpler preset also support MVU
   - ✨ [Frankenstein v4.2 fatman preset](https://rentry.org/freaky-frankenstein-presets) works but without extensive testing.

<br><br>
✨You install extension at SillyTavern at this location, just copy and paste the link above.<br>
<img width="600"   alt="image" src="https://github.com/user-attachments/assets/9a0d09d5-ab30-403d-9e9e-fc0d12c4d70f" />

<br><br>
✨Make sure you set the Preset Context no smaller than the following<br>
<img width="400" height="439" alt="image" src="https://github.com/user-attachments/assets/984b875e-5c0b-40cd-a301-ab194feba18a" />

<br><br>
✨You might want to set the Target word count 1000 to 1500 so that it will better to describe the story in Megumin preset<br>
<img width="600"  alt="image" src="https://github.com/user-attachments/assets/fe2b8a31-1f1f-4c3a-92a0-81cc9d2643f3" />

<br><br>

✨Check the MVU Compatiblity icon in Megumin preset<br>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/0a955501-eb9c-4199-83af-37449c428480" />


<Br><br>

✨If you are using Megumin v6, Use DreamTeam Lite<br>
<img  width="600" alt="image" src="https://github.com/user-attachments/assets/244ab5bd-05e5-41b4-be86-9ccc5fef5126" />
<br>
<img width="600"  alt="image" src="https://github.com/user-attachments/assets/4a79c653-2739-4392-b4b0-7e6361b52113" />



<Br><br>
4. Download:
   - 📦 [MVU Game Maker](https://github.com/KritBlade/MVU_Game_Maker/releases)
<br><br>
---

## ▶️ How to use

> Make sure all required extensions are installed first.

1. Extract the MVU Game Maker ZIP  
2. Double-click `index.html`  
3. Click **Load Character Card**
4. Select your SillyTavern RPG character   **(DO THIS FIRST)**
5. Click **JSON Export** (top-right corner)  
6. Click **Download PNG Card**  
7. Open SillyTavern → Import character card  
8. Click **Import → OK → OK**

9. Click the **Megumin preset icon** (top-right):
   - Enable ✅ **MVU Compatibility**  
     → Found under **Format Blocks**  
   - Click **Save**

---

## 🎉 You're ready!

Start your game with a **fully persistent, system-driven RPG experience** powered by MVU Game Maker.

---

## 💡 Notes

- Supports **RPG / Fantasy Adventure** and **Slice of Life / Dating Simulation** character cards.
- Designed for **advanced users who want full control over systems and UI**.
- In order to pull off such a complex system, **you need a pretty smart AI model**. My testing platform is on Gemini 3 Flash. Gemini 3 Pro, Claude Sonnet, and Claude Opus all work well. GLM 5.0 should also work.
- Slice of Life genre is more sensitive to model quality than RPG — the trait-driven personality system and D20 social check enforcement need a model that can resist the urge to "soften" failures.

---

## ⭐ Credits

- MVU system & tools by Tavern Helper extension, ST-Prompt-Template and MVU ZOD creator
- Megumin Suite compatibility support from Kazuma

---

## 💡 FAQ

### RPG Genre
- System should pick up team members when you **ask the NPC to join your party**. The system will populate stats into the Familiar tab. For a more defined profile, look at the lorebook entry `[Demo Characters] Engni` for the recommended way to define a character.

### Slice of Life / Dating Genre
- A character is promoted to **Partner** only when she meets all four criteria in `<encounter_guide>` (named character, recurring presence, personal interaction, romantic intent). Friends, mentors, coworkers without romantic signal stay as NPCs in `World_Calc.NPCs`.
- **Repeated social check failures are not a dead end.** When the partner walks away due to repeated rejection, the system automatically resets ConflictActive to false, lowers Stress, and (if she was a Stranger) advances her to Acquaintance — so the next encounter is meaningfully easier.
- **Boundaries evolve, they don't disappear.** The system supports two paths: explicit verbal renegotiation, OR de facto supersession when prior story events have already objectively resolved the named condition.
- System should pick up and populate as partner when the **the NPC play a major role in lorebook **. The system will populate stats into the Partner tab. For a more defined profile, look at the lorebook entry `[Demo Characters] Mina` for the recommended way to define a character.

### Both Genres
- You can mod the GUI of the stats menu using [MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder) to whatever color and presentation you want — no coding needed.

---
