# МАШИНИ СТАНІВ КВЕСТІВ P26–P30

**Дата:** 2026-11-26

**Перевірений HEAD:** `d3dd245`

**Метод:** стани й переходи виведені з фактичних умов, флагів і текстів; це не код рушія.

---

## 1. Базові стани

| Стан | Умова | Поведінка |
|---|---|---|
| `LOCKED` | Тригер квесту false | Квест недоступний; повторний вхід не запускає сцену |
| `ACTIVE` | Тригер true, DONE false | Доступні діалог, відмова, провал, Акт II |
| `FAILED` | Провал/відмова | DONE не ставиться; повернення в `ACTIVE` з непоставленого кроку |
| `DONE_A` | Фінал А | DONE; окремого state немає |
| `DONE_B/C/G` | Фінал Б/В/Г | DONE + відповідний state |
| `REPEAT` | DONE true | Лише пам’ять; без нової сцени/нагород |

Для всіх 22 квестів діє правило: `DONE` — one-shot; `FAILED` і відмова не ставлять жодного флага; `REPEAT` не видає нагород.

---

## 2. Детальні машини

### 2.1. P26 HERO-26-01 → HERO-26-01-E (ґудзик)

```
[Q01 LOCKED] --trigger Q01_DONE false--> [Q01 ACTIVE]
[Q01 ACTIVE] --V4 refusal--> [Q01 ACTIVE] (no flag)
[Q01 ACTIVE] --fail escape--> [Q01 ACTIVE] (retry next night)
[Q01 ACTIVE] --Final A--> [Q01 DONE_A] (Q01_DONE; BUTTON absent)
[Q01 ACTIVE] --Final B--> [Q01 DONE_B] (Q01_DONE + Q01_BUTTON)
[Q01 DONE_A/B] --repeat--> [Q01 REPEAT] (memory only)

[Q01E LOCKED] --Q01_DONE true--> [Q01E ACTIVE]
[Q01E ACTIVE] --V4 refusal--> [Q01E ACTIVE] (no flag)
[Q01E ACTIVE] --fail alarm--> [Q01E ACTIVE] (retry next night)
[Q01E ACTIVE] --Final A burn--> [Q01E DONE_A] (Q01E_DONE)
[Q01E ACTIVE] --Final B archive--> [Q01E DONE_B] (Q01E_DONE + ARCHIVE)
[Q01E ACTIVE] --Final C charter--> [Q01E DONE_C] (Q01E_DONE + CHARTER)
[Q01E DONE_*] --repeat--> [Q01E REPEAT] (memory: гумно/архів/хартія)
```

**Ключові перевірки:**
- `Q01_BUTTON` впливає лише на репліку Оляни в 01-E (P26:138), не на доступність фіналів.
- Фінал В 01-E має умову P26:175, але в Акті II немає кроку переговорів; перехід `ACTIVE → DONE_C` декларативний (`GA-P26-001`).
- Фінал Б 01-E доступний після 01-A або 01-B, бо тригер читає лише `Q01_DONE` (P26:125).

### 2.2. P28 FOLK-28-02 (Цар-Вуж, дар, ріг)

Зовнішні стани P15:
- `P15_NONE` — Q03 не пройдено.
- `P15_NATURE` — `FLAG_P15_Q03_DONE` + `FLAG_P15_Q03_NATURE_TONGUE`.
- `P15_GREED` — `DONE` + `GREED_PUNISHED`; ріг повернуто владиці (P15:370).
- `P15_LIVING` — `DONE` + `LIVING_WATER`; герой торкався рога (P15:383), про повернення не сказано.

```
[Q02 LOCKED] --Q02_DONE true OR not Zdvizhennia--> [Q02 LOCKED]
[Q02 LOCKED] --Zdvizhennia window--> [Q02 ACTIVE]
[Q02 ACTIVE] --V4 refusal--> [Q02 ACTIVE] (no flag)
[Q02 ACTIVE] --fail (Вуж сховався)--> [Q02 ACTIVE] (same day retry)
[Q02 ACTIVE] --Final A (horn)--> [Q02 DONE_A] (Q02_DONE)
[Q02 ACTIVE] --Final B (drop)--> [Q02 DONE_B] (Q02_DONE + BALM)
[Q02 ACTIVE] --Final C (seal)--> [Q02 DONE_C] (Q02_DONE + WARD)
[Q02 DONE_*] --repeat--> [Q02 REPEAT] (memory only)

Gift resolution in DONE_A:
  P15_NONE    -> gift first time; horn accepted
  P15_GREED   -> gift first time; horn shed again (King has it)
  P15_LIVING  -> text says gift first time, but hero already touched horn  [HIGH]
  P15_NATURE  -> gift already present; horn "returns to the lord"          [ambiguous ownership]
```

**Проблеми:**
- `P15_LIVING → DONE_A` дає другий фізичний ріг (`GA-P28-001`).
- `P15_NATURE → DONE_A` не описує повернення рога, який герой носить із P15 (`GA-P28-001`).
- `DONE_B` і `DONE_C` не визначають, що сталося з рогом, який упав у кроці 3 (`GA-P28-002`).
- `Q02_DONE` не має окремого state дару; для майбутніх пакетів — `GC-P28-Q02-VOICE-001` (OBS).

### 2.3. P29 DRAMA-29-02 (чотири розв’язки)

```
[Q02 LOCKED] --Q02_DONE true--> [Q02 LOCKED]
[Q02 LOCKED] --trigger--> [Q02 ACTIVE]
[Q02 ACTIVE] --V4 refusal--> [Q02 ACTIVE] (no flag)
[Q02 ACTIVE] --fail (раду зірвано)--> [Q02 ACTIVE] (next day retry?)   [AMBIGUOUS]
[Q02 ACTIVE] --Final A (expose)--> [Q02 DONE_A] (Q02_DONE)
[Q02 ACTIVE] --Final B (rescue)--> [Q02 DONE_B] (Q02_DONE + RESCUE)
[Q02 ACTIVE] --Final C (song)--> [Q02 DONE_C] (Q02_DONE + SONG)
[Q02 ACTIVE] --Final G (ruin)--> [Q02 DONE_G] (Q02_DONE + RUIN)
[Q02 DONE_*] --repeat--> [Q02 REPEAT]
```

**Проблема:** `FAILED` («раду зірвано») і `DONE_G` («різанину не зупинено») мають однаковий тригер, але різні наслідки; немає умови, яка їх розрізняє (`GA-P29-001`). Фінал Г не має окремої дії/вибору в Акті II.

### 2.4. P30 ROM-30-03 (перлина)

```
[Q03 LOCKED] --Q03_DONE true--> [Q03 LOCKED]
[Q03 LOCKED] --trigger--> [Q03 ACTIVE]
[Q03 ACTIVE] --V4 refusal--> [Q03 ACTIVE] (no flag)
[Q03 ACTIVE] --fail (не встиг до заходу)--> [Q03 ACTIVE] (until tomorrow)
[Q03 ACTIVE] --Final A (wedding)--> [Q03 DONE_A] (Q03_DONE + pearl reward)
[Q03 ACTIVE] --Final B (deepward)--> [Q03 DONE_B] (Q03_DONE + DEEPWARD)
[Q03 ACTIVE] --Final C (dam)--> [Q03 DONE_C] (Q03_DONE + DAM)
[Q03 DONE_*] --repeat--> [Q03 REPEAT] (no second pearl)
```

**Проблема:** «перлина дихання» отримана в Акті II (P30:320), а фінал А знову подає «Перлину Росіани» як нагороду (P30:355). Це або той самий предмет, або дубль; текст не уточнює (`GA-P30-001`, OBS).

### 2.5. P27 KHOLOD-27-01 (Склик: A дія, B/C декларативні)

```
[Q01 LOCKED] --Q01_DONE true--> [Q01 LOCKED]
[Q01 LOCKED] --trigger--> [Q01 ACTIVE]
[Q01 ACTIVE] --V4 refusal--> [Q01 ACTIVE]
[Q01 ACTIVE] --fail (metal crack)--> [Q01 ACTIVE] (re-smelt)
[Q01 ACTIVE] --forging + 3 hits--> [Q01 DONE_A] (Q01_DONE)
[Q01 ACTIVE] --resonance (no step)--> [Q01 DONE_B] (Q01_DONE + RESONANCE)  [DECLARATIVE]
[Q01 ACTIVE] --tower integration (no step)--> [Q01 DONE_C] (Q01_DONE + NETWORK) [DECLARATIVE]
[Q01 DONE_*] --repeat--> [Q01 REPEAT]
```

**Проблема:** Акт II описує лише три удари (фінал А). Резонанс і вежовий тракт залишаються сетапом, не дією (`GA-SYS-001`).

---

## 3. Рівень квестів: зведена таблиця 22 квестів

| Пакет | Квест | Тригер | Відмова/провал | Фінали | Флаги | Повтор |
|---|---|---|---|---|---|---|
| P26 | HERO-26-01 | `Q01_DONE` false | без флагів; повтор | A/B | `Q01_DONE` (+`BUTTON`) | пам’ять |
| P26 | HERO-26-01-E | `Q01_DONE` + `Q01E_DONE` false | без флагів | A/B/C | `Q01E_DONE` (+`ARCHIVE`/`CHARTER`) | пам’ять |
| P26 | HERO-26-02 | `Q02_DONE` false | без флагів | A/B/C | `Q02_DONE` (+`FORTRESS`/`BROTHERHOOD`) | пам’ять |
| P26 | HERO-26-03 | `Q03_DONE` false | без флагів | A/B/C | `Q03_DONE` (+`RESCUE`/`SICH`) | пам’ять |
| P26 | HERO-26-04 | `Q04_DONE` false | без флагів | A/B/C | `Q04_DONE` (+`DUEL`/`BASTION`) | пам’ять |
| P26 | HERO-26-05 | `Q05_DONE` false | без флагів | A/B/C | `Q05_DONE` (+`BARTKA`/`STONE`) | пам’ять |
| P27 | KHOLOD-27-01 | `Q01_DONE` false | без флагів | A/B/C | `Q01_DONE` (+`RESONANCE`/`NETWORK`) | пам’ять |
| P27 | KHOLOD-27-02 | `Q02_DONE` false | без флагів | A/B/C | `Q02_DONE` (+`BASTION`/`BALM`) | пам’ять |
| P27 | KHOLOD-27-03 | `Q03_DONE` false | без флагів | A/B/C | `Q03_DONE` (+`MAP`/`WARD`) | пам’ять |
| P27 | KHOLOD-27-04 | `Q04_DONE` false | без флагів | A/B/C | `Q04_DONE` (+`POWDER`/`SCHOOL`) | пам’ять |
| P28 | FOLK-28-01 | `Q01_DONE` false | без флагів | A/B/C | `Q01_DONE` (+`TOBACCO`/`CARNIVAL`) | пам’ять |
| P28 | FOLK-28-02 | `Q02_DONE` false + Здвиження | без флагів; same day | A/B/C | `Q02_DONE` (+`BALM`/`WARD`); CHECK P15 | пам’ять |
| P28 | FOLK-28-03 | `Q03_DONE` false | без флагів | A/B/C | `Q03_DONE` (+`FEATHER`/`WATER`) | пам’ять |
| P28 | FOLK-28-04 | `Q04_DONE` false | без флагів | A/B/C | `Q04_DONE` (+`GROVE`/`PACT`) | пам’ять |
| P29 | SATIR-29-01 | `Q01_DONE` false | без флагів | A/B/C | `Q01_DONE` (+`SEA`/`TRADE`) | пам’ять |
| P29 | DRAMA-29-02 | `Q02_DONE` false | без флагів | A/B/C/Г | `Q02_DONE` (+`RESCUE`/`SONG`/`RUIN`) | пам’ять; fail/G ambiguity |
| P29 | SOC-29-03 | `Q03_DONE` false | без флагів | A/B/C | `Q03_DONE` (+`SAILOR`/`ASHES`) | пам’ять |
| P30 | ROM-30-01 | `Q01_DONE` false | без флагів | A/B/C | `Q01_DONE` (+`TEAR`/`GROVE`) | пам’ять |
| P30 | ROM-30-02 | `Q02_DONE` false | без флагів | A/B/C | `Q02_DONE` (+`STARFLIGHT`/`WATCH`) | пам’ять |
| P30 | ROM-30-03 | `Q03_DONE` false | без флагів | A/B/C | `Q03_DONE` (+`DEEPWARD`/`DAM`) | пам’ять |
| P30 | ROM-30-04 | `Q04_DONE` false | без флагів | A/B/C | `Q04_DONE` (+`LEAP`/`WREATH`) | пам’ять |
| P30 | ROM-30-05 | `Q05_DONE` false | без флагів | A/B/C | `Q05_DONE` (+`FREEHOLD`/`SONG`) | пам’ять |

---

## 4. Матриця 66 фіналів

Позначення дії: `Y` — у Акті II є крок, що directly виконує умову; `N` — лише сетап/декларація; `P` — часткова дія.

| # | Пакет | Квест | Фінал | Умова (стисло) | Флаг(и) | Дія | Примітка |
|---:|---|---|---|---|---|---|---|
| 1 | P26 | HERO-26-01 | A «Лісова Воля» | вийти з Кармелюком | `Q01_DONE` | Y | крок 3 |
| 2 | P26 | HERO-26-01 | B «Срібний Ґудзик» | зняти ґудзик | `Q01_DONE+BUTTON` | Y | крок 2Б |
| 3 | P26 | HERO-26-01-E | A «Попіл» | підпалити гумно | `Q01E_DONE` | Y | Етап 2 |
| 4 | P26 | HERO-26-01-E | B «Списки» | винести архів | `Q01E_DONE+ARCHIVE` | Y | Етап 2 |
| 5 | P26 | HERO-26-01-E | В «Хартія» | переговори | `Q01E_DONE+CHARTER` | N | `GA-P26-001` |
| 6 | P26 | HERO-26-02 | A «Ніж» | занурити клинок | `Q02_DONE` | Y | Етап 2 |
| 7 | P26 | HERO-26-02 | B «Твердиня» | відбити драгун | `Q02_DONE+FORTRESS` | N | лише сетап/подія |
| 8 | P26 | HERO-26-02 | В «Заповіт» | заснувати братство | `Q02_DONE+BROTHERHOOD` | N | лише сетап |
| 9 | P26 | HERO-26-03 | A «Три стріли» | подати лук | `Q03_DONE` | Y | Етап 1 |
| 10 | P26 | HERO-26-03 | B «Прорив» | піднятися/перепиляти | `Q03_DONE+RESCUE` | Y | Етап 3 [0/1] |
| 11 | P26 | HERO-26-03 | В «Січ» | прийняти грамоту | `Q03_DONE+SICH` | N | лише сетап |
| 12 | P26 | HERO-26-04 | A «Морок» | навести морок | `Q04_DONE` | Y | Етапи 1–3 |
| 13 | P26 | HERO-26-04 | B «Герць» | викликати командира | `Q04_DONE+DUEL` | N | лише сетап |
| 14 | P26 | HERO-26-04 | В «Редути» | побудувати редути | `Q04_DONE+BASTION` | N | лише сетап |
| 15 | P26 | HERO-26-05 | A «Золото» | роздати срібло | `Q05_DONE` | Y | Етап 3 |
| 16 | P26 | HERO-26-05 | B «Бартка» | прийняти бартку | `Q05_DONE+BARTKA` | N | лише сетап |
| 17 | P26 | HERO-26-05 | В «Камінь» | запечатати перевали | `Q05_DONE+STONE` | N | лише сетап |
| 18 | P27 | KHOLOD-27-01 | A «Склик» | три удари | `Q01_DONE` | Y | Етап 3 |
| 19 | P27 | KHOLOD-27-01 | B «Резонанс» | налаштувати резонанс | `Q01_DONE+RESONANCE` | N | лише сетап |
| 20 | P27 | KHOLOD-27-01 | В «Мережа» | інтегрувати вежі | `Q01_DONE+NETWORK` | N | лише сетап |
| 21 | P27 | KHOLOD-27-02 | A «Жива Крапля» | очистити/напоїти | `Q02_DONE` | Y | Етап 2 |
| 22 | P27 | KHOLOD-27-02 | B «Бастіон» | звести бастіон | `Q02_DONE+BASTION` | N | лише сетап |
| 23 | P27 | KHOLOD-27-02 | В «Бальзам» | зварити бальзам | `Q02_DONE+BALM` | N | лише сетап |
| 24 | P27 | KHOLOD-27-03 | A «Акінак» | випробування волі | `Q03_DONE` | Y | Етап 2 |
| 25 | P27 | KHOLOD-27-03 | B «Карта» | скласти карту | `Q03_DONE+MAP` | Y | Етап 2 |
| 26 | P27 | KHOLOD-27-03 | В «Варта» | освятити вали | `Q03_DONE+WARD` | N | лише сетап |
| 27 | P27 | KHOLOD-27-04 | A «Засідка» | розбити колону | `Q04_DONE` | Y | Етап 2 |
| 28 | P27 | KHOLOD-27-04 | B «Порох» | підірвати фургон | `Q04_DONE+POWDER` | N | лише сетап |
| 29 | P27 | KHOLOD-27-04 | В «Школа» | заснувати школу | `Q04_DONE+SCHOOL` | N | лише сетап |
| 30 | P28 | FOLK-28-01 | A «Цар-Сом» | замирити/нагодувати | `Q01_DONE` | Y | Етап 3 |
| 31 | P28 | FOLK-28-01 | B «Люлька» | повернути люльку | `Q01_DONE+TOBACCO` | N | лише сетап |
| 32 | P28 | FOLK-28-01 | В «Карнавал» | вийти святкувати | `Q01_DONE+CARNIVAL` | N | лише сетап |
| 33 | P28 | FOLK-28-02 | A «Голос Землі» | прийняти ріг | `Q02_DONE` | Y | крок 3; ріг HIGH |
| 34 | P28 | FOLK-28-02 | B «Слина/Роса» | підставити рушник | `Q02_DONE+BALM` | N | ріг не визначений |
| 35 | P28 | FOLK-28-02 | В «Союз» | запечатати вхід | `Q02_DONE+WARD` | N | ріг не визначений |
| 36 | P28 | FOLK-28-03 | A «Гармонія» | залатати тріщину | `Q03_DONE` | Y | Етап 2 |
| 37 | P28 | FOLK-28-03 | B «Перо» | прийняти перо | `Q03_DONE+FEATHER` | N | лише сетап |
| 38 | P28 | FOLK-28-03 | В «Вода» | освятити річки | `Q03_DONE+WATER` | N | лише сетап |
| 39 | P28 | FOLK-28-04 | A «Удар» | скинути Змія | `Q04_DONE` | Y | Етап 2 |
| 40 | P28 | FOLK-28-04 | B «Калина» | посадити кущі | `Q04_DONE+GROVE` | N | лише сетап |
| 41 | P28 | FOLK-28-04 | В «Договір» | домовитися | `Q04_DONE+PACT` | Y | Етап 2 альтернатива |
| 42 | P29 | SATIR-29-01 | A «Лист» | запечатати/вручити | `Q01_DONE` | Y | Етап 3 |
| 43 | P29 | SATIR-29-01 | B «Рейд» | відправити чайки | `Q01_DONE+SEA` | P | ескорт, не 20 чайок |
| 44 | P29 | SATIR-29-01 | В «Гендель» | викупити тюрбан | `Q01_DONE+TRADE` | P | тюрбан знято, викуп — ні |
| 45 | P29 | DRAMA-29-02 | A «Згода» | викрити агітаторів | `Q02_DONE` | Y | Етап 2 [0/3] |
| 46 | P29 | DRAMA-29-02 | B «Леся» | вивезти сім’ю | `Q02_DONE+RESCUE` | N | лише сетап |
| 47 | P29 | DRAMA-29-02 | В «Пісня» | доспівати думу | `Q02_DONE+SONG` | Y | Етап 2 |
| 48 | P29 | DRAMA-29-02 | Г «Руїна» | не зупинити різанину | `Q02_DONE+RUIN` | N | fail/G ambiguity |
| 49 | P29 | SOC-29-03 | A «Грамота» | відбити/грамота | `Q03_DONE` | Y | Етап 1 |
| 50 | P29 | SOC-29-03 | B «Море» | хрещення | `Q03_DONE+SAILOR` | N | лише сетап |
| 51 | P29 | SOC-29-03 | В «Попіл» | спалити книги | `Q03_DONE+ASHES` | Y | Етап 2 |
| 52 | P30 | ROM-30-01 | A «Подружжя» | обітниця | `Q01_DONE` | Y | Етап 3 |
| 53 | P30 | ROM-30-01 | B «Сльоза» | віддати перлину | `Q01_DONE+TEAR` | N | лише сетап |
| 54 | P30 | ROM-30-01 | В «Брама» | не йти з лісу | `Q01_DONE+GROVE` | N | лише сетап |
| 55 | P30 | ROM-30-02 | A «Обручка» | прийняти перстень | `Q02_DONE` | Y | Етап 3 |
| 56 | P30 | ROM-30-02 | B «Злет» | злетіти разом | `Q02_DONE+STARFLIGHT` | N | лише сетап |
| 57 | P30 | ROM-30-02 | В «Варта» | благословити розлуку | `Q02_DONE+WATCH` | N | лише сетап |
| 58 | P30 | ROM-30-03 | A «Весілля» | дари/обітниця | `Q03_DONE` | Y | Етап 3 |
| 59 | P30 | ROM-30-03 | B «Варта» | лишитися під водою | `Q03_DONE+DEEPWARD` | N | лише сетап |
| 60 | P30 | ROM-30-03 | В «Гребля» | маяк/гребля | `Q03_DONE+DAM` | N | лише сетап |
| 61 | P30 | ROM-30-04 | A «Папороть» | зірвати квітку | `Q04_DONE` | Y | Етап 3 |
| 62 | P30 | ROM-30-04 | B «Стрибок» | стрибок | `Q04_DONE+LEAP` | Y | Етап 2 |
| 63 | P30 | ROM-30-04 | В «Вінок» | прибити вінок | `Q04_DONE+WREATH` | N | лише сетап |
| 64 | P30 | ROM-30-05 | A «Вінчання» | встромити ніж | `Q05_DONE` | Y | Етап 3 |
| 65 | P30 | ROM-30-05 | B «Ватага» | спрямувати град | `Q05_DONE+FREEHOLD` | N | лише сетап |
| 66 | P30 | ROM-30-05 | В «Трембіта» | засурмити | `Q05_DONE+SONG` | N | лише сетап |

**Підсумок:** 30 `Y`, 34 `N`, 2 `P` (P29 Q01-B/C). Усі 66 мають умову, SET і наслідок; 36 не мають повної дії (`GA-SYS-001`).

---

## 5. Виявлені стани, які неможливо отримати або скинути

| Стан | Проблема | Статус |
|---|---|---|
| `FLAG_P28_Q02_DONE` + дар | Немає окремого state дару; `DONE` не розрізняє «дар уперше» і «дар підтверджено» | OBS `GC-P28-Q02-VOICE-001` |
| `FLAG_P15_Q03_LIVING_WATER` → P28 | Фізичний ріг уже в героя, але P28 дає новий | HIGH `GA-P28-001` |
| `FLAG_P29_Q02_RUIN` | Конкурує з fail-станом; немає умови розрізнення | MEDIUM `GA-P29-001` |
| `Q01_BUTTON` | Має двох споживачів (повтор + 01-E); не губиться | OK |
| `Q01E_ARCHIVE/CHARTER` | Взаємовиключні через один DONE; CLEAR немає | OK |
| Усі state-флаги | CLEAR немає; скидання не передбачене | OK (постійні) |

**Висновок:** флагових циклів, «SET без CHECK» і «CHECK без SET» у межах 66 ID не знайдено. Проблеми — предметно-наративні (ріг, перлина, fail/G), а не відсутність ID.
