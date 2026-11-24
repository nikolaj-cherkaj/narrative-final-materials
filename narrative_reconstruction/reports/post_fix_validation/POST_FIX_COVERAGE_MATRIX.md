# POST-FIX COVERAGE MATRIX — охоплення і докази

| Вимога 1.txt | Де перевірено | Доказ |
|---|---|---|
| 4 HIGH, 12+11+10 сценаріїв (Q-030, арени, борг, Око) | Q030/P02_ARENA/DEBT/P08 звіти + вихідники з рядками | Цитати + таблиці PASS |
| 17 MEDIUM + 9 LOW, кожен з рядками | ISSUE_VERIFICATION_MATRIX + вибіркові цитати вище | Файл:рядок:цитата для кожного ID |
| 7 рішень власника B1–B7 | OWNER_DECISIONS_POST_FIX | Файл:рядок для кожного |
| D-006 (§6) | OWNER_DECISIONS_POST_FIX + P01:603/P02:989,1007 | Daily послідовно; doc-розбіжність зафіксована |
| Флаги SET/CLEAR/CHECK | FLAG_LIFECYCLE_POST_FIX | Ключові цикли |
| Залежності | REGRESSION_AUDIT + FLAG_LIFECYCLE | 11 ключових ребер |
| 36 пакетів | PACKAGE_READINESS + REGRESSION_AUDIT | 36/36 |
| TTS P24/P25/P28/P18 | TTS_MANUAL_TEST_CHECKLIST (NOT TESTABLE) | Структура PASS, прослуховування — чек-лист |
| Числа (не підміняти аудит) | BALANCE_CALIBRATION_DEBT | Структурно PASS, баланс PENDING |
| Формальна методика (§11) | Таблиці крок/стан/дія/очікуване/фактичне в Q030/ARENA/DEBT/P08 | Присутні |
| SHA-маніфест | POST_FIX_CHECKSUMS.sha256 | Згенеровано з вихідників HEAD 014c43b |

## Обмеження (чесно)

- Повна state-machine 240 сцен не будувалась.
- Повний grep усіх 385 NPC не виконувався; перевірено ключових + реєстрові твердження fix (дубль NPC-0428).
- Флаги: ключові цикли повністю; другорядні — вибірково.
- Рантайм/TTS-аудіо — NOT TESTABLE.
- Баланс — PENDING.
