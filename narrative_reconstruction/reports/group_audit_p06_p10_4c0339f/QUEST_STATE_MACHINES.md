# QUEST STATE MACHINES — P06–P10 (`4c0339f`)

## SOC-001 (свадьба): IDLE → STARTED → COMPLETED
- IDLE --[условия P06:50–55 + згода]--> STARTED (SET P06:83; CLEAR BROKEN/CONSENT; COMPLETED/BETRAYAL/SEAL НЕ трогаются).
- STARTED --[клятвы + Крок 3]--> COMPLETED (SET P06:90; CLEAR STARTED/BROKEN).
- STARTED --[разошлись]--> STARTED (P06:91, повтор с Кроку 1).
- COMPLETED --[«ви вже зв'язані»]--> отказ нового старта (P06:104–105) → только через SOC-002.
- Допущения: смерть/возрождение состояние не меняют (обрядна пам'ять).

## SOC-002 (развод): COMPLETED → {CONSENT|BETRAYAL|SEAL} + BROKEN
- COMPLETED --[обоюдно]--> CONSENT+BROKEN, CLEAR COMPLETED/STARTED (P06:155).
- COMPLETED --[измена]--> BETRAYAL+BROKEN, CLEAR COMPLETED/STARTED; прощение → CLEAR BETRAYAL (P06:159/166).
- COMPLETED --[нема срібла]--> SEAL+BROKEN, CLEAR COMPLETED/STARTED (P06:163); сплата/прощение → CLEAR SEAL+BETRAYAL (P06:166); BROKEN → CLEAR новым союзом (P06:83/90).
- Недоопределённость: зрада+несплата одновременно (только снятие парой, без SET пары) — безвредно.

## CRAFT-002 (долг Савы): DEBT_50|100 → {PAID(+путь)|DEFAULTED} → PAID
- _50/_100 --[В1 обладунок, P06:311]--> PAID+PAID_ARMOR (CLEAR _50/_100).
- _50/_100 --[В2 робота, P06:314]--> PAID+WORKED_OFF (CLEAR _50/_100; отказ mid-work → назад к В3).
- _50/_100 --[В3 отказ утром, P06:317]--> DEFAULTED (CLEAR _50/_100; PAID не трогается).
- _50/_100 --[нападение, P06:320]--> DEFAULTED (CLEAR не прописан → GA-P06-002).
- DEFAULTED --[грішми/доспехом/роботою через Саву/Миколу/Хому, P01:580–585]--> PAID (CLEAR _50/_100+DEFAULTED). В P06 путь — отсылкой (GA-P06-010).
- Новая позика — только без активного борга/DEFAULTED (P01:586).

## LORE-001–005: 5× FOUND → D-015 REWARDED
- Каждый сувой: SET FOUND (P06:338/354/368/383/397) → проверка 5/5 (P06:407) → выплата только P01:1114 (REWARDED, one-shot). P06 не выдаёт. Цикл завершается.

## P07: PROF-001/002/003 (DONE + взаимоискл. памяти)
- IDLE --[триггер !DONE]--> ACT I (В1/В2/В3) → ACT II (счётчики [0/N]) → выбор → DONE+память (SOLD/FREED, ACONITE_SOLD) → повтор только память. Провал → Fail-Loop без флага. DUN-001/002: IDLE → DONE (TECH SET) → повтор без артефакта, вход раз в сутки.

## P08: MAIN-001 (3 сумісні DONE) → MAIN-002 (гейт SEAL) → MAIN-003/004/005 (вільні)
- MAIN-001: IDLE → SEAL_DONE (A) / WARD_DONE (Б) / ASH_DONE (В); триггер «доки хоч один не активний»; все три → узвар/нічліг + молитва по запросу (PRAYER_KNOWN SET P08:49/22).
- MAIN-002: требует SEAL_DONE → DONE + DELIVERED/SOLD (взаимоискл.).
- MAIN-003: требует !DONE; гейт PRAYER_KNOWN (P08:293) → DONE + PRAYED/FORGED. Вход коваля — без реплики игрока (GA-P08-004).
- MAIN-004: → DONE + BLOWN/RAIDED; BLOWN → обход в MAIN-005 (P08:507).
- MAIN-005: → DONE + KEEPER/SPRING; Око рекомендовано, не обязательно (P08:466).
- RIT-001: !NIGHTSENSE → успех (SET, CLEAR повня) / зрив (без флага). RIT-002: !BOUND → успех (SET, CLEAR кровь невинного) / зрив (без флага).

## P09: 3× (DONE + взаимоискл.)
- Q01: → DONE + MARA/SHRINE/TRICKSTER. Q02: → DONE + WEDDING/ASHED/JUDGED (финал Б требует воск+смола вне чек-листа → GA-P09-005). Q03: → DONE + BURNED/PACT (PACT → внешний P24).

## P10: 3× (DONE + взаимоискл. + ARTEL-продовження)
- Q01: взнос/тавро (без флага → GA-P10-006) → DONE + CHAMPION/BROTHERHOOD/DONATION.
- Q02: → DONE + PATH/HELM/RESERVE (форпост — одна реплика сетапа → GA-P10-008).
- Q03: → DONE + ARMOR/BLADE → ARTEL при активном DONE (совместим).
