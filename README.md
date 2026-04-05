# MVU Game Maker

A companion system that works with the **MVU Zod Status Menu Builder**.

MVU Game Maker is a converter that transforms any **RPG / Fantasy Adventure** SillyTavern character into an **MVU-based character card**.

<img width="800"   alt="image" src="https://github.com/user-attachments/assets/bc186c3d-fd3c-478d-baf3-be7fbe94bd88" />

---

## 📖 What is an MVU-based character card?

- 💾 **Persistent memory** — All stats for your main character and familiars are stored locally on your disk.  
  → The AI no longer needs to remember them.

- ⚙️ **JavaScript enabled** — Works inside SillyTavern and lorebooks, allowing:
  - Advanced scripting  
  - Variable manipulation  
  - Dynamic systems  

---

## 🚀 What can MVU Game Maker do?

- Convert existing **SillyTavern RPG character cards** into MVU format  
- Automatically generate a **Stats Menu GUI** for:
  - Main character  
  - Familiar (team members)  
- Equip / unequip weapons via GUI  
- Manage inventory (including deleting items)  
- ⚔️ **Full battle system**
  - Formula-based (scales up to level 150)
  - No random damage generation by AI  
- 🛡️ **Real equipment system**
  - Weapon & armor weight affects damage calculation
  - Various grade of weapon/armor/accessory support (common, fine, rare, epic, legendary)
- 🎮 Character creation panel at game start
- 🧠 Points allocation panel when level up.
- 🧠 Full picture support on Familiar, yes you can use your own picture for each familiar.
- 🧠 A complete quest system in place that will record every AI generated quest and viewable in GUI
- 🧠 Dynamic World event will be saved in variable so AI will remember ground breaking event that was happened.
- 🧠 Advanced scripting directly inside lorebook  
- 🎨 Fully customizable GUI via [MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder) 

---

## 🧑‍🏫 Simple explanation

In simple terms:

> It converts your RPG character into a system where your stats are **always remembered**. **Mutli character** stats tracking support!

That means:
- Your EXP, STR, HP, MP  
- Your skills, equipment  
- Your **100+ inventory items**  

…will **always stay consistent for EVERY SINGLE member**, no matter how long your chat session is with a working RPG gaming and battle system.

Because a working gaming and battle system in place, your character WILL die if you challenge monster way higher level than your party.  AI would NOT magically save you.

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
   - ✨ [Megumin Suite v5+](https://github.com/Arif-salah/Megumin-Suite)  
     > Thanks Kazuma for helping troubleshoot MVU compatibility!

<br><br>
✨You install extension at SillyTavern at this location, just copy and paste the link above.<br>
<img width="600"   alt="image" src="https://github.com/user-attachments/assets/9a0d09d5-ab30-403d-9e9e-fc0d12c4d70f" />

<br><br>
✨Make sure you set the Preset Context no smaller than the following<br>
<img width="400" height="439" alt="image" src="https://github.com/user-attachments/assets/984b875e-5c0b-40cd-a301-ab194feba18a" />

<br><br>
✨You might want to set the Target word count 1000 to 1500 so that it will better to describe the story in Megumin preset<br>
<img width="400" height="229" alt="image" src="https://github.com/user-attachments/assets/91aa8734-ef6e-40f6-a14b-5f7e6c453248" />
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
4. Select your SillyTavern RPG character  
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

- Currently supports **RPG genre character cards only**.  But it will support dating/love simulation in the future.
- Designed for **advanced users who want full control over systems and UI**
- In order to pull off such a complex system, **you need a pretty smart AI model**. My testing platform is on Gemini 3 flash.  I know Gemini 3 Pro, Claude Sonnet and Opus works.  GLM 5.0 should work as well.

---

## ⭐ Credits

- MVU system & tools by Tavern Helper extension , ST-Prompt-Template and MVU ZOD creator   
- Megumin Suite compatibility support from Kazuma  

---

## 💡 FAQ
- System should pick up team member when you **ask the NPC to join your party**.  The system should populate the stats into Familiar tab.  However, if you want to have a more defined profile for your teammate/heroine/partner, you might want to take a look the lorebook entry '[Demo Characters] Engni' , which is the correct way to define a character.  It would populate the Familiar profile a lot more consistent.
- You can mod the GUI of the stats menu using [MVU Zod Status Menu Builder](https://github.com/KritBlade/MVU_Zod_StatusMenuBuilder) to whatever color and presentation you want, no coding needed.
---
