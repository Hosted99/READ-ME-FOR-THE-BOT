# 🛡️ Admin Commands — Quick Reference

For administrators and moderators only. Commands are typed in a server channel; the bot deletes your message.

- 🔴 = **Administrator** only
- 🟠 = **Administrator or `mod_role`** (moderators can use it too)
- 🔐 = needs the password from the bot owner

---

## ⚙️ Server Setup

| Command | What it does |
|---|---|
| 🔴 `!setconfig <key> <id>` | Sets a channel, role or other setting. Example: `!setconfig mod_role 123456789` |
| 🔴 `!unsetconfig <key>` | Deletes one setting |
| 🔴 `!getconfig` | Shows all current values |
| 🔴 `!checkconfig` | Shows what is configured ✅, what is missing ❌, and which systems are ON 🟢 / OFF 🔴 |
| 🔴 `!neon-status` | Shows what woke the database last |

Important `!setconfig` keys: `mod_role`, `admin_log_channel`, `welcome_channel`, `rules_channel`, `general_channel`, `rookies_role`, `player_role`, `bounty_channel`, `bounty_upload_channel`, `reminders_channel`, `translator_channel`, `repair_channel`, `belly_rush_channel`, `belly_rush_roles_channel`, `crew_approval_channel`, `ship_status_channel`, `blacklist_channel`, `shipless_list_channel`, `unit_build_channel`, `bday_channel`, `bday_user`. The full list is in the README.

---

## 🔌 Turning Systems On / Off

| Command | What it does | Default |
|---|---|---|
| 🔴🔐 `!leveling-enable <password>` / 🔴 `!leveling-disable` | XP and levels | OFF |
| 🔴🔐 `!translate-enable <password>` / 🔴 `!translate-disable` | Flag reaction translation | OFF |
| 🔴🔐 `!auto-translate-enable <password>` / 🔴 `!auto-translate-disable` | Automatic translation of non-English messages | OFF |
| 🔴🔐 `!ai-enable <password>` / 🔴 `!ai-disable` | AI chat | OFF |
| 🔴 `!ship-enable` / `!ship-disable` | The whole ship system | **ON** |
| 🔴 `!linkscan-enable` / `!linkscan-disable` / `!linkscan-status` | VirusTotal link scanner | **ON** |
| 🔴 `!everyoneguard-enable` / `!everyoneguard-disable` | @everyone scam guard | OFF |
| 🔴 `!everyoneguard-ai-enable` / `!everyoneguard-ai-disable` | AI check of images in @everyone messages | OFF |
| 🔴 `!everyoneguard-status` | Guard state and whether the bot has the needed permissions | — |
| 🔴 `!weeklytop-enable` / `!weeklytop-disable` | Weekly bounty Top 10 + posters + Top 3 roles (Mondays 02:00 Sofia) | OFF |
| 🔴 `!ignoretranslate-add #channel` / `-remove #channel` / `-list` | Channels where auto-translate stays silent | — |

---

## 🏆 Weekly Bounty Top

| Command | What it does |
|---|---|
| 🔴 `!weeklytop-channel #channel` | Where the Top 10 and posters are posted (default: `bounty_channel`) |
| 🔴 `!powerranks-enable` / `!powerranks-disable` | Power ranking roles by bounty (Rookie Pirate … Pirate King, given next to the "Bounty: XM+" role) | OFF |
| 🔴 `!powerranks-sync` | Ranks everyone who already has a bounty (run once after enabling) |
| 🔴 `!powerranks-status` | Shows whether it is on and the full ladder |
| 🔴 `!weeklytop-boards [@EuropeRole @GlobalRole \| off]` | Splits the Top 10 into **Europe** and **Global** boards by role (creates the roles if none given). Each board gets its own Top 10, posters and Top 3 roles |
| 🔴 `!weeklytop-channel-global #channel` | Separate channel for the Global board (optional) |
| 🔴 `!weeklytop-picker [#channel]` | Posts the "choose ONE leaderboard" buttons (members can't be in both) |
| 🔴 `!weeklytop-preview` | Posts it right now without changing roles (for testing) |
| 🔴 `!weeklytop-now` | Runs the full job right now (posts + changes the Top 1/2/3 roles) |
| 🔴 `!weeklytop-status` | Shows settings and whether posters are available |

---

## 📣 Event Reminders

| Command | What it does |
|---|---|
| 🔴 `!events-enable` / `!events-disable` | Embed reminders for events (OFF by default) |
| 🔴 `!events-version main\|global\|both` | Which game version this server follows (default `main` = Europe/London; `global` = game clock GMT-4) |
| 🔴 `!events-channel #channel` / `!events-channel-global #channel` | The Events channel (and an optional separate one for the global version) |
| 🔴 `!events-role @role` / `!events-role-global @role` | Role to ping (leave empty to clear; the global one falls back to the main role) |
| 🔴 `!events-board [#channel]` | Posts the self-updating schedule board(s). With a `#channel` they all go there (e.g. a `#schedule` channel) |
| 🔴 `!events-test <event>` | Plays 30 min → live → ended right now, no pings (add `-global` for the global version, e.g. `mania-global`) |
| 🔴 `!events-list` | Event keys and the current status |

---

## 🎭 Roles

| Command | What it does |
|---|---|
| 🔴 `!panel-lang [#channel]` | Language buttons panel (roles are created on first press) |
| 🔴 `!panel-colors [#channel]` | Colour dropdown, pick one colour (roles are created on first pick) |
| 🔴 `!panel-custom <buttons\|menu\|menu-single> Title \| Description @role @role [#channel]` | Panel from roles you already have |
| 🔴 `!role-create <name> [#hex]` | Creates a role with no permissions |
| 🔴 `!role-give @role @user @user` | Gives a role to specific members |
| 🔴 `!role-take @role @user @user` | Removes a role from specific members |
| 🔴 `!role-bulk @role all` | Gives a role to every human member (asks to confirm) |
| 🔴 `!role-bulk @role @otherRole` | Gives a role to everyone who has the other role |
| 🔴 `!role-bulk-remove @role` | Removes a role from everyone who has it |
| 🔴 `!rolepanel-help` | Short help |
| 🟠 `!addrole @user Role` / `!removerole @user Role` | Gives or removes a role |
| 🟠 `!addroleallts @role` / `!addroleallgm @role` | Gives a role to everyone with ᐪˢ☠️ / ᴳᴹ☠️ in their name |

Do not rename the roles created by `!panel-lang` and `!panel-colors` — the panels find them by name.

---

## 🚢 Ships (Belly Rush)

| Command | What it does |
|---|---|
| 🟠 `!ship-add "Name" 🚢 @role` | Adds a ship |
| 🟠 `!ship-remove <name>` | Removes a ship |
| 🟠 `!ship-captain @user <ship>` / `!ship-uncaptain @user` | Permanent captain |
| 🟠 `!ship-addpermanent @user <ship>` / `!ship-removepermanent @user` | Permanent crew without approval |
| 🟠 `!ship-listpermanent` | Lists permanent crew |
| 🟠 `!ship-addrepair <ship> text with {user}` / `!ship-repairs <ship>` / `!ship-removerepair <id>` | Messages for the repair channel |
| 🟠 `!shipstatus ...` / `!shipstatus-image` | Crew status (HP / fatigue) |
| 🔴 `!setup` | Sends the panel manually (otherwise it posts Tue and Fri at 10:00) |
| 🔴 `!post-roles-info` / `!post-crew-info` / `!post-shipless-list` / `!post-unlock-info` | Posts the info cards |
| 🔴 `!blacklist-add <name> [reason]` / `!blacklist-remove <name>` / `!blacklist-refresh` | Belly Rush blacklist |

---

## 💰 Bounty

| Command | What it does |
|---|---|
| 🟠 `!setbounty @user <amount>` | Sets a bounty |
| 🟠 `!resetbounty @user` | Resets a bounty to ฿0 |

---

## 🧹 Moderation & Messages

| Command | What it does |
|---|---|
| 🟠 `!clear <count>` | Deletes the last messages (needs Manage Messages or Administrator) |
| 🔴 `!say <text>` | The bot sends a message |
| 🔴 `!sendto #channel <text>` | The bot sends a message to another channel |
| 🔴 `!sendbday` | Sends the birthday message right now |
| 🔴 `!delete <id>` | Deletes a reminder by ID |
| 🔴 `!maintenance` | Maintenance mode |

---

## 📊 Leveling & Mania

| Command | What it does |
|---|---|
| 🔴 `!top` | Top 10 most active members |
| 🔴 `!sync` | Saves XP to the database right now |
| 🔴 `!mania-addguild <code> @role #channel #channel` | Adds a guild for Mania |
| 🔴 `!mania-guilds` / `!mania-removeguild <code>` | List and remove guilds |

---

## 🤖 Automatic Things Admins Get Notified About

- **@everyone scam:** the bot deletes the message, times the author out for 24 hours, and messages all admins and `admin_log_channel`.
- **Permanent ship request (`!want`):** goes to `crew_approval_channel` (or `admin_log_channel`) with Approve / Deny buttons.
- **Deleted messages, bans, timeouts:** logged in `admin_log_channel`.

---

## 💡 Permissions the Bot Needs

Manage Roles (roles), Manage Messages (cleanup, @everyone guard), Moderate Members (timeouts), View Audit Log (who deleted a message). The bot's role must be **above** every role it manages.
