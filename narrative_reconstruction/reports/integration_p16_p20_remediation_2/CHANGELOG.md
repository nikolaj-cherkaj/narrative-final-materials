# CHANGELOG — ремонт P16–P20 за аудитом `dac3696` (другий цикл)

**Дата:** 2026-11-25
**Гілка:** `agent/integration-p16-p20-fix-dac3696`
**База:** `dac3696` (звіти аудиту) від `17105ac` (інтеграція + рішення власника B)

## Додано

- `reports/integration_p16_p20_remediation_2/` — повний комплект звітів другого циклу.
- `original_backup/naratyvni_teksty_paket_19_pre_remediation_p16_p20_remediation2_2026-11-25.md`
- `original_backup/naratyvni_teksty_paket_20_pre_remediation_p16_p20_remediation2_2026-11-25.md`

## Змінено

### Пакети

- `revised/naratyvni_teksty_paket_19.md` — GA-P19-003: етап 1 п.4 (ніж/вода Хими), розвилка етапу 3 А/Б/В, умова/дія фіналу В (з етапу 1).
- `revised/naratyvni_teksty_paket_20.md` — GA-P20-012 (D1 сигнал/12/розвилка/XOR), GA-P20-013 (D2 вівтар/ніша/розвилка/XOR, LIFELINE лише Б), GA-P20-014 (D3 1–6-й А/Б, 7-й В, нагорода 7-го лише у В, трекер), GA-P20-015 (W2 гармати напоготові/розвилка/XOR).

### Канон і реєстри

- `canon/FLAG_REGISTRY.md` — v2.10: шапка (69ee62a/17105ac/dac3696), SET-описи DAILY01/DALIY02/DAILY03/STREAK_7/WEEKLY02 + KNIGHT (джерело ножа/води); семантика LIFELINE B — без змін.
- `reports/GLOBAL_CARRYOVER_REGISTER.md` — шапка (17105ac/dac3696); §2.7/§3.1/історія — без видалення.
- `reports/integration_p16_p20_fix/` — GA-DOC-001: `REMEDIATION_RESULT.md:6` (14 FIXED), `CARRYOVER_HANDOFF.md:31/33` (FIXED/B), `OWNER_DECISION_BRIEF.md` (superseded by 17105ac), `CHANGELOG.md:33`/`INTEGRATION_REPORT.md:162` («рішенням»).

## Не змінено

- P15, P16, P17, P18, P21–P25, P26–P30 та інші зовнішні пакети.
- Числові нагороди, XP, валюта, репутація, карма, ресурси, економіка.
- Затверджений канон персонажів, локацій, фракцій і механік; LIFELINE варіант B.
- Історичні аудити й попередні резервні копії (не перезаписувалися).
- Нові технічні ID, предмети, нагороди, наслідки — не вводилися.

## Підсумок

- MEDIUM: 5 `FIXED`.
- LOW (документація): 1 `FIXED`.
- OBS: 4 `ACCEPTED_NONBLOCKING` (без правок пакетів).
- Регресії: не знайдено.
