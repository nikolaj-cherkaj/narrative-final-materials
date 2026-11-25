# FLAG LIFECYCLE AUDIT — P06–P10 (SET/CHECK/CLEAR)

**HEAD:** `c3aca43`. Источник истины текстов — пакеты; сверено с `FLAG_REGISTRY.md` v1.5 §§6–10. Тип: one-shot/state/temp. Числа — примеры TBD.

## P06 (16 ID)

- SOC_WED_STARTED (state): SET 83; CHECK 91; CLEAR 90/149/153/157/83. GA-P06-F1/F7: CLEAR BETRAYAL/SEAL/COMPLETED в 83 — избыточен, убрать.
- SOC_WED_COMPLETED (state): SET 90; CHECK 106/120; CLEAR 83/149/153/157.
- SOC_WED_BROKEN (state): SET 149/153/157; CHECK 160; CLEAR 83/90/160.
- DIVORCE_CONSENT (state): SET 149; CHECK 83/133; CLEAR 83.
- DIVORCE_BETRAYAL (state до прощения): SET 153; CHECK 153/160; CLEAR 83*/153/160 (*83 — убрать).
- DIVORCE_SEAL (state-борг): SET 157; CHECK 162; CLEAR 83*/160 (*83 — убрать).
- SURV_FAINTED (state-память): SET 220; CHECK 220; CLEAR —.
- CRAFT_BLADE_LOST/REFORGED (state, взаимоисключ.): SET 272/280; CHECK 282; CLEAR взаимный.
- P06_DEBT_PAID_ARMOR/WORKED_OFF (one-shot пути): SET 305/311 и 308/311; CHECK P01:1104/1106; CLEAR —. GA-P06-F2: не чистить неактивный PAID.
- LORE_01–05_FOUND (state каждый): SET 329/345/359/374/388; CHECK 398 + P01:1112; CLEAR —. Выплата только P01:1114 (GA-P06-F3).
- Внешние: CHECK 289 (P01_SAVA_50/100 без DEFAULTED), 48 (P05_UPYR_RESTED), 280 (P04_CLASS_CHOSEN — лишь реакция). CLEAR/SET P01-долгов 305/308/311 — модель C.

## P07 (8 ID)

- PROF001_DONE (one-shot): SET 150/162/174; CHECK 65/99+; CLEAR —. +SOM_SOLD (162; CHECK 99; vs FREED) / SOM_FREED (174; CHECK 99/173; vs SOLD).
- PROF002_DONE: SET 264/276/288; CHECK 183/214; CLEAR —. +ACONITE_SOLD (288; CHECK 214).
- PROF003_DONE: SET 379/391/403; CHECK 298/329; CLEAR —. GA-P07-F1: «новое Серце после грозы» (352) vs блок (298/329) — убрать фразу.
- DUN001_DONE: SET 417; CHECK 445–446 + раз в сутки; CLEAR —. DUN002_DONE: SET 493; CHECK 519–520; CLEAR —.
- Провалы/отказы флаги не ставят; повторы — без реликвий.

## P08 (17 ID)

- MAIN001_SEAL/WARD/ASH_DONE (one-shot, совместимые): SET 97/110/121; CHECK 22 (+98/131 для SEAL→MAIN-002); CLEAR —. GA-P08-F5: триггер «до першого» переформулировать; мак — 1 мішечок/финал.
- MAIN002_DONE: SET 208/221/233; CHECK 131; CLEAR —. +GRAMOTA_DELIVERED (221; vs SOLD) / GRAMOTA_SOLD (233; vs DELIVERED).
- MAIN003_DONE: SET 321/333/346; CHECK 243; CLEAR —. +EYE_PRAYED (333; vs FORGED) / EYE_FORGED (346; vs PRAYED). GA-P08-F1: добавить PRAYER_KNOWN (SET 49/22, CHECK 326). GA-P08-F6: CHECK молитвы до спуска.
- MAIN004_DONE: SET 431/443/454; CHECK 354; CLEAR —. +BASTION_BLOWN (443; CHECK только своя строка — GA-P08-F3/F7: добавить потребителя в MAIN-005) / BASTION_RAIDED (454; vs BLOWN).
- MAIN005_DONE: SET 541/554/566; CHECK 464; CLEAR —. +PACT_KEEPER (554; vs REBORN; GA-P08-F8: варта без квеста) / REBORN_SPRING (566; vs KEEPER).
- RIT001_NIGHTSENSE (temp): SET 615; CHECK 583; CLEAR следующая повня; срыв — без флага.
- RIT002_BOUND (state): SET 657; CHECK 626; CLEAR кровь невинного; срыв — трещина, без флага. GA-P08-F4: кістка — «будь-яка ватажка».

## P09 (11 ID)

- Q01_DONE: SET 140/155/170; CHECK 27; CLEAR —. +MARA_MARKED (140, незнімне) / SHRINE_BURNED (155) / TRICKSTER (170, канон) — взаимоисключ.
- Q02_DONE: SET 294/308/321; CHECK 192; CLEAR —. +WEDDING_BELOW (294) / ASHED (308) / JUDGED (321). GA-P09-F1/F3: перстень — явная перевидача; свидетели/золото/порядок.
- Q03_DONE: SET 434/449/463; CHECK 343; CLEAR —. +BURNED (449; vs PACT) / PACT (463; внешний P24). GA-P09-F3: ход пакту описать; «відлуння» = финал.
- Провалы/отказы — без флагов.

## P10 (12 ID)

- Q01_DONE: SET 133/149/165; CHECK 29; CLEAR —. +CHAMPION/BROTHERHOOD/DONATION — взаимоисключ.
- Q02_DONE: SET 287/301/316; CHECK 190; CLEAR —. +PATH/HELM/RESERVE — взаимоисключ.
- Q03_DONE: SET 442/457; CHECK 339; CLEAR —. +ARMOR/BLADE — взаимоисключ; +ARTEL (471; при DONE; совместим).
- Провалы/отказы — без флагов; повторы — память.

## Сводные списки

- SET без CHECK: BLOWN в MAIN-005 (GA-P08-F3); GRAMOTA/EYE/SOM/памятии P09/P10 — CHECK лишь в своей строке (будущие потребители заявлены).
- CHECK без SET: молитва P08 (GA-P08-F1); расходники (вода/єлей/мёд/мак/полын) — нарративные, без флагов-инвентаря; «раз на сутки» DUN — без флага.
- Temp без CLEAR-флага: RIT001 (календарная повня — OBS).
- CLEAR стирающие постоянное: P06:83 (GA-P06-F1/F7); P06:311 PAID (GA-P06-F2).
- Недостижимые: второе Серце (GA-P07-F1); пост-дефолт в P06 (только D-005).
- Циклы повторной награды: закрыты DONE; остаток — бесконечные юшка/ночлег (GA-P07-F2 LOW).
- Реестр: пропущенных/дублирующих ID нет; расхождение лишь подсчёт GA-REG-F1 (60 групп vs физики).
