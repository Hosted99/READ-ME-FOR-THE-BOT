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
