# КАРТА ФЛАГІВ І СТАНІВ P06–P10 fix2 — «Дике Поле»

Джерело: `FLAG_REGISTRY.md` (§§6–10; §8 — 18 ID з `PRAYER_KNOWN`). Кожен ID перевірено за текстом. Тип: one-shot/state/temp. Числа — приклади.

## P06 (16 ID; зміни fix2)

- `SOC_WED_STARTED`: SET 83; CHECK 91; CLEAR 90. 🔧2: BROKEN/CONSENT знімаються, COMPLETED/BETRAYAL/SEAL — ні.
- `SOC_WED_COMPLETED`: SET 90; CHECK 106/120; CLEAR — (тільки суд SOC-002). 🔧2: 83 не зносить.
- `SOC_WED_BROKEN`: SET 149/153/157; CHECK 160; CLEAR 83/90/160.
- `DIVORCE_CONSENT`: SET 149; CLEAR 83. / `DIVORCE_BETRAYAL`: SET 153; CLEAR 153/160 (прощення). / `DIVORCE_SEAL`: SET 157; CLEAR 160 (сплата/прощення). 🔧2: 83 їх не чіпає.
- `SURV_FAINTED`: SET/CHECK 220; CLEAR —.
- `CRAFT_BLADE_LOST/REFORGED`: SET 272/280; взаємовиключні.
- `P06_DEBT_PAID_ARMOR/WORKED_OFF`: SET 305–311; CHECK P01:1104/1106; CLEAR —. 🔧2: знімають лише активний борг; PAID не чіпається.
- `LORE_01–05_FOUND`: SET 329/345/359/374/388; CHECK 398+P01:1112; виплата лише P01:1114 (REWARDED). 🔧2: репліка — з посиланням на D-015.
- Зовнішні: `P01_SAVA_50/100` (CHECK 295; CLEAR/SET 311–317, модель C), `P05_UPYR_RESTED` (CHECK 48), `P04_CLASS_CHOSEN` (реакція 280).

## P07 (8 ID; зміни fix2 — текст без нових ID)

- `PROF001_DONE` (150/162/174) + `SOM_SOLD`/`SOM_FREED`; `PROF002_DONE` (264/276/288) + `ACONITE_SOLD`; `PROF003_DONE` (379/391/403; 🔧2: без «нового Серця»); `DUN001/DUN002_DONE` (417/493; раз на добу). Гостинність після DONE — не нагорода [TECH].

## P08 (18 ID; +1 fix2)

- `MAIN001_SEAL/WARD/ASH_DONE` (97/110/121; сумісні). 🔧2: тригер «доки хоч один»; мак — 1 торбинка/фінал.
- `P08_PRAYER_KNOWN` (state-знання): SET 49/22; CHECK 326 + спуск (293); CLEAR —. 🔧2 NEW.
- `MAIN002_DONE` (208/221/233; вхід — SEAL) + `GRAMOTA_DELIVERED/SOLD`.
- `MAIN003_DONE` (321/333/346) + `EYE_PRAYED/FORGED` (сварка→Трохим 🔧2).
- `MAIN004_DONE` + `BASTION_BLOWN/RAIDED` (🔧2: BLOWN → обхід у MAIN-005).
- `MAIN005_DONE` + `PACT_KEEPER/REBORN_SPRING` (🔧2: тригер рекомендує Око; варта — лор).
- `RIT001_NIGHTSENSE` (temp, повня), `RIT002_BOUND` (state, кров невинного; кістка — будь-яка ватажка 🔧2).

## P09 (11 ID; перейменувань ID нема)

- `Q01_DONE` + MARA/SHRINE/TRICKSTER; `Q02_DONE` + WEDDING/ASHED/JUDGED (🔧2: перстень — перевидача; свідки; порядок; золотий весільний); `Q03_DONE` + BURNED/PACT (🔧2: фінал В; хід; фільтри; вогонь).

## P10 (12 ID; без новых)

- `Q01_DONE` + CHAMPION/BROTHERHOOD/DONATION (🔧2: «усю грошову»; тавро; вигнання); `Q02_DONE` + PATH/HELM/RESERVE (🔧2: мотузка; промах; бранці); `Q03_DONE` + ARMOR/BLADE + ARTEL (🔧2: відпрацювання/гроза/скриня).

## Помилки: не виявлено

Орфани/фарм/стираючі CLEAR — закрито. Реєстр синхронізовано (61 група = текстам). `PRAYER_KNOWN` — єдиний новий ID циклу.
