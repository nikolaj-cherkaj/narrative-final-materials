# FLAG LIFECYCLE AUDIT — P01–P05 (`820b281`)

**Реестр:** `canon/FLAG_REGISTRY.md` v1.0 — единственный; исторические матрицы не переписаны. Ниже — независимая сверка SET/CHECK/CLEAR по текстам `820b281`.

## 1. Полный цикл (SET → CHECK → CLEAR)

| Флаг | SET | CHECK | CLEAR | Тип | Вердикт |
|---|---|---|---|---|---|
| FLAG_P01_CHARCOAL_DELIVERED / _BURNED | P01:371–372; P02:908 | P01:344/347–348/374; P02:778/912 | взаимный (P01:371–372) | state | OK |
| FLAG_D006_REPENTED | P01:626 (+мітка дня) | P02:991 | — (постоянный доказ; мітка — кулдаун) | state+temp | OK |
| FLAG_D006_REWARDED | P01:628 | P01:629–630 | — one-shot | one-shot | OK |
| FLAG_P01_PANAS_DONE / _FAILED | P01:704–705 | P01:688/697–698/1096–1098 | взаимный | state | OK |
| FLAG_P01_ILARION_PRAYER / _SAVED / _LOST | P01:645/886–887 | P01:882–885/1090–1092 | SAVED/LOST взаимоискл. | state | OK |
| FLAG_P01_RADOMYR_WAIT | P01:836 | P01:837–838 | P01:840 | temp | OK |
| FLAG_SAVA_DEBT_100/50/PAID/DEFAULTED | P01:560–586 | P01:560–586/1101–1109 | единый стан; PAID/DEFAULTED взаимоискл. | state | OK |
| FLAG_P01_OLD_MILL_KNOWN | P01:753 | P01:1006 | — | state | OK |
| FLAG_MYKHAILO_MET / _RUN_01 / _RUN_DONE | P01:994/1005/1008–1009 | P01:750/1006/524/530/1079–1080 | — one-shot (DONE) | state/one-shot | OK |
| FLAG_LORE_01–05_FOUND / _REWARDED | сбор вне P01–P05 / P01:1114 | P01:1112/1116; P06:397 | — one-shot (REWARDED) | state/one-shot | OK |
| FLAG_P02_LISOVYK_KILLED | P02:867 | P01:55/1128–1131; P02:898/940; P04:534/542 | — permanent | permanent | OK |
| FLAG_Q001_GATE/BEACON/SCOUT/GUARD | P02:512 | P02:531/622–624 | — | state | OK |
| FLAG_Q002_PATH_CHOSEN | P02:733 | P02:748 | — (без нового персонажа) | state | OK |
| FLAG_D020_ERRAND_1/2/3 | P02:1079/1131/1178 | P02:1044/1084/1090–1091/1136/1142–1143/1183/1185/990–991 | — one-shot | one-shot | OK |
| FLAG_D020_SWORN | P02:1020 | P04:32; P03:327/469/493 | P03:469/493 (хабар/наліт) | state | OK |
| FLAG_Q021_BRAGA_TRIED/ALLIED/BRIBED | P03:430/450/461 | P03:471; P01:1048–1053 | взаимоискл. | state | OK |
| FLAG_KAZYMIR_SPARED/EXECUTED | P04:638/641/664 | P04:649/657/664/743; P01:592–596/1066–1068 | взаимоискл. | state | OK |
| FLAG_P04_CLASS_CHOSEN (9) | P04:319–343 | P04:349/743 | смена — лишь новый персонаж | state | OK |
| FLAG_P05_CHUHAYSTER_KILLED / _ABSENT | P05:87/90 | P05:94–99; P01:1134–1138 | KILLED — never; ABSENT — 3 світанки | perm+temp | OK |
| FLAG_P05_UPYR_RESTED | P05 BEST-008 (обряд) | P05 повтор; P01 Z-006/Гаврило | — one-shot | one-shot | OK |
| FLAG_ART_001_FOUND / _003_FOUND | P05:367/434 (003 — лише після взяття) | P05:368–369/435–436 | — one-shot | one-shot | OK |
| Внешние (P06_DEBT_*, TALES19, PAGAN22, NALIVAYKO) | вне P01–P05 | P01:1101–1117/1061–1076 | — external | external | OK |

## 2. Контрольные списки (§6.3)

- **SET без CHECK:** нет (все SET читаются; ERRAND_*/MYKHAILO/LORE/ART — CHECK в повторах/реакциях).
- **CHECK без SET:** нет (внешние LORE_01–05/P06_DEBT/TALES/PAGAN/NALIVAYKO — SET вне группы по канону, CHECK корректен; локальных висячих CHECK нет).
- **Temp без CLEAR:** нет (RADOMYR_WAIT — CLEAR P01:840; ABSENT — 3 світанки P05:96; REPENTED-мітка — сутки P01:626).
- **CLEAR, стирающий нужное:** нет (взаимные снятия DELIVERED/BURNED, DONE/FAILED, SAVED/LOST, PAID/DEFAULTED, TRIED/ALLIED/BRIBED, SPARED/EXECUTED — корректны; SWORN CLEAR — только при нарушении + путь покаяния).
- **Несколько флагов — одно состояние:** корректно разделены (KILLED permanent vs ABSENT temp; REWARDED one-shot vs REPENTED state+cooldown; DONE vs FAILED).
- **Недостижимые/несбрасываемые:** нет (все достижимы путями выше; постоянные — намеренно one-shot/permanent).
- **Циклы повторной награды:** нет (D-015/D-006/D-007/PANAS/ART/ERRAND/MYKHAILO — все закрыты флагами).

## 3. Вывод
Жизненный цикл непротиворечив; реестр полон и точен. Дефектов SET/CHECK/CLEAR, требующих правки пакетов, нет.
