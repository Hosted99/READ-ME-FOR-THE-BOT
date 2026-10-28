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
| 🔴 `!ignoretranslate-add #channel` / `-remove #channel` / `-list` | Channels where auto-translate stays silent | — |

---

## 🎭 Roles

| Command | What it does |
|---|---|
| 🔴 `!panel-lang [#channel]` | Language buttons panel (roles are created on first press) |
| 🔴 `!panel-colors [#channel]` | Colour dropdown, pick one colour (roles are created on first pick) |
| 🔴 `!panel-custom <buttons\|menu\|menu-single> Title @role @role [#channel]` | Panel from roles you already have |
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

# 🛡️ Админ команди — бърза справка

Само за администратори и модератори. Командите се пишат в чата на сървъра; ботът изтрива съобщението ти.

- 🔴 = само **Administrator**
- 🟠 = **Administrator или `mod_role`** (модераторите също могат)
- 🔐 = иска парола от собственика на бота

---

## ⚙️ Настройка на сървъра

| Команда | Какво прави |
|---|---|
| 🔴 `!setconfig <ключ> <id>` | Задава канал, роля или друга настройка. Пример: `!setconfig mod_role 123456789` |
| 🔴 `!unsetconfig <ключ>` | Изтрива една настройка |
| 🔴 `!getconfig` | Показва всички текущи стойности |
| 🔴 `!checkconfig` | Показва какво е настроено ✅, какво липсва ❌ и кои системи са включени 🟢/🔴 |
| 🔴 `!neon-status` | Показва кое е събудило базата последно |

Важни ключове за `!setconfig`: `mod_role`, `admin_log_channel`, `welcome_channel`, `rules_channel`, `general_channel`, `rookies_role`, `player_role`, `bounty_channel`, `bounty_upload_channel`, `reminders_channel`, `translator_channel`, `repair_channel`, `belly_rush_channel`, `belly_rush_roles_channel`, `crew_approval_channel`, `ship_status_channel`, `blacklist_channel`, `shipless_list_channel`, `unit_build_channel`, `bday_channel`, `bday_user`. Пълният списък е в README.

---

## 🔌 Включване и изключване на системи

| Команда | Какво прави | По подразбиране |
|---|---|---|
| 🔴🔐 `!leveling-enable <парола>` / 🔴 `!leveling-disable` | XP и нива | изключено |
| 🔴🔐 `!translate-enable <парола>` / 🔴 `!translate-disable` | Превод с флаг реакция | изключено |
| 🔴🔐 `!auto-translate-enable <парола>` / 🔴 `!auto-translate-disable` | Автоматичен превод на не-английски съобщения | изключено |
| 🔴🔐 `!ai-enable <парола>` / 🔴 `!ai-disable` | AI чат | изключено |
| 🔴 `!ship-enable` / `!ship-disable` | Цялата система с кораби | **включена** |
| 🔴 `!linkscan-enable` / `!linkscan-disable` / `!linkscan-status` | Проверка на линкове с VirusTotal | **включена** |
| 🔴 `!everyoneguard-enable` / `!everyoneguard-disable` | Защита срещу скам с @everyone | изключена |
| 🔴 `!everyoneguard-ai-enable` / `!everyoneguard-ai-disable` | AI проверка на снимки при @everyone | изключена |
| 🔴 `!everyoneguard-status` | Състояние на защитата и дали ботът има нужните права | — |
| 🔴 `!ignoretranslate-add #канал` / `-remove #канал` / `-list` | Канали, в които авто-преводът мълчи | — |

---

## 🎭 Роли

| Команда | Какво прави |
|---|---|
| 🔴 `!panel-lang [#канал]` | Панел с бутони за езици (ролите се създават при първото натискане) |
| 🔴 `!panel-colors [#канал]` | Меню за избор на един цвят (ролите се създават при първия избор) |
| 🔴 `!panel-custom <buttons\|menu\|menu-single> Заглавие @роля @роля [#канал]` | Панел от роли, които вече имаш |
| 🔴 `!role-create <име> [#hex]` | Създава роля без права |
| 🔴 `!role-give @роля @user @user` | Дава роля на конкретни хора |
| 🔴 `!role-take @роля @user @user` | Маха роля от конкретни хора |
| 🔴 `!role-bulk @роля all` | Дава роля на всички хора (с потвърждение) |
| 🔴 `!role-bulk @роля @другаРоля` | Дава роля на всички, които имат другата роля |
| 🔴 `!role-bulk-remove @роля` | Маха роля от всички, които я имат |
| 🔴 `!rolepanel-help` | Кратка помощ |
| 🟠 `!addrole @user Роля` / `!removerole @user Роля` | Дава или маха роля |
| 🟠 `!addroleallts @роля` / `!addroleallgm @роля` | Дава роля на всички с ᐪˢ☠️ / ᴳᴹ☠️ в името |

Не преименувай ролите от `!panel-lang` и `!panel-colors` — панелите ги търсят по име.

---

## 🚢 Кораби (Belly Rush)

| Команда | Какво прави |
|---|---|
| 🟠 `!ship-add "Име" 🚢 @роля` | Добавя кораб |
| 🟠 `!ship-remove <име>` | Маха кораб |
| 🟠 `!ship-captain @user <кораб>` / `!ship-uncaptain @user` | Постоянен капитан |
| 🟠 `!ship-addpermanent @user <кораб>` / `!ship-removepermanent @user` | Постоянен екипаж без одобрение |
| 🟠 `!ship-listpermanent` | Списък на постоянния екипаж |
| 🟠 `!ship-addrepair <кораб> текст с {user}` / `!ship-repairs <кораб>` / `!ship-removerepair <id>` | Съобщения за repair канала |
| 🟠 `!shipstatus ...` / `!shipstatus-image` | Статус на екипажа (HP / умора) |
| 🔴 `!setup` | Праща панела на ръка (иначе излиза вторник и петък в 10:00) |
| 🔴 `!post-roles-info` / `!post-crew-info` / `!post-shipless-list` / `!post-unlock-info` | Публикува информационните карти |
| 🔴 `!blacklist-add <име> [причина]` / `!blacklist-remove <име>` / `!blacklist-refresh` | Черен списък на Belly Rush |

---

## 💰 Bounty

| Команда | Какво прави |
|---|---|
| 🟠 `!setbounty @user <сума>` | Задава bounty |
| 🟠 `!resetbounty @user` | Нулира bounty |

---

## 🧹 Модерация и съобщения

| Команда | Какво прави |
|---|---|
| 🟠 `!clear <брой>` | Трие последните съобщения (иска Manage Messages или Administrator) |
| 🔴 `!say <текст>` | Ботът пише съобщение |
| 🔴 `!sendto #канал <текст>` | Ботът пише в друг канал |
| 🔴 `!sendbday` | Праща рождения-ден съобщение веднага |
| 🔴 `!delete <id>` | Изтрива напомняне по ID |
| 🔴 `!maintenance` | Режим за поддръжка |

---

## 📊 Leveling и Mania

| Команда | Какво прави |
|---|---|
| 🔴 `!top` | Топ 10 най-активни |
| 🔴 `!sync` | Записва XP в базата веднага |
| 🔴 `!mania-addguild <код> @роля #канал #канал` | Добавя гилдия за Mania |
| 🔴 `!mania-guilds` / `!mania-removeguild <код>` | Списък и премахване |

---

## 🤖 Автоматични неща, за които админите получават известие

- **@everyone скам:** ботът трие съобщението, мълчи автора за 24 часа и пише на всички админи и в `admin_log_channel`.
- **Заявка за постоянен кораб (`!want`):** отива в `crew_approval_channel` (или `admin_log_channel`) с бутони Approve / Deny.
- **Изтрити съобщения, банове, таймаути:** логват се в `admin_log_channel`.

---

## 💡 Нужни права на бота

Manage Roles (роли), Manage Messages (чистене, @everyone защита), Moderate Members (таймаут), View Audit Log (лог кой е изтрил съобщение). Ролята на бота трябва да е **над** ролите, които управлява.
