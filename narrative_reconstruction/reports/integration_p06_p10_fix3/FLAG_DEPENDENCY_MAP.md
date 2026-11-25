# FLAG DEPENDENCY MAP — P06–P10 (fix3)

Джерело істини: `canon/FLAG_REGISTRY.md` §6–§10. Нижче — стисла карта життєвого циклу; номери рядків — поточний стан після fix3. Тип: `one-shot`, `state`, `temp`.

## P06 — 16 ID

| ID | SET | CHECK | CLEAR | Тип / зовнішнє |
|---|---|---|---|---|
| `FLAG_SOC_WED_STARTED` | P06:83 | P06:91; 155/159/163 | P06:90; 155/159/163; 83 (лише разом із BROKEN/CONSENT) | state |
| `FLAG_SOC_WED_COMPLETED` | P06:90 | P06:104–105; 126 | P06:155/159/163; P06:83 НЕ знімає | state |
| `FLAG_SOC_WED_BROKEN` | P06:155/159/163 | P06:166; 126 | P06:83/90; 166 | state |
| `FLAG_SOC_DIVORCE_CONSENT` | P06:155 | P06:83 | P06:83 | one-shot у межах розриву |
| `FLAG_SOC_DIVORCE_BETRAYAL` | P06:159 | P06:159; 166 | P06:159; 166; P06:83 НЕ знімає | state до прощення |
| `FLAG_SOC_DIVORCE_SEAL` | P06:163 | P06:168 | P06:166 | state (борг храму) |
| `FLAG_SURV_FAINTED` | P06:226 | P06:226 | — | state (пам'ять) |
| `FLAG_CRAFT_BLADE_LOST` | P06:278 | P06:288 | P06:286 | state |
| `FLAG_CRAFT_BLADE_REFORGED` | P06:286 | P06:288 | — | state |
| `FLAG_P06_DEBT_PAID_ARMOR` | P06:311/317 | P01:1104 | — | one-shot; ⤴ P01 |
| `FLAG_P06_DEBT_WORKED_OFF` | P06:314/317 | P01:1106 | — | one-shot; ⤴ P01 |
| `FLAG_P01_SAVA_DEBT_50` | P01:563 | P06:295; P01:580 | P06:311/314/317/320 | state; ⤴ P01 |
| `FLAG_P01_SAVA_DEBT_100` | P01:560 | P06:295; P01:580 | P06:311/314/317/320 | state; ⤴ P01 |
| `FLAG_P01_SAVA_DEBT_PAID` | P06:311/314/317 | P01:1102–1107 | P01:586 (новий займ/дефолт) | state; ⤴ P01 |
| `FLAG_P01_SAVA_DEBT_DEFAULTED` | P06:317/320 | P01:580 | P01:582/585 | state; ⤴ P01 |
| `FLAG_LORE_01_FOUND` … `FLAG_LORE_05_FOUND` (5 ID) | P06:338/354/368/383/397 | P06:407; P01:1112 | — | one-shot кожен |

**Ключові інваріанти:** `PAID` і `DEFAULTED` взаємовиключні; напад на Хому тепер знімає активний `_50`/`_100` і `PAID` (захисно) перед SET `DEFAULTED`; погашення після дефолту — лише P01:580–585.

## P07 — 8 ID

| ID | SET | CHECK | CLEAR | Тип |
|---|---|---|---|---|
| `FLAG_P07_PROF001_DONE` | P07:152/164/176 | P07:65; 101–102 | — | one-shot |
| `FLAG_P07_SOM_SOLD` | P07:164 | P07:102 | — | state, взаємовикл. з FREED |
| `FLAG_P07_SOM_FREED` | P07:176 | P07:102; 175 | — | state, взаємовикл. з SOLD |
| `FLAG_P07_PROF002_DONE` | P07:268/280/292 | P07:185; 217 | — | one-shot |
| `FLAG_P07_ACONITE_SOLD` | P07:292 | P07:218 | — | state |
| `FLAG_P07_PROF003_DONE` | P07:385/397/409 | P07:302; 334; 358 | — | one-shot |
| `FLAG_P07_DUN001_DONE` | P07:423 (TECH) + P07:494 (епілог) | P07:451 | — | one-shot |
| `FLAG_P07_DUN002_DONE` | P07:500 (TECH) + P07:566 (епілог) | P07:526 | — | one-shot |

**Виправлено:** DUN-флаги тепер мають явний SET у рядку «Прапорці:» епілогу боса, а не лише в TECH-паспорті.

## P08 — 18 ID

| ID | SET | CHECK | CLEAR | Тип |
|---|---|---|---|---|
| `FLAG_P08_MAIN001_SEAL_DONE` | P08:97 | P08:22; 98; 131 | — | one-shot |
| `FLAG_P08_MAIN001_WARD_DONE` | P08:110 | P08:22 | — | one-shot |
| `FLAG_P08_MAIN001_ASH_DONE` | P08:121 | P08:22 | — | one-shot |
| `FLAG_P08_PRAYER_KNOWN` | P08:49; 22 | P08:295; 330 | — | state |
| `FLAG_P08_MAIN002_DONE` | P08:208/221/233 | P08:131 | — | one-shot |
| `FLAG_P08_GRAMOTA_DELIVERED` | P08:221 | P08:221 | — | state, взаємовикл. з SOLD |
| `FLAG_P08_GRAMOTA_SOLD` | P08:233 | P08:233 | — | state, взаємовикл. з DELIVERED |
| `FLAG_P08_MAIN003_DONE` | P08:325/337/350 | P08:243 | — | one-shot |
| `FLAG_P08_EYE_PRAYED` | P08:337 | P08:337 | — | state, взаємовикл. з FORGED |
| `FLAG_P08_EYE_FORGED` | P08:350 | P08:350 | — | state, взаємовикл. з PRAYED |
| `FLAG_P08_MAIN004_DONE` | P08:435/447/458 | P08:358 | — | one-shot |
| `FLAG_P08_BASTION_BLOWN` | P08:447 | P08:447; 509 | — | state, взаємовикл. з RAIDED |
| `FLAG_P08_BASTION_RAIDED` | P08:458 | P08:458 | — | state, взаємовикл. з BLOWN |
| `FLAG_P08_MAIN005_DONE` | P08:545/558/570 | P08:468 | — | one-shot |
| `FLAG_P08_PACT_KEEPER` | P08:558 | P08:558 | — | state, взаємовикл. з REBORN |
| `FLAG_P08_REBORN_SPRING` | P08:570 | P08:570 | — | state, взаємовикл. з PACT |
| `FLAG_P08_RIT001_NIGHTSENSE` | P08:619 | P08:587 | P08:619 (наступна повня) | temp |
| `FLAG_P08_RIT002_BOUND` | P08:661 | P08:630 | P08:661 (кров невинного) | state |

**Виправлено:** `PRAYER_KNOWN` має CHECK на спуску (P08:295) і в умові фіналу Б (P08:330); вхід у ковальську гілку тепер має явний Варіант 4 (P08:273).

## P09 — 11 ID

| ID | SET | CHECK | CLEAR | Тип |
|---|---|---|---|---|
| `FLAG_P09_Q01_DONE` | P09:140/155/170 | P09:27 | — | one-shot |
| `FLAG_P09_Q01_MARA_MARKED` | P09:140 | P09:140 | — | state (незнімний знак) |
| `FLAG_P09_Q01_SHRINE_BURNED` | P09:155 | P09:155 | — | state |
| `FLAG_P09_Q01_TRICKSTER` | P09:170 | P09:170 | — | state (канон) |
| `FLAG_P09_Q02_DONE` | P09:296/310/323 | P09:192 | — | one-shot |
| `FLAG_P09_Q02_WEDDING_BELOW` | P09:296 | P09:296 | — | state |
| `FLAG_P09_Q02_ASHED` | P09:310 | P09:310 | — | state |
| `FLAG_P09_Q02_JUDGED` | P09:323 | P09:323 | — | state (канон) |
| `FLAG_P09_Q03_DONE` | P09:436/451/465 | P09:345 | — | one-shot |
| `FLAG_P09_Q03_BURNED` | P09:451 | P09:451 | — | state, взаємовикл. з PACT |
| `FLAG_P09_Q03_PACT` | P09:465 | P09:465 | — | state; ⤴ P24 (P21–P25) |

**Виправлено:** перевидача персня — один раз при неактивному Q02_DONE (P09:228); воск/смола — [0/1] у чек-листі (P09:262–263); табір обложників має сетап (P09:368).

## P10 — 12 ID

| ID | SET | CHECK | CLEAR | Тип |
|---|---|---|---|---|
| `FLAG_P10_Q01_DONE` | P10:133/149/165 | P10:29 | — | one-shot |
| `FLAG_P10_Q01_CHAMPION` | P10:133 | P10:133 | — | state |
| `FLAG_P10_Q01_BROTHERHOOD` | P10:149 | P10:149 | — | state |
| `FLAG_P10_Q01_DONATION` | P10:165 | P10:165 | — | state |
| `FLAG_P10_Q02_DONE` | P10:287/301/316 | P10:190 | — | one-shot |
| `FLAG_P10_Q02_PATH` | P10:287 | P10:287 | — | state |
| `FLAG_P10_Q02_HELM` | P10:301 | P10:301 | — | state |
| `FLAG_P10_Q02_RESERVE` | P10:316 | P10:316 | — | state |
| `FLAG_P10_Q03_DONE` | P10:443/458 | P10:339 | — | one-shot |
| `FLAG_P10_Q03_ARMOR` | P10:443 | P10:443 | — | state, взаємовикл. з BLADE |
| `FLAG_P10_Q03_BLADE` | P10:458 | P10:458 | — | state, взаємовикл. з ARMOR |
| `FLAG_P10_Q03_ARTEL` | P10:472 | P10:472 | — | state, сумісний з ARMOR/BLADE |

**Виправлено:** тавро Михея більше не є CHECK без SET — сплата фіксується в книзі турніру (P10:78), тавро лише видимий знак; втрата тавра не дає безкоштовного допуску (P10:100).

## Виявлені та закриті дефекти

| Дефект | Було | Стало |
|---|---|---|
| Реєстр SOC overclaim | P06:83 нібито знімає COMPLETED/BETRAYAL | CLEAR виправлено; пакет і реєстр збігаються |
| Борг Сави, напад | DEFAULTED без CLEAR | CLEAR `_50`/`_100` + `PAID`, SET `DEFAULTED` |
| DUN SET | лише TECH | явний рядок «Прапорці:» в епілозі |
| PRAYER gate | CHECK без явного SET | SET 49/22, CHECK 295/330 |
| Коваль P08 | без репліки гравця | Варіант 4 |
| Воск/смола | поза чек-листом | [0/1], ціна-приклад, аудіо-якір |
| Тавро P10 | CHECK без SET | книга турніру |
| Перстень P09 | «востаннє» без межі | одна перевидача при неактивному DONE |
| P09:141 | лише «золото» | звук/запах |
| Реєстр §6 | дрейф +4…+6 | перенумеровано |

**Підсумок:** 65 ID; orphan-флагів немає; CHECK без SET у P06–P10 не залишилось; тимчасові флаги мають CLEAR; єдина зовнішня лінія — PACT → P24.
