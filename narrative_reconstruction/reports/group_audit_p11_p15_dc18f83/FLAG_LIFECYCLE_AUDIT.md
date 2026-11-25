# FLAG LIFECYCLE AUDIT — P11–P15 (HEAD `dc18f83`)

**Реестр:** `canon/FLAG_REGISTRY.md` v2.2, §11–§15 (60 ID: 12 × 5).
**Тексты:** `revised/naratyvni_teksty_paket_11…15.md` @ `dc18f83`.
**Внешние:** `FLAG_P05_CHUHAYSTER_KILLED` / `_ABSENT` (P13 читает; P05 — источник).
**Правило:** SET/CHECK/CLEAR сверены по строкам; числа наград — примеры; TTS не тестировался.

## 1. P11 — 12 ID

| ID | SET (текст) | CHECK (текст) | CLEAR | Тип | Повтор | Вердикт |
|---|---|---|---|---|---|---|
| `FLAG_P11_Q01_DONE` | 125/140/157 | 27; 125/140/157 | — | one-shot | память | MATCH |
| `FLAG_P11_Q01_FIRST_SWORD` | 125 | 125 | — | state | память | MATCH |
| `FLAG_P11_Q01_BROTHER_SAVED` | 140 | 140 | — | state | память | MATCH |
| `FLAG_P11_Q01_SPRINGS_HEALED` | 157 | 157 | — | state | память | MATCH |
| `FLAG_P11_Q02_DONE` | 281/295/309 | 180; 281/295/309 | — | one-shot | память | MATCH |
| `FLAG_P11_Q02_WREATH_UNION` | 281 | 281 | — | state | память | MATCH |
| `FLAG_P11_Q02_RIVER_CLEANSED` | 295 | 295 | — | state | память | MATCH |
| `FLAG_P11_Q02_BROTHERHOOD_FEAST` | 309 | 309 | — | state | память | MATCH |
| `FLAG_P11_Q03_DONE` | 420/436/450 | 332; 420/436/450 | — | one-shot | память | MATCH |
| `FLAG_P11_Q03_STEEL_BROTHERHOOD` | 420 | 420 | — | state | память | MATCH |
| `FLAG_P11_Q03_PEACE_PACT` | 436 | 436 | — | state | память | MATCH |
| `FLAG_P11_Q03_ORDER_FOUNDED` | 450 | 450 | — | state | память | MATCH |

Провал P11:108; отказ P11:62/216/363 — флагов не ставят. Внешних читателей P11 нет.

## 2. P12 — 12 ID

| ID | SET (текст) | CHECK (текст) | CLEAR | Тип | Повтор | Вердикт |
|---|---|---|---|---|---|---|
| `FLAG_P12_Q01_DONE` | 145/160/174 | 66; 145/160/174 | — | one-shot | память | MATCH |
| `FLAG_P12_Q01_GATE_HELD` | 145 | 145 | — | state | память | MATCH |
| `FLAG_P12_Q01_CULVERTS_FLOODED` | 160 | 160 | — | state | память | MATCH |
| `FLAG_P12_Q01_LIGHT_BARRIER` | 174 | 174 | — | state | память | MATCH |
| `FLAG_P12_Q02_DONE` | 275/291/306 | 196; 275/291/306 | — | one-shot | память | MATCH |
| `FLAG_P12_Q02_ALLIANCE` | 275 | 275 | — | state | память | MATCH |
| `FLAG_P12_Q02_CATHEDRAL_LAW` | 291 | 291 | — | state | память | MATCH |
| `FLAG_P12_Q02_CHARTER` | 306 | 306 | — | state | память | MATCH |
| `FLAG_P12_Q03_DONE` | 406/421/435 | 328; 406/421/435 | — | one-shot | память | MATCH |
| `FLAG_P12_Q03_FURROW_PLOWED` | 406 | 406 | — | state | память | MATCH |
| `FLAG_P12_Q03_GALLERY_SEALED` | 421 | 421 | — | state | память | MATCH |
| `FLAG_P12_Q03_SERPENT_DREAMING` | 435 | 435 | — | state | память | MATCH |

Провал P12:128/258/389; отказ P12:100/230/361 — флагов не ставят. Внешних читателей P12 нет.

## 3. P13 — 12 ID

| ID | SET (текст) | CHECK (текст) | CLEAR | Тип | Повтор | Вердикт |
|---|---|---|---|---|---|---|
| `FLAG_P13_Q01_DONE` | 147/159/171 | 65; 147/159/171 | — | one-shot | память | MATCH |
| `FLAG_P13_Q01_RAIN` | 147 | 147 | — | state | память | MATCH |
| `FLAG_P13_Q01_WRATH` | 159 | 159 | — | state | память | MATCH |
| `FLAG_P13_Q01_PEACE` | 171 | 171 | — | state | память | MATCH |
| `FLAG_P13_Q02_DONE` | 273/286/299 | 190; 273/286/299 | — | one-shot | память | MATCH |
| `FLAG_P13_Q02_BARTKA` | 273 | 273 | — | state | память | MATCH |
| `FLAG_P13_Q02_JUSTICE` | 286 | 286 | — | state | память | MATCH |
| `FLAG_P13_Q02_BROTHERHOOD` | 299 | 299 | — | state | память | MATCH |
| `FLAG_P13_Q03_DONE` | 411/423/435 | 319; 411/423/435 | — | one-shot | память | MATCH |
| `FLAG_P13_Q03_DANCE` | 411 | 411 | — | state | память | MATCH |
| `FLAG_P13_Q03_TEAR` | 423 | 423 | — | state | память | MATCH |
| `FLAG_P13_Q03_SONG` | 435 | 435 | — | state | память | MATCH |

Провал P13:129/255/393; отказ P13:98/226/365 — флагов не ставят.
**Внешние P05:** `FLAG_P05_CHUHAYSTER_KILLED` / `_ABSENT` — CHECK P13:216/218 (Q02), 340/342 (Q03); P13 их не SET/CLEAR. Семантика P05:87/90 — KILLED постоянный, ABSENT — три рассвета. MATCH.

## 4. P14 — 12 ID

| ID | SET (текст) | CHECK (текст) | CLEAR | Тип | Повтор | Вердикт |
|---|---|---|---|---|---|---|
| `FLAG_P14_Q01_DONE` | 142/156/168 | 64; 142/156/168 | — | one-shot | память | MATCH |
| `FLAG_P14_Q01_TYASMIN` | 142 | 142 | — | state | память | MATCH |
| `FLAG_P14_Q01_DUEL` | 156 | 156 | — | state | память | MATCH |
| `FLAG_P14_Q01_PEACE` | 168 | 168 | — | state | память | MATCH |
| `FLAG_P14_Q02_DONE` | 266/279/292 | 186; 266/279/292 | — | one-shot | память | MATCH |
| `FLAG_P14_Q02_FLOTILLA` | 266 | 266 | — | state | память | **MATCH текста; реестр §14 устарел — `GA-P14-003`** |
| `FLAG_P14_Q02_RESCUE` | 279 | 279 | — | state | память | MATCH |
| `FLAG_P14_Q02_SWORD` | 292 | 292 | — | state | память | MATCH |
| `FLAG_P14_Q03_DONE` | 389/401/414 | 311; 389/401/414 | — | one-shot | память | MATCH |
| `FLAG_P14_Q03_BLESSING` | 389 | 389 | — | state | память | MATCH |
| `FLAG_P14_Q03_TREASURY` | 401 | 401 | — | state | память | MATCH |
| `FLAG_P14_Q03_SEALED` | 414 | 414 | — | state | память | MATCH |

Провал P14:124/248/371; отказ P14:97/219/343 — флагов не ставят. Внешних читателей P14 нет; предметная зависимость P34 — `GC-P14-P34-001`.

## 5. P15 — 12 ID

| ID | SET (текст) | CHECK (текст) | CLEAR | Тип | Повтор | Вердикт |
|---|---|---|---|---|---|---|
| `FLAG_P15_Q01_DONE` | 108/121/134 | 27; 108/121/134 | — | one-shot | память | MATCH |
| `FLAG_P15_Q01_HORN_SHOT` | 108 | 108 | — | state | память | MATCH |
| `FLAG_P15_Q01_MILL_BOUND` | 121 | 121 | — | state | память | MATCH |
| `FLAG_P15_Q01_SERPENT_JUDGE` | 134 | 134; 314 | — | state | память | MATCH |
| `FLAG_P15_Q02_DONE` | 235/247/259 | 153; 235/247/259 | — | one-shot | память | MATCH |
| `FLAG_P15_Q02_DUMA_SUNG` | 235 | 235 | — | state | память | MATCH |
| `FLAG_P15_Q02_NEDOLYA_SEALED` | 247 | 247 | — | state | память | MATCH |
| `FLAG_P15_Q02_KOBZA_HEIR` | 259 | 259 | — | state | память | MATCH |
| `FLAG_P15_Q03_DONE` | 359/371/384 | 278; 359/371/384; 133 | — | one-shot | память | MATCH |
| `FLAG_P15_Q03_NATURE_TONGUE` | 359 | 359 | — | state | память | MATCH |
| `FLAG_P15_Q03_GREED_PUNISHED` | 371 | 371 | — | state | память | MATCH |
| `FLAG_P15_Q03_LIVING_WATER` | 384 | 384 | — | state | память | MATCH |

Провал P15:90/217/341; отказ P15:60/188/311 — флагов не ставят. Внешних читателей P15 нет; P28 — лор-зависимость `GC-P15-P28-001`.

## 6. Сводные списки §6.3

- **SET без CHECK:** нет. Каждый DONE имеет CHECK в триггере и в финале; каждый state-флаг имеет CHECK в строке финала (повтор-память). У state-флагов CHECK совпадает со SET-строкой, что достаточно для памяти; отдельных «потребителей» в других сценах нет by design.
- **CHECK без SET:** нет внутри P11–P15. Внешние: `FLAG_P05_CHUHAYSTER_KILLED/ABSENT` — SET в P05:87/90, CHECK в P13:216/218/340/342; источник существует. `FLAG_P15_Q03_DONE` CHECK в P15:133; SET в P15:359/371/384. Все CHECK имеют SET.
- **Временные без CLEAR:** нет. Все 60 — `one-shot`/`state` с постоянной памятью; временных (`temp`) в P11–P15 нет. P05 ABSENT — временный, CLEAR в P05:96 (три рассвета); P13 его только читает.
- **CLEAR, стирающие нужное постоянное состояние:** нет. Все CLEAR — `—`.
- **Несколько флагов на одно состояние:** нет. DONE + branch state — разные уровни (завершение + память ветки); взаимоисключение branch-флагов через общий DONE.
- **Недостижимые/несохраняемые состояния:** нет. Все 60 достижимы через соответствующие финалы/отзвуки (см. `QUEST_STATE_MACHINES.md`); все сохраняются постоянно.
- **Циклы повторной награды:** нет. Все финалы гардованы «DONE не активен»; повторные входы — память без наград. P11 Q02 F-A доступен одинокому игроку через побратима (`P11:228`), но это не новый цикл награды.
- **Конфликты/взаимоисключения:** в одном прохождении активен один branch-флаг; DONE общий. Внешние P05 KILLED/ABSENT могут сосуществовать (KILLED постоянный, ABSENT временный) — это семантика P05, не конфликт P13.

## 7. Реестр vs текст: единственное расхождение

| Место | Что говорит реестр | Что говорит текст/карта | Статус |
|---|---|---|---|
| `FLAG_REGISTRY.md:1027` (`FLAG_P14_Q02_FLOTILLA`) | «усі дев'ять порогів пройдено» | `P14:264–265` — «Ненаситець + решта за лоцманом»; `FLAG_DEPENDENCY_MAP.md:83` — то же | **LOW `GA-P14-003`** |

Остальные 59 записей реестра §11–§15 сверены с текстом: SET/CHECK/CLEAR и типы совпадают. Линейные ссылки P11–P15 в реестре проверены выборочно и в целом точны (P11 125/140/157; P12 145/160/174; P13 147/159/171; P14 142/156/168; P15 108/121/134).

## 8. Внешние флаги/зависимости

| Флаг/сутність | SET | CHECK | CLEAR | Статус |
|---|---|---|---|---|
| `FLAG_P05_CHUHAYSTER_KILLED` | P05:87/90 | P13:218/342 | — (постоянный) | CLOSED для P13 |
| `FLAG_P05_CHUHAYSTER_ABSENT` | P05:87/90 | P13:216/340 | P05:96 (три рассвета) | CLOSED для P13 |
| `FLAG_P15_Q03_DONE` (cross-quest) | P15:359/371/384 | P15:133 (Q01-В) | — | MATCH |
| `FLAG_P15_Q01_SERPENT_JUDGE` (cross-quest) | P15:134 | P15:314 (Q03) | — | MATCH |

## 9. Итог

**Флаги P11–P15 — PASS с одной документационной ошибкой.** 60/60 ID имеют полный жизненный цикл; 59/60 записей реестра совпадают с текстом; `FLAG_P14_Q02_FLOTILLA` требует синхронизации (`GA-P14-003`). Внешние P05/P13 закрыты; P28/P34/P26/P20 — вне диапазона.
