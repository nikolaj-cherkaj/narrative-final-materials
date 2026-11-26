# 02. ПОВТОРНАЯ ПРОВЕРКА ВСЕХ FINDINGS

**Проверяемый HEAD:** `d2b4e5d`

**Метод:** прямое чтение P15, P26–P30, реестров и Git diff; отчёты ремедиации использованы только как список заявлений, не как доказательство.

---

## 1. Ключевые findings, названные пользователем

| ID | Приоритет | Исходная проблема | Заявленное исправление | Фактическое состояние | Статус |
|---|---|---|---|---|---|
| `GA-P28-001` | HIGH | Физический рог дублировался/не имел владельца; `LIVING_WATER` и `NATURE_TONGUE` не согласованы с P28 | P15 финал А — рог у героя; Б — у владыки; эхо — возврат; P28 условный шаг 3; финалы А/Б/В определяют владельца | Прямой порядок: 12/12 комбинаций без дублирования; P15:358–359, 370–371, 383–384; P28:152–157, 195–198, 218–231 | **VERIFIED FIXED** (прямой порядок). Остаточные: обратный порядок `GA2-P28-002`, дублирование описания возврата `GA2-P28-001`, scope `GA2-P15-001` |
| `INT-P28-H01` | HIGH | Дар мови не подвоювався за `DONE`, хоча P15 має фінали без дару | `DONE` — узнавание; `NATURE_TONGUE` — дар | P28:152–157: дар только при `NATURE_TONGUE`; `LIVING_WATER`/`GREED_PUNISHED`/none — без дара; P28:196, 219 | **VERIFIED FIXED** |
| `GA-P28-002` | MEDIUM | Шаг 3 безусловно скидывал рог; финалы Б/В не определяли судьбу | Шаг 3 условный; Б/В не скидывают рог | P28:195–198, 224, 229 | **VERIFIED FIXED** |
| `GA-P26-001` | MEDIUM | P26 HERO-26-01-E финал В «Хартія» без игрового шага | Варіант 3 → переговоры; Этап 2В; финал В требует хартию | P26:143–144, 156–160, 178–183 | **VERIFIED FIXED** |
| `GA-SYS-001` | MEDIUM | 36/66 финалов имели только декларативный сетап | 19 блоков выбора + Этап 2В + P28 шаг 3 | Все 66 финалов имеют условие, действие/выбор и SET; 19 блоков «Розв’язка: вибір шляху»; P26:253–258, 361–366, 461–466, 573–578; P27:113–118, 219–224, 320–325, 414–419; P28:91–96, 195–198, 297–302, 395–400; P29:117–122, 235–241, 353–358; P30:84–89, 229–234, 361–366, 489–494, 617–622 | **VERIFIED FIXED** |
| `GA-FLAG-001` | MEDIUM | 27 state-флагов без флаг-специфичного CHECK; P26 Q04/Q05 противоречили финалу | 27 повторных реплик; P26 Q04/Q05 переписаны | 44/44 state-флага имеют повтор; 27/27 целевых — с именем флага; P26:418, 520 | **VERIFIED FIXED** |
| `GA-P29-001` | MEDIUM | P29 DRAMA-29-02: финал Г и обычный провал имели один триггер | Fail — Сомко жив, повтор, без `RUIN`; Г — отдельный выбор, `RUIN` | P29:228–241, 281–289; fail 233; repeat 185 | **VERIFIED FIXED** |
| `GA-DOC-001` | LOW | 17 MEDIUM vs 18 | 18 | `INTEGRATION_REPORT.md:57`; `GLOBAL_CARRYOVER_REGISTER.md:290` | **VERIFIED FIXED** |
| `GA-DOC-002` | LOW | CHARACTERS NPC-0254: таблица P26, карточка P13 | Таблица P13 | `CHARACTERS.md:290`, `2489` | **VERIFIED FIXED** |
| `GA-DOC-003` | LOW | FLAG_REGISTRY §15 «множинні ріжки» | Один рог | `FLAG_REGISTRY.md:1111` | **VERIFIED FIXED** |
| `GA-P29-002` | LOW | P29 «15 NPC», перечислено 16 | 16 | P29:403 | **VERIFIED FIXED** |
| `GA-P28-003` | LOW | P28 финал Б «Слина» vs «роса» | «Роса Зміїного Царя» | P28:222; `FLAG_REGISTRY.md:2825` | **VERIFIED FIXED** |
| `GA-LANG-001` | LOW | P30:541 «на кателів» | «на карателів» | P30:568 | **VERIFIED FIXED** |
| `GA-LANG-002` | LOW | P26:22 «у три пудові» | «трипудові» | P26:22 | **VERIFIED FIXED** |

---

## 2. Остальные findings первоначального аудита

| ID | Приоритет | Статус | Доказательство/комментарий |
|---|---|---|---|
| `GA-DOC-004` | OBS | **ACCEPTED NON-BLOCKING** | P25:260–261 всё ещё «не механічна перевірка»; P26:41, 50 реально читает `ALLIANCE`; doc-only, передано |
| `GA-P30-001` | OBS | **VERIFIED FIXED** | P30:375 — «та сама перлина дихання… другої перлини нема»; repeat P30:293 |
| `GA-ACC-001` | OBS | **ACCEPTED NON-BLOCKING** | P27:313 — печать не является условием финала; не гейт |
| `GA-ACC-002` | OBS | **PARTIALLY FIXED** | P27:280 — «чути дряпання нігтем»; **P28:181 всё ещё «не озирайся на шелест»**, хотя `FINDINGS_STATUS_MATRIX.md:33` заявляет «не обертайся» |
| `GA-REWARD-001` | OBS | **ACCEPTED NON-BLOCKING** | Часть финалов Б/В без отдельного блока «Нагорода», но обещания не нарушены |
| `GA-DOC-005` | OBS | **VERIFIED FIXED** | `INTEGRATION_REPORT.md:66` — «2 фінали + відлуння» |

---

## 3. 35 findings первоначальной интеграции

### 3.1. HIGH (6)

| ID | Статус | Доказательство |
|---|---|---|
| `INT-P26-H01` | **VERIFIED FIXED** | P26:136–138; CHECK `FLAG_P26_Q01_BUTTON`; SET P26:115 |
| `INT-P26-H02` | **VERIFIED FIXED** | P26:55, 75–77, 110–115; Этап 2Б |
| `INT-P28-H01` | **VERIFIED FIXED** | P28:152–157, 195–198, 218–231; дар/рог разделены |
| `INT-P28-H02` | **VERIFIED FIXED** | P28:202; повтор того же дня |
| `INT-ACC-P27-H01` | **VERIFIED FIXED** | P27:217; «Стій! Праворуч!» |
| `INT-ACC-P30-H01` | **VERIFIED FIXED** | P30:359; «Стій! Праворуч!» |

### 3.2. MEDIUM (18)

| ID | Статус | Доказательство |
|---|---|---|
| `INT-P26-M01` | **VERIFIED FIXED** | P26:181, 126; титул «Підписант Подільської Хартії», повтор А/Б/В |
| `INT-P26-M02` | **VERIFIED FIXED** | P26:50; P25:200–201 |
| `INT-P26-M03` | **VERIFIED FIXED** | P26 Q02–Q05: блоки 253–258, 361–366, 461–466, 573–578 |
| `INT-P26-M04` | **VERIFIED FIXED** | P26:396; Байда скидає грамоту, чайки знімають |
| `INT-P26-M05` | **VERIFIED FIXED** | P26:489; герой и Палій на герці |
| `INT-P27-M01` | **VERIFIED FIXED** | P27:217 |
| `INT-P27-M02` | **VERIFIED FIXED** | P27:280; зарубки, «чути дряпання нігтем» |
| `INT-P27-M03` | **VERIFIED FIXED** | P27 Q01–Q04: блоки 113–118, 219–224, 320–325, 414–419 |
| `INT-P28-M01` | **VERIFIED FIXED** | P28:181; звук шелесту/дихання |
| `INT-P28-M02` | **VERIFIED FIXED** | P28:195–198; блоки Q01/Q03/Q04 91–96, 297–302, 395–400 |
| `INT-P28-M03` | **VERIFIED FIXED** | P28:121; Баюра дарит люльку на память |
| `INT-P29-M01` | **VERIFIED FIXED** | P29:204; сцена у возов |
| `INT-P29-M02` | **VERIFIED FIXED** | P29:117–122, 353–358; тюрбан в Акте II |
| `INT-P29-M03` | **VERIFIED FIXED** | P29:270; Сомко жив, без булавы |
| `INT-P30-M01` | **VERIFIED FIXED** | P30:359 |
| `INT-P30-M02` | **VERIFIED FIXED** | P30:435, 466, 469; треск венка и пение ведут |
| `INT-P30-M03` | **VERIFIED FIXED** | P30:398, 403; маяк + кристальная плотина |
| `INT-P30-M04` | **VERIFIED FIXED** | P30 Q01–Q05: блоки 84–89, 229–234, 361–366, 489–494, 617–622 |

### 3.3. LOW (5)

| ID | Статус | Доказательство |
|---|---|---|
| `INT-DOC-01` | **VERIFIED FIXED** | `CHARACTERS.md:6` — 418 |
| `INT-DOC-02` | **VERIFIED FIXED** | `CHARACTERS.md:290` — P13 QUEST-13-02; `2489` |
| `INT-DOC-03` | **VERIFIED FIXED** | `FLAG_REGISTRY.md:2496–2500`; P26:41, 50 |
| `INT-DOC-04` | **VERIFIED FIXED** | `FLAG_REGISTRY.md:49`, `1191–1198`, `2787`, `2821`; §15:1111 |
| `INT-DOC-05` | **VERIFIED FIXED** | `FLAG_REGISTRY.md:3053–3058`; P30:398 |

### 3.4. OBS (6)

| ID | Статус | Комментарий |
|---|---|---|
| `INT-OBS-01` «Дана» | **ACCEPTED NON-BLOCKING** (owner decision pending) | P28:265; в MYTHOLOGY/TERMINOLOGY/WORLD_CANON совпадений 0; текст не менялся |
| `INT-OBS-02` два игумена | **ACCEPTED NON-BLOCKING** (owner decision pending) | P26:201 Мелхіседек; P27:275 Мелетій; прямого конфликта нет |
| `INT-OBS-03` Устим P25/P26 | **VERIFIED FIXED (игра)** | P25:182, 200–201; P26:41, 50; P25-текст — `GA-DOC-004` |
| `INT-OBS-04` обратный порядок | **NOT FIXED** (non-blocking при обязательном порядке) | P15:278 не читает `FLAG_P28_Q02_DONE`; см. `08_REMAINING_FINDINGS.md` `GA2-P28-002`; нужно решение владельца |
| `INT-OBS-05` state дара P28 | **ACCEPTED NON-BLOCKING** (owner decision pending) | `FLAG_P28_Q02_VOICE` не создан; P28:218–221; future consumer |
| `INT-OBS-06` Леся NEW | **ACCEPTED NON-BLOCKING** (owner decision pending) | `CHARACTERS.md:424`, `3526`; P29:173, 197; NEW |

---

## 4. Итоговая матрица

### 4.1. 35 findings первоначальной интеграции

| Статус | HIGH | MEDIUM | LOW | OBS | Всего |
|---|---:|---:|---:|---:|---:|
| VERIFIED FIXED | 6 | 18 | 5 | 1 (`INT-OBS-03`, игра) | 30 |
| PARTIALLY FIXED | 0 | 0 | 0 | 0 | 0 |
| ACCEPTED NON-BLOCKING | 0 | 0 | 0 | 4 (`INT-OBS-01`, `02`, `05`, `06`) | 4 |
| NOT FIXED | 0 | 0 | 0 | 1 (`INT-OBS-04`) | 1 |
| **Всего** | **6** | **18** | **5** | **6** | **35** |

### 4.2. 19 findings первоначального независимого аудита

| Статус | HIGH | MEDIUM | LOW | OBS | Всего |
|---|---:|---:|---:|---:|---:|
| VERIFIED FIXED | 1 | 5 | 7 | 2 (`GA-P30-001`, `GA-DOC-005`) | 15 |
| PARTIALLY FIXED | 0 | 0 | 0 | 1 (`GA-ACC-002`) | 1 |
| ACCEPTED NON-BLOCKING | 0 | 0 | 0 | 3 (`GA-DOC-004`, `GA-ACC-001`, `GA-REWARD-001`) | 3 |
| **Всего** | **1** | **5** | **7** | **6** | **19** |

### 4.3. Новые findings этого аудита

| ID | Приоритет | Статус |
|---|---|---|
| `GA2-P15-001` | LOW (scope) | **NOT FIXED** (non-blocking; нужно подтверждение владельца) |
| `GA2-P28-001` | LOW | **NOT FIXED** (non-blocking; редакционная правка) |
| `GA2-P28-002` | MEDIUM | **NOT FIXED** (non-blocking при обязательном порядке; нужно решение владельца) |
| `GA2-DOC-001` | LOW | **NOT FIXED** (non-blocking; исправить отчёт/текст) |
| `GA2-DOC-002` | LOW | **NOT FIXED** (non-blocking; исправить реестр) |
| `GA2-P25-001` | OBS | **ACCEPTED NON-BLOCKING** (передано) |
| `GA2-ACC-001` | OBS | **ACCEPTED NON-BLOCKING** |
| `GA2-P28-003` | OBS | **ACCEPTED NON-BLOCKING** (future consumer) |
| `GA2-P29-001` | OBS | **ACCEPTED NON-BLOCKING** |

**Вывод:** ни одного открытого CRITICAL/HIGH нет. Открыты: 1 MEDIUM (`GA2-P28-002`, обратный порядок), 1 LOW scope (`GA2-P15-001`), 2 LOW-документационных (`GA2-DOC-001/002`), 1 LOW-редакционный (`GA2-P28-001`), остальное — OBS.
