# 🏴‍☠️ Sailing Kingdom Bot — User Guide

> ## 🧠 How the Bot Works / Как работи ботът
>
> Sailing Kingdom Bot is a **per-server Discord bot**. Each server has its own configuration, channels, roles, data and enabled features. Changes made on one server do not affect another server.
>
> The bot mainly works in three ways:
>
> **🔵 Commands** — A user types a command such as `!wanted` or `!shipstatus`, and the bot performs the requested action.
>
> **🟢 Automatic systems** — The bot reacts to Discord events without a command, such as new members joining, links being posted, screenshots being uploaded, or roles changing.
>
> **🔐 Password-protected systems** — Leveling, Flag Translate, Auto-Translate and AI Chat are disabled by default and must be activated for each server with a password provided by the bot owner.
>
> ### 🔄 Basic Bot Flow
>
> ```text
> USER / DISCORD EVENT
>          │
>          ├── 🔵 !command ───────→ BOT ─────→ ACTION
>          │
>          ├── @Bot ──────────────→ AI CHAT
>          │
>          └── 🟢 Automatic Event
>                 ├── New member
>                 ├── Link posted
>                 ├── Screenshot posted
>                 └── Role changed
>                           │
>                           ↓
>                          BOT
>                           │
>                           ↓
>                         ACTION
> ```
>
> ### 🔐 Permission Levels
>
> | Level | Meaning |
> |---|---|
> | **Everyone** | Any server member can use the feature. |
> | **Mod** | A member with the server's configured `mod_role`, or an Administrator where specified. |
> | **Admin** | A Discord member with Administrator permission. |
> | **Bot Owner** | The owner of the bot. Used for password-protected feature activation. |
>
> ### 🧩 Feature Types
>
> | Icon | Type | How it works |
> |---|---|---|
> | 🔵 | Command | Requires a command such as `!wanted`. |
> | 🟢 | Automatic | Triggered by an event; no command is required. |
> | 🔐 | Password | Must first be enabled for the current server. |
> | 🤖 | AI | Uses the bot's AI system to interpret or generate content. |
>
> ### 📌 Important Concepts
>
> **Per-server:** Configuration and feature state are independent for every Discord server.
>
> **Edit-in-place:** Some panels and status messages are created once and then updated instead of creating a new message every time.
>
> **Automatic does not always mean unrestricted:** Some automatic systems may still depend on a configured channel, API key or other setup.
>
> **AI actions may require confirmation:** For example, `!shipstatus-image` shows a preview and waits for a Mod/Admin to confirm before changing the ship status.
>
> **Configuration first:** Use `!checkconfig` to see what is configured, what is missing, and the status of supported systems.
>
> ### 🗺️ Recommended Setup Order
>
> ```text
> 1. Enable Developer Mode
>          ↓
> 2. Configure channels / roles with !setconfig
>          ↓
> 3. Run !checkconfig
>          ↓
> 4. Configure optional systems you want to use
>          ↓
> 5. Enable password-protected features when needed
>          ↓
> 6. Use the commands / automatic systems
> ```
>
> The sections below are the detailed command and feature reference.


# 🏴‍☠️ Sailing Kingdom Bot — User Guide

> **A complete guide for users, moderators, and administrators.**
>
> This guide explains not only which commands exist, but also **what the bot does, when it acts automatically, what permissions are required, and what happens after each action.**

---

## 🧭 Quick Navigation

- [🧠 How the Bot Works](#-how-the-bot-works--как-работи-ботът)
- [🚀 Quick Start](#-quick-start--бърз-старт)
- [🇬🇧 English](#-english)
- [🇧🇬 Български](#-български)
- [🛠️ Troubleshooting](#-troubleshooting)
- [📚 Command Reference](#-command-reference)

---

## 🧠 How the Bot Works / Как работи ботът

### 🏗️ 1. One bot, separate server configuration

Each Discord server has its **own configuration and data**.

That means:
- one server's channels, roles, crew, blacklist, bounty data, and settings do not automatically affect another server;
- optional systems can be enabled/configured independently;
- changing a setting on one server does not change the same setting on another server.

### 🔵 2. Commands

Commands are actions that a user starts manually.

```text
USER
  │
  └── !command
        ↓
       BOT
        ↓
   Permission check
        ↓
     Validation
        ↓
      ACTION
```

### 🟢 3. Automatic systems

Some features react to Discord events without a command.

```text
DISCORD EVENT
     │
     ├── New member joins
     ├── Link is posted
     ├── Screenshot is posted
     ├── Message is deleted
     └── Scheduled time is reached
              ↓
             BOT
              ↓
       Automatic action
```

### 🔐 4. Password-protected systems

Some optional systems require a password supplied by the bot owner.

```text
Admin
  ↓
!feature-enable <password>
  ↓
Bot verifies password
  ↓
Feature enabled for THIS server
```

### 🤖 5. AI-powered systems

AI features can read information from messages or screenshots and then perform an action.

For actions that can change server data, the guide clearly identifies whether the action is:
- automatic;
- confirmed by the user;
- restricted to Moderators/Admins.

### 🛡️ 6. Permission levels

| Level | Typical access |
|---|---|
| 👤 Everyone | Normal user commands and allowed interactions |
| 🛡️ Moderator | Moderation, crew management, bounty management, etc. |
| 👑 Admin | Server configuration and administrative systems |
| ☠️ Bot Owner | Bot-level secrets such as activation passwords |

> **Important:** A feature being automatic does not necessarily mean that everyone can manually trigger or configure it.

---

## 🚀 Quick Start / Бърз старт

For a new server, use this order:

```text
1. Invite the bot
      ↓
2. Enable Developer Mode
      ↓
3. Create the required channels & roles
      ↓
4. Run !setconfig for the needed settings
      ↓
5. Run !checkconfig
      ↓
6. Configure Moderator/Admin permissions
      ↓
7. Enable optional systems
      ↓
8. Test each system
      ↓
9. Use the Command Reference when needed
```

### ✅ Minimum recommended first test

```text
!checkconfig
     ↓
Fix ❌ missing settings
     ↓
Test one command
     ↓
Test one automatic feature
     ↓
Check admin_log_channel
```

---

## 🇬🇧 ENGLISH

### 🚀 Getting Started — New Server Setup

**1. Enable Developer Mode**
Settings → Advanced → Developer Mode → right-click channel/role → **Copy ID**

**2. Full configuration (Admin only):**

```
!setconfig level_up_channel         <id>  ← channel for level-up messages
!setconfig log_channel              <id>  ← channel for DB sync log
!setconfig stats_channel            <id>  ← channel for !top leaderboard
!setconfig admin_log_channel        <id>  ← channel for mod logs + crew approvals
!setconfig welcome_channel          <id>  ← channel for new members
!setconfig belly_rush_channel       <id>  ← channel for the Belly Rush panel
!setconfig crew_approval_channel    <id>  ← channel for permanent crew approvals (optional)
!setconfig belly_rush_roles_channel <id>  ← channel for ship commands only (!want, !ship-captain, etc — everything else auto-deleted)
!setconfig reminders_channel        <id>  ← channel for reminders
!setconfig repair_channel           <id>  ← channel for repair-ship commands
!setconfig translator_channel       <id>  ← channel for two-way AI translator
!setconfig bot_status_channel       <id>  ← channel for Online/Offline status
!setconfig bot_info_channel         <id>  ← channel for the bot manual
!setconfig unit_build_channel       <id>  ← channel for !hero commands
!setconfig bounty_channel           <id>  ← channel for !wanted posters
!setconfig rules_channel            <id>  ← rules channel (for welcome message)
!setconfig general_channel          <id>  ← general chat (for welcome message)
!setconfig rookies_role             <id>  ← role for new members (auto-created)
!setconfig player_role              <id>  ← role after verification (auto-created)
!setconfig mod_role                 <id>  ← moderator role
!setconfig restricted_channel       <id>  ← channel with mention restrictions
!setconfig protected_users     <id1,id2>  ← protected users (IDs separated by ,)
!setconfig bday_channel             <id>  ← birthday channel (optional)
!setconfig bday_user                <id>  ← birthday user ID (optional)
!setconfig blacklist_channel        <id>  ← channel for the live Belly Rush blacklist embed (optional)
!setconfig shipless_list_channel    <id>  ← channel for the auto-updating list of members without a ship (optional)
!setconfig ship_status_channel      <id>  ← channel where !shipstatus always posts, regardless of where typed (optional)
!setconfig bounty_upload_channel    <id>  ← channel where any screenshot auto-triggers a bounty update, no command needed (optional)

```

**3. Check what's missing:**

```
!checkconfig   ← configured ✅, missing ❌, system status 🟢/🔴
!getconfig     ← all current values

```

> 💡 **Rookie** and **Player** roles are created automatically!

---

### 🎖️ Leveling & XP — Password Activation

Disabled by default. Password provided only by the bot owner.

```
!leveling-enable <password>   ← activate XP for THIS server
!leveling-disable             ← disable (Admin only)

!rank       ← level and progress bar (auto-deletes after 60s)
!top        ← Top 10 most active (Admin only)
!sync       ← manually flush XP to database (Admin only)

```

---

### 🌐 Translation Systems — Password Activation

#### 1. Flag Reaction Translator

React with a flag → translation in channel, disappears after 2 min.

```
!translate-enable <password>   ← activate for THIS server
!translate-disable             ← disable (Admin only)

```

Supports 50+ languages. Works in **all channels**.

#### 2. Auto-Translate Non-English Messages

Non-English message → English translation below it. **Does not disappear.**

```
!auto-translate-enable <password>   ← activate for THIS server
!auto-translate-disable             ← disable (Admin only)

```

Works in **all channels** except `#ai-translator` and admin channels, plus any
channels added to the ignore list below.
Ignores: `!` commands, very short messages, mostly Latin text.

**Extra ignored channels (Admin only):**

```
!ignoretranslate-add <#channel>      ← stop auto-translating in this channel
!ignoretranslate-remove <#channel>   ← resume auto-translating in this channel
!ignoretranslate-list                ← show extra ignored channels

```

#### 3. AI Channel Translator (#translator\_channel)

For conversation between people speaking different languages.

- Write in **any language** → translated to English
- Reply in English → translates back to their language
- Remembers language for 5 hours | Cooldown: 5 seconds

---

### ⚔️ Mania — Setup & Usage

```
!mania-addguild ts @ThousandSunny #mania-strategy #general
!mania-guilds              ← list all guilds
!mania-removeguild ts      ← remove a guild

mania-plan ts / all        ← start plan with ✅ ❌ ⏳
mania-list ts              ← show votes, ping missing members
mania-dm ts                ← DM everyone who hasn't voted

mania-strategy
Kronos - @Luffy @Zoro      ← each line = one boss
Hydra - @Nami @Sanji

```

---

### 🚢 Belly Rush — Ships & Crew

**Ship management (Admin):**

```
!ship-add Sunny ☀️ @mugi-role      ← add a ship
!ship-remove Sunny                  ← remove a ship
!ship-list                          ← view all ships and crews
!ship-captain @Luffy Sunny         ← set permanent captain (never reset)
!ship-uncaptain @Luffy             ← remove captain
!setup                             ← manually send panel (auto Tue/Fri 10:00)

```

**Permanent crew:**

```
!want Sunny                        ← request permanent spot (requires Mod approval)
!ship-addpermanent @user Sunny     ← add directly without approval (Mod/Admin)
!ship-removepermanent @user        ← remove from permanent crew (Mod/Admin)
!ship-listpermanent                 ← list all permanent crew members (Mod/Admin)

```

```
> [!NOTE]
> ### 💡 **Important Note on Permissions:**
> In order for your moderators to use ship admin commands and the fleet reset button **without needing full Discord Administrator permissions**, you must first register your server's moderator role using:
> `!setconfig mod_role <role-id>`
    > The role must have the following Discord permissions enabled
        > * View Channels
        > * Manage Roles
        > * Mention @everyone, @here, and All Roles
    > The bot will automatically recognize members with this role as authorized managers for the fleet on a per-server basis!

> 💡 When a user types `!want Sunny`, the bot sends a request to `crew_approval_channel` (or `admin_log_channel` if that isn't set) with **✅ Approve** / **❌ Deny** buttons. A Mod or Admin clicks the button and the user gets a DM with the result.

> ⚠️ **The `belly_rush_roles_channel` accepts commands only.** Any message that isn't a `!` command (e.g. `!want`, `!ship-captain`, `!ship-list`) is auto-deleted with a warning: *"this channel is only for ship selection commands"*.

> 📌 **Pinned instructions (edit-in-place, never repost):**
> `!post-roles-info` — posts the rules card in `belly_rush_roles_channel` *(Admin)*
> `!post-crew-info` — posts the ship-management/approval guide in `crew_approval_channel` (or `admin_log_channel` if that's not set) *(Admin)*
> Run either command again any time to **edit** the same message with fresh text — it never creates a duplicate post, and the original post date stays untouched.

> 📋 **Shipless member list (auto-updating, edit-in-place):**
> `!post-shipless-list` — posts the list once in `shipless_list_channel` *(Admin, needs `!setconfig shipless_list_channel <channel>` first)*
> Set `!setconfig belly_rush_role <role>` to only show members who actually play Belly Rush — otherwise every member without a ship shows up, including people who don't participate at all.
> After that it updates **automatically** — no command needed — every time a member gains or loses a ship role or the Belly Rush role (button, `!ship-captain`, `!ship-addpermanent`, or a manual role change), so the list always reflects reality.

> 🔓 **Belly Rush category unlock instructions (edit-in-place):**
> `!post-unlock-info` — posts the unlock steps card in `belly_rush_unlock_channel` *(Admin, needs `!setconfig belly_rush_unlock_channel <channel>` first)*
> Run it again any time to edit the same message — it never duplicates.

```

---

### 📊 Ship Status (HP / Fatigue)

Post a crew-status board for a ship — either manually or by letting AI read it off a screenshot. Same **edit-in-place** pattern as everything else: re-run for the same ship and it updates the existing message instead of posting a new one.

```
!shipstatus title:Sunny unit1:Mugiwara,100 unit2:Hosted,92 unit3:Akagami,33,Team 3 Fatigue -30%

```

```
!shipstatus-image [title]   ← attach 1-8 screenshots of the crew status

```

> 💡 `!shipstatus-image` sends the screenshot(s) to AI — attach more than one if the crew doesn't fit in a single screenshot, and it merges every unit into one combined list — then shows you a **preview with ✅ Confirm / ❌ Cancel buttons** — nothing is posted or overwritten until a Mod/Admin confirms it. If the AI misreads a name or a percentage, just hit Cancel and try `!shipstatus` manually or clearer screenshots.
> 🔒 Both commands require Mod/Admin (same as the other ship-admin commands, `mod_role` or Administrator).
> ⚙️ Bars are rendered as text (`█████░░░░░`) inside a normal embed — not a graphic image — so it needs no extra setup and always works on Railway.
> 📍 By default the status is posted in whichever channel you typed the command in. Set `!setconfig ship_status_channel <channel>` to always post/update in **one fixed channel** instead, no matter where the command is used.

---

### 📸 Bounty Auto-Detect (no command needed)

If `bounty_upload_channel` is configured, **anyone** who posts a bounty screenshot in that channel gets their bounty read by AI and updated automatically — no `!setbounty` typing needed. Works with all 3 common screenshot layouts (profile card, top HUD bar, personal info panel).

```
!setconfig bounty_upload_channel <channel-id>

```

> ⚠️ **No confirmation step, no permission check** — this is intentionally fully automatic and trusts whatever number the screenshot shows (by design, for fun/convenience). It's not spoof-proof — someone could in theory fake a screenshot. If you want a review step instead, ask to have it added.
> 🎖️ Posts the exact same "Bounty Update" embed as `!setbounty` — both share one design (`bountyEmbed.js`), including a before → after change line (e.g. "📈 +฿350,110,000") and a punchier title depending on whether the bounty went up, down, or is brand new — and assigns the same tier role.
> ⏱️ A 30-second per-user cooldown prevents accidental spam from hammering the AI — it's not a moderation feature.

---

### 🏴‍☠️ Belly Rush

**How to think about this system:** Belly Rush combines configuration, ship/crew data, role management, and approval workflows. Some commands are restricted to specific channels or moderator/admin roles.

**Typical flow:**

```text
Configure channels / roles
        ↓
Create ships
        ↓
Assign captains / crew
        ↓
Members use ship commands
        ↓
Bot updates roles & stored data
        ↓
Embeds / lists stay synchronized
```

### 🏴‍☠️ Belly Rush Blacklist

Names are stored as **plain text**, not Discord users — works even for people not in the server.

```
!black-list                              ← view the current blacklist (anyone)
!blacklist-add Luffy123 duplicate account  ← add a name (Admin)
!blacklist-add "Red Hair Shanks" scammer   ← use quotes for names with spaces (Admin)
!blacklist-remove Luffy123                 ← remove a name (Admin)

```

> 💡 If `blacklist_channel` is configured, the bot keeps **one** live embed message there and edits it on every add/remove instead of spamming new posts.

---

### 🎂 Birthday Messages

```
!setconfig bday_channel <id>   ← channel for the birthday message
!setconfig bday_user    <id>   ← Discord ID of the person having a birthday
!sendbday                      ← manually send the message right now (Admin)

```

> ⚠️ There's no auto-clear — the message is sent **every day at 08:30** (Sofia time) while `bday_user` stays set. Update or overwrite it after the birthday so it doesn't repeat.

---

### ⚙️ Repair Ship

Only in `repair_channel`. Only `repair @ship` is allowed.

```
!ship-addrepair Sunny {user} sails on fire!! 🔥   ← add a message
!ship-repairs Sunny                                ← list all with IDs
!ship-removerepair 1                               ← remove by ID
repair @Sunny                                      ← usage (any member)

```

---

### 💰 Bounty (Per-server)

```
!wanted / !wanted @user              ← Wanted poster
!setbounty @user 500000000           ← set bounty (Mod/Admin)
!resetbounty @user                   ← reset to ฿0 (Mod/Admin)

```

Every 50M crossed automatically assigns a tier role, named `Bounty: <N>M+` by
default (e.g. `Bounty: 250M+`). The role must already exist on the server
with that exact name, or the bot won't find it to assign.

If your server's roles use a different word instead of "Bounty" (e.g.
`RP: 250M+`), change the label with:

```
!setconfig bounty_role_label RP   ← roles become "RP: <N>M+" instead of "Bounty: <N>M+"

```

Defaults to `Bounty` if never set.

---

### 🤖 AI Chat — Password Activation

Disabled by default. Password provided only by the bot owner.

```
!ai-enable <password>   ← activate AI chat for THIS server
!ai-disable             ← disable (Admin only)

```

Once enabled, **@mention the bot** anywhere to chat with it!

```
@Bot what's the strongest Devil Fruit?   ← ask anything
@Bot tell me about the Grand Line        ← One Piece lore
@Bot yo what's up                        ← just vibe

```

> 💡 The bot responds **in character** as a One Piece pirate — in English.
> It remembers the last 10 messages per user during the session.

---

### ⚔️ Heroes (only in unit\_build\_channel)

```
!hero-list              ← all available heroes
!hero mihawk            ← full build guide
!hero luffy-cultiv1     ← Culti V1 variant

```

---

### ⏰ Reminders

```
!remind 0 21 * * * Raid!   ← every day at 21:00
!reminders                  ← your reminders
!allreminders               ← all reminders
!delete <id>                ← delete by ID
!cron                       ← cron format guide

```

---

### 🛂 New Member Verification

**Typical verification flow:**

```text
NEW MEMBER
    ↓
Rookie role
    ↓
Enters nickname with guild tag
    ↓
Player role
    ↓
Full server access
```

### 🛂 New Member Verification

1. New user joins → **Rookie** role (automatic)
2. Clicks **"Nickname"** → enters nickname with guild tag
3. Gets **Player** role and full server access

---

### 🧹 Moderation

```
!clear 50                  ← delete last 50 messages
!say Ahoy!                 ← bot sends the message (command deleted)
!sendto #channel Ahoy!     ← send to a specific channel
!addrole @user Role        ← give a role
!removerole @user Role     ← remove a role
!addroleallts @role        ← give role to everyone with ᐪˢ☠️
!addroleallgm @role        ← give role to everyone with ᴳᴹ☠️

```

---

### 💬 Automatic Reactions

```
good night / nighty night  ← bot replies with a good night GIF
good morning / добро утро  ← bot replies with a random good morning GIF

```

---

### 🛡️ Link / Phishing Protection (Automatic)

**Typical flow:**

```text
Message containing a link
          ↓
       Bot scans
          ↓
   ┌──────┴──────┐
   ↓             ↓
   Safe       Malicious
   ↓             ↓
Keep/repost   Delete + warn
                 ↓
             Admin log
```

### 🛡️ Link / Phishing Protection (Automatic)

Always on — no setup needed.

- Every message containing a link is scanned via the VirusTotal API.
- **Safe links** are kept (re-posted via webhook under the user's name).
- **Malicious / phishing links** are deleted instantly and the user is warned.
- Threat alerts are logged to `admin_log_channel`.

> ⚠️ Note: detection relies on:

- VirusTotal
- MetaDefender
- Jotti's Malware
- Kaspersky Threat Intelligence Portal.

> Detection depends on the configured scanning services and their existing databases, so brand-new domains may pass. For specific domains you always want
> blocked, add them to a local denylist.
> The configured scanning services require their corresponding API configuration in `.env`. If the required configuration is missing, link scanning may not work as intended.

---

### 🗑️ Moderation Logging (Automatic)

Logged to `admin_log_channel`.

- **Deleted messages** — author, who deleted it (via Audit Log), channel, content, attachments, original timestamp.
- **Bulk deletes** — a `.txt` file with all deleted messages + who did it.
- **Bans & timeouts** — responsible mod, target, reason, duration.

> 💡 The bot needs the **View Audit Log** permission to detect *who* deleted a message. Self-deletes create no audit entry (Discord limitation), so they show as "self / unknown".

---

## 🛠️ Troubleshooting / Отстраняване на проблеми

### Bot does not respond
1. Check that the bot can **View Channel**, **Send Messages**, and **Read Message History**.
2. Check the channel restriction for that feature.
3. Run `!checkconfig`.
4. Check `admin_log_channel` for errors or system messages.

### A command says the channel is wrong
Some systems intentionally allow commands only in their configured channel, such as:
- `repair_channel`
- `unit_build_channel`
- `belly_rush_roles_channel`

Move the command to the correct channel instead of changing permissions unnecessarily.

### A role is not assigned
Check:
- the role exists;
- the bot's role is high enough in the Discord role hierarchy;
- the configured role ID/name is correct;
- the bot has **Manage Roles**.

### An automatic feature does nothing
Check:
- the feature's required channel is configured;
- the bot can read messages and attachments there;
- required API/AI configuration is present;
- the event matches the feature's documented trigger;
- cooldowns or other limits have not been reached.

### Bounty tier role is missing
The role must exist with the expected name, or with the configured `bounty_role_label`.

Example:

```text
Bounty: 250M+
```

or, if configured:

```text
RP: 250M+
```

### AI screenshot result is wrong
Use a clearer screenshot and follow the documented confirmation step where available. Remember that screenshot recognition is not guaranteed to be perfect.

### Where should an administrator look first?

```text
Problem
  ↓
!checkconfig
  ↓
Discord permissions
  ↓
Correct channel
  ↓
Correct role hierarchy
  ↓
API / AI configuration
  ↓
admin_log_channel
```

---

## 🇧🇬 БЪЛГАРСКИ

### 🚀 Първи стъпки — Настройка на нов сървър

**1. Включи Developer Mode**
Settings → Advanced → Developer Mode → десен клик на канал/роля → **Copy ID**

**2. Пълна конфигурация (само Админ):**

```
!setconfig level_up_channel         <id>  ← канал за level-up съобщения
!setconfig log_channel              <id>  ← канал за XP логове
!setconfig stats_channel            <id>  ← канал за !top класация
!setconfig admin_log_channel        <id>  ← канал за модерация логове + crew одобрения
!setconfig welcome_channel          <id>  ← канал за нови членове
!setconfig belly_rush_channel       <id>  ← канал за Belly Rush панела
!setconfig crew_approval_channel    <id>  ← канал за одобрения на постоянен екипаж (опционален)
!setconfig belly_rush_roles_channel <id>  ← канал само за ship команди (!want, !ship-captain и т.н. — всичко друго се трие автоматично)
!setconfig reminders_channel        <id>  ← канал за напомняния
!setconfig repair_channel           <id>  ← канал за repair-ship команди
!setconfig translator_channel       <id>  ← канал за двупосочен AI превод
!setconfig bot_status_channel       <id>  ← канал за Online/Offline статус
!setconfig bot_info_channel         <id>  ← канал за мануала с командите
!setconfig unit_build_channel       <id>  ← канал за !hero команди
!setconfig bounty_channel           <id>  ← канал за !wanted плакати
!setconfig rules_channel            <id>  ← канал с правилата (за welcome)
!setconfig general_channel          <id>  ← general chat (за welcome)
!setconfig rookies_role             <id>  ← роля за нови членове (авт. се създава)
!setconfig player_role              <id>  ← роля след верификация (авт. се създава)
!setconfig mod_role                 <id>  ← роля за модератори
!setconfig restricted_channel       <id>  ← канал с ограничения за менции
!setconfig protected_users     <id1,id2>  ← защитени потребители (ID-та с ,)
!setconfig bday_channel             <id>  ← канал за birthday (опционален)
!setconfig bday_user                <id>  ← user ID за birthday (опционален)
!setconfig blacklist_channel        <id>  ← канал за живото blacklist embed (опционален)
!setconfig shipless_list_channel    <id>  ← канал за авто-обновяващия се списък с членове без кораб (опционален)
!setconfig ship_status_channel      <id>  ← канал, в който !shipstatus винаги постира, независимо къде е писана командата (опционален)
!setconfig bounty_upload_channel    <id>  ← канал, в който всеки скрийншот автоматично обновява bounty, без нужда от команда (опционален)

```

**3. Провери какво липсва:**

```
!checkconfig   ← конфигурирано ✅, липсващо ❌, статус на системите 🟢/🔴
!getconfig     ← всички текущи стойности

```

> 💡 **Rookie** и **Player** ролите се създават автоматично!

---

### 🎖️ Leveling & XP — Активиране с парола

Изключен по подразбиране. Паролата се дава само от собственика на бота.

```
!leveling-enable <парола>   ← активира XP за ТОЗИ сървър
!leveling-disable           ← спира (само Админ)

!rank       ← ниво и прогрес бар (изчезва след 60 сек)
!top        ← Топ 10 най-активни (само Админ)
!sync       ← ръчно запазване (само Админ)

```

---

### 🌐 Преводни системи — Активиране с парола

#### 1. Флаг реакция превод

Реагираш с флаг → превод в канала, изчезва след 2 мин.

```
!translate-enable <парола>   ← активира за ТОЗИ сървър
!translate-disable           ← спира (само Админ)

```

Поддържа 50+ езика. Работи в **всички канали**.

#### 2. Авто-превод на не-английски съобщения

Не-английско съобщение → превод на английски под него. **Не изчезва.**

```
!auto-translate-enable <парола>   ← активира за ТОЗИ сървър
!auto-translate-disable           ← спира (само Админ)

```

Работи в **всички канали** освен `#ai-translator` и admin канали, плюс всеки
канал, добавен в списъка с игнорирани канали по-долу.
Игнорира: команди с `!`, много кратки съобщения, предимно латински текст.

**Допълнителни игнорирани канали (само Админ):**

```
!ignoretranslate-add <#канал>      ← спира авто-превода в този канал
!ignoretranslate-remove <#канал>   ← връща авто-превода в този канал
!ignoretranslate-list              ← показва допълнителните игнорирани канали

```

#### 3. AI Канален преводач (#translator\_channel)

За разговор между хора на различни езици.

- Пишеш на **всякакъв език** → превод на английски
- Отговаряш на английски → превод обратно на езика му
- Помни езика 5 часа | Cooldown: 5 сек

---

### ⚔️ Mania — Настройка и употреба

```
!mania-addguild ts @ThousandSunny #mania-strategy #general
!mania-guilds              ← показва всички гилдии
!mania-removeguild ts      ← маха гилдия

mania-plan ts / all        ← стартира план с ✅ ❌ ⏳
mania-list ts              ← показва гласувалите, пингва липсващите
mania-dm ts                ← DM на незагласувалите

mania-strategy
Kronos - @Luffy @Zoro      ← всеки ред = един бос
Hydra - @Nami @Sanji

```

---

### 🚢 Belly Rush — Кораби и екипаж

**Управление на кораби (Админ):**

```
!ship-add Sunny ☀️ @mugi-role      ← добавя кораб
!ship-remove Sunny                  ← маха кораб
!ship-list                          ← всички кораби и екипажи
!ship-captain @Luffy Sunny         ← постоянен капитан (не се ресетва)
!ship-uncaptain @Luffy             ← маха капитан
!setup                             ← изпраща панела веднага (авт. Вт/Пт 10:00)

```

**Постоянен екипаж:**

```
!want Sunny                        ← заявява постоянно място (изисква одобрение от Мод)
!ship-addpermanent @user Sunny     ← директно добавя без одобрение (Мод/Админ)
!ship-removepermanent @user        ← маха от постоянен екипаж (Мод/Админ)
!ship-listpermanent                 ← показва всички постоянни членове (Мод/Админ)

```

```
> 💡 **Важно за правата на Модераторите:**
> За да могат вашите модератори да използват корабните команди и бутона за ресет **без да имат реални Администраторски права в Discord**, задължително трябва първо да настроите модераторската роля  за сървъра чрез командата:
> `!setconfig mod_role <ID-на-ролята>`
    > Като ролята трябва да има следните права в Discord
        > * Преглед на канали.
        > * Управление на роли.
        > * С позовавания @EVERYONE, @HERE и Всички роли.
    > Ботът автоматично ще разпознае притежателите на тази роля като оторизирани лица за управление на флота per-сървър!

> 💡 Когато потребител напише `!want Sunny`, ботът изпраща заявка в `crew_approval_channel` (или в `admin_log_channel`, ако той не е зададен) с бутони **✅ Approve** / **❌ Deny**. Мод или Админ натиска бутон и потребителят получава ЛС с резултата.

**🔄 Crew Approval Flow:**

```text
USER
  │
  └── !want Sunny
          ↓
Crew Approval Channel
          ↓
   ┌───────────────┐
   │ ✅ Approve    │
   │ ❌ Deny       │
   └───────────────┘
       ↓       ↓
   APPROVED   DENIED
       ↓       ↓
  Crew Role     DM
       │
       └──────→ DM result
```

> ⚠️ **Каналът `belly_rush_roles_channel` приема само команди.** Всяко съобщение, което не е `!` команда (напр. `!want`, `!ship-captain`, `!ship-list`), се трие автоматично с предупреждение: *"this channel is only for ship selection commands"*.

> 📌 **Постоянни инструкции (редактират се на място, не се препращат наново):**
> `!post-roles-info` — праща/обновява правилата в `belly_rush_roles_channel` *(Админ)*
> `!post-crew-info` — праща/обновява гайда за управление на кораби + одобрения в `crew_approval_channel` (или `admin_log_channel`, ако не е зададен) *(Админ)*
> Пускаш командата пак по всяко време, за да **редактираш** същото съобщение с нов текст — никога не създава дубликат, а датата на оригиналния пост остава непроменена.

> 📋 **Списък с членове без кораб (авто-обновяващ се, редактира се на място):**
> `!post-shipless-list` — постван веднъж в `shipless_list_channel` *(Админ, нужен е първо `!setconfig shipless_list_channel <channel>`)*
> Задай `!setconfig belly_rush_role <role>`, за да се показват само хора, които реално играят Belly Rush — иначе излиза всеки член без кораб, включително хора, които изобщо не участват.
> След това се обновява **автоматично** — без команда — всеки път когато член получи или загуби ship роля или Belly Rush ролята (бутон, `!ship-captain`, `!ship-addpermanent`, или ръчна промяна на роля), така че списъкът винаги отразява реалността.

> 🔓 **Инструкции за отключване на Belly Rush категорията (редактира се на място):**
> `!post-unlock-info` — праща картата с инструкции в `belly_rush_unlock_channel` *(Админ, нужен е първо `!setconfig belly_rush_unlock_channel <channel>`)*
> Пускаш командата пак по всяко време, за да редактираш същото съобщение — никога не се дублира.

```

---

### 📊 Ship Status (HP / Fatigue)

Постваш статус табло за екипажа на кораб — ръчно или чрез AI, което го разчита от скрийншот. Работи по същия **edit-in-place** принцип — пускаш пак командата за същия кораб и тя редактира съществуващото съобщение, вместо да постне ново.

```
!shipstatus title:Sunny unit1:Mugiwara,100 unit2:Hosted,92 unit3:Akagami,33,Team 3 Fatigue -30%

```

```
!shipstatus-image [title]   ← прикачи 1-8 скрийншота от статуса на екипажа

```

> 💡 `!shipstatus-image` праща скрийншота(ите) на AI — прикачи повече от един, ако екипажът не се събира в един скрийншот, и то ги обединява в един общ списък — после ти показва **preview с ✅ Confirm / ❌ Cancel бутони** — нищо не се поства или презаписва, докато Мод/Админ не потвърди.

**🔄 AI Screenshot Flow:**

```text
1–8 SCREENSHOTS
       ↓
      AI
       ↓
Reads names / HP / Fatigue
       ↓
   PREVIEW
   ↙     ↘
Confirm   Cancel
   ↓         ↓
Update     Nothing changes
status
``` Ако AI-то сгреши име или процент, просто натисни Cancel и пробвай `!shipstatus` ръчно или по-ясни скрийншоти.
> 🔒 И двете команди изискват Мод/Админ (както другите ship-admin команди — `mod_role` или Administrator).
> ⚙️ Баровете се рендират като текст (`█████░░░░░`) в обикновен embed, не като графична картинка — затова не иска допълнителна настройка и винаги работи на Railway.
> 📍 По подразбиране статусът се постира в канала, в който е писана командата. Задай `!setconfig ship_status_channel <channel>`, за да постира/обновява винаги в **един фиксиран канал**, независимо откъде е пусната командата.

---

### 📸 Bounty Auto-Detect (без команда)

Ако е конфигуриран `bounty_upload_channel`, **всеки**, който постне bounty скрийншот в този канал, автоматично получава прочетено от AI и обновено bounty — без изобщо да пише `!setbounty`. Работи и с трите чести варианта на скрийншот (профилна карта, горен HUD бар, лична информация панел).

```
!setconfig bounty_upload_channel <channel-id>

```

> ⚠️ **Няма стъпка за потвърждение, няма проверка на права** — това е нарочно напълно автоматично и вярва на каквото число показва скрийншотът (по дизайн, за забавление/удобство). Не е защитено от фалшифициране — теоретично някой може да редактира снимка. Ако искаш вместо това стъпка за преглед, кажи да я добавим.
> 🎖️ Постира точно същия "Bounty Update" embed като `!setbounty` — и двата споделят един дизайн (`bountyEmbed.js`), включително ред с промяната преди → сега (напр. "📈 +฿350,110,000") и по-драматично заглавие според това дали bounty-то се е вдигнало, спаднало, или е първото за човека — и дава същата tier роля.
> ⏱️ 30-секунден cooldown на потребител предпазва от случаен спам към AI-то — не е модераторска мярка.

---

### 🏴‍☠️ Belly Rush Blacklist

Имената се пазят като **обикновен текст**, не Discord потребители — работи дори за хора, които не са в сървъра.

```
!black-list                              ← показва текущия blacklist (всеки)
!blacklist-add Luffy123 duplicate account  ← добавя име (Админ)
!blacklist-add "Red Hair Shanks" scammer   ← кавички за имена с интервали (Админ)
!blacklist-remove Luffy123                 ← маха име (Админ)

```

> 💡 Ако е зададен `blacklist_channel`, ботът пази **едно** живо embed съобщение там и го edit-ва при всяко добавяне/махане, вместо да спамва нови постове.

---

### 🎂 Birthday съобщения

```
!setconfig bday_channel <id>   ← канал за birthday съобщението
!setconfig bday_user    <id>   ← Discord ID на рождника
!sendbday                      ← изпраща съобщението веднага ръчно (Админ)

```

> ⚠️ Няма авто-изчистване — съобщението се изпраща **всеки ден в 08:30** (София час), докато `bday_user` е зададен. Обнови/презапиши го след рождения ден, за да не се повтаря.

---

### ⚙️ Repair Ship

Само в `repair_channel`. Само `repair @ship` е разрешено.

```
!ship-addrepair Sunny {user} sails on fire!! 🔥   ← добавя съобщение
!ship-repairs Sunny                                ← показва всички с ID-та
!ship-removerepair 1                               ← маха по ID
repair @Sunny                                      ← използване (от всеки)

```

---

### 💰 Bounty (Per-сървър)

```
!wanted / !wanted @user              ← Wanted плакат
!setbounty @user 500000000           ← задава bounty (Мод/Админ)
!resetbounty @user                   ← нулира до ฿0 (Мод/Админ)

```

При всеки 50M bounty автоматично се дава tier роля, наречена по подразбиране
`Bounty: <N>M+` (напр. `Bounty: 250M+`). Ролята трябва вече да съществува на
сървъра с точно това име, иначе ботът няма да я намери, за да я даде.

Ако ролите на твоя сървър използват друга дума вместо "Bounty" (напр.
`RP: 250M+`), смени думата с:

```
!setconfig bounty_role_label RP   ← ролите стават "RP: <N>M+" вместо "Bounty: <N>M+"

```

По подразбиране е `Bounty`, ако никога не е задавано.

---

### 🤖 AI Чат — Активиране с парола

Изключен по подразбиране. Паролата се дава само от собственика на бота.

```
!ai-enable <парола>   ← активира AI чата за ТОЗИ сървър
!ai-disable           ← спира (само Админ)

```

След активиране, **тагни бота** навсякъде за да чатиш с него!

```
@Бот what's the strongest Devil Fruit?   ← питай каквото искаш
@Бот tell me about the Grand Line        ← One Piece лор
@Бот yo what's up                        ← просто си говори

```

> 💡 Ботът отговаря **в роля** на One Piece пират — на английски.
> Помни последните 10 съобщения на всеки потребител по време на сесията.

---

### ⚔️ Герои (само в unit\_build\_channel)

```
!hero-list              ← всички герои
!hero mihawk            ← пълен билд
!hero luffy-cultiv1     ← Culti V1 вариант

```

---

### ⏰ Напомняния

```
!remind 0 21 * * * Raid!   ← всеки ден в 21:00
!reminders                  ← твоите напомняния
!allreminders               ← всички напомняния
!delete <id>                ← изтрива по ID
!cron                       ← наръчник за cron формата

```

---

### 🛂 Верификация

1. Нов потребител → **Rookie** роля (автоматично)
2. Натиска **"Nickname"** → въвежда nickname с гилдиен таг
3. Получава **Player** роля и достъп

**🔄 Flow:**

```text
NEW MEMBER
    ↓
Rookie Role
    ↓
Clicks "Nickname"
    ↓
Enters nickname with guild tag
    ↓
Player Role
    ↓
Full Server Access
```

---

### 🧹 Модерация

```
!clear 50                  ← трие последните 50 съобщения
!say Ahoy!                 ← ботът изпраща (командата се трие)
!sendto #канал Ahoy!       ← изпраща в конкретен канал
!addrole @user Роля        ← дава роля
!removerole @user Роля     ← маха роля
!addroleallts @роля        ← дава роля на всички с ᐪˢ☠️
!addroleallgm @роля        ← дава роля на всички с ᴳᴹ☠️

```

---

### 💬 Автоматични реакции

```
good night / nighty night  ← лека нощ GIF
good morning / добро утро  ← добро утро GIF

```

---

### 🛡️ Защита от линкове / фишинг (автоматична)

Винаги включена — без настройка.

- Всяко съобщение с линк се проверява през VirusTotal API.
- **Безопасните линкове** остават (препращат се през webhook от името на потребителя).
- **Зловредните / фишинг линкове** се трият веднага и потребителят се предупреждава.
- Заплахите се логват в `admin_log_channel`.

> ⚠️ Засичането разчита на базата на VirusTotal, така че съвсем нови домейни, които още не е виждал, може да минат. За конкретни домейни, които винаги искаш блокирани, се добавя локална денлиста.
> Изисква `VIRUSTOTAL_API_KEY` в `.env` (без него всички линкове минават).

---

### 🗑️ Логване на модерация (автоматично)

Логва се в `admin_log_channel`.

- **Изтрити съобщения** — автор, кой го е изтрил (през Audit Log), канал, съдържание, прикачени файлове, време на пращане.
- **Масово триене** — `.txt` файл с всички изтрити съобщения + кой го е направил.
- **Банове и тайм-аути** — отговорен модератор, цел, причина, продължителност.

> 💡 Ботът трябва да има право **View Audit Log**, за да засича *кой* е изтрил съобщение. При самостоятелно триене Discord не прави запис, така че се показва „сам / неизвестно".

---

---

---

> 📌 **Важно / Important:**
> Всичко е **per-сървър** и напълно независимо.
> Everything is **per-server** and fully independent.
>
> 🔐 **Leveling, Flag Translate, Auto-Translate и AI Chat** се активират с парола от собственика на бота.
>
> 🔐 **Leveling, Flag Translate, Auto-Translate and AI Chat** are activated with a password from the bot owner.


## 📚 Command Reference

Use the detailed sections above for full explanations. This list is a quick lookup of the bot's command families.

| Command family | Purpose |
|---|---|
| `!setconfig` / `!checkconfig` / `!getconfig` | Server configuration |
| `!leveling-*` / `!rank` / `!top` / `!sync` | Leveling & XP |
| `!mania-*` | Mania tools |
| `!ship-*` / `!setup` / `!want` | Belly Rush |
| `!shipstatus*` | Ship status |
| `!blacklist-*` / `!black-list` | Belly Rush blacklist |
| `!wanted` / `!setbounty` / `!resetbounty` | Bounty |
| `!ai-enable` / `!ai-disable` | AI chat |
| `!hero*` | Hero builds |
| `!remind` / `!reminders` / `!allreminders` / `!delete` | Reminders |
| `!clear` / `!say` / `!sendto` / `!addrole` / `!removerole` | Moderation |
| `!sendbday` | Birthday message |
| `!ship-addrepair` / `!ship-repairs` / `!ship-removerepair` | Repair Ship |

> 💡 **Rule of thumb:** If you are unsure whether a command is allowed for you or where it should be used, open the relevant feature section above first. It explains the permissions, channel restrictions, and automatic behavior.

---

