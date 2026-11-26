# ЖУРНАЛ ЗМІН — Інтеграція P31–P36 (2026-11-26)

**Гілка:** `agent/integration-p31-p36-fix-c21dbd1` (від `c21dbd1c1bd60b1cf7628395f9304818678207be`)
**База:** P36 `agent/package-p36-20261126-f4982f4`
**Дата:** 2026-11-26

## Файли

- `narrative_reconstruction/revised/naratyvni_teksty_paket_31.md` — виправлено «ОБЕРІГІВ» → «ОБЕРЕГІВ»; додано «Розв'язку» HEARTH-31-01, «Третій шлях» HEARTH-31-03, «Розв'язку» HEARTH-31-04 і HEARTH-31-05; кінь Збишка передано громаді, нагорода — запасний скакун; «Збишко» → «Збишек»; «бере її заміж» → «одружується з нею»; «прийме на себе» → «візьме на себе»; fail-loop HEARTH-31-01 отримав перехід до фіналу В.
- `narrative_reconstruction/revised/naratyvni_teksty_paket_32.md` — знято взаємовиключення `TRAP`/`GROVE`; відлуння після засідки тепер дає обидві пам'яті.
- `narrative_reconstruction/revised/naratyvni_teksty_paket_33.md` — Хуха веде «за писком і шелестом хутра», а не «за слідами».
- `narrative_reconstruction/revised/naratyvni_teksty_paket_34.md` — орієнтація в «Закрученому Степу» за теплом сонця, запахом полину й вітром; «обух ковадла» → «обух клевця», сетап — ковадло + важкий клевець.
- `narrative_reconstruction/revised/naratyvni_teksty_paket_36.md` — арифметика прикладів ECON-36-04: 1500 → 3000 (діалог, фінал А, підсумок).
- `narrative_reconstruction/canon/FLAG_REGISTRY.md` — v2.31: §32 `TRAP`+`GROVE`, покриття P32, §0 `GC-P14-P34-001` → `CLOSED`, додано рядок інтеграції P31–P36.
- `narrative_reconstruction/canon/CHARACTERS.md` — §2 «421 записів»; NPC-0431 «одружується з нею».
- `narrative_reconstruction/reports/GLOBAL_CARRYOVER_REGISTER.md` — §2.11, §3.4, §1, історія оновлень.
- `narrative_reconstruction/reports/integration_p31_p36/` — `INTEGRATION_REPORT.md`, `FINDINGS_STATUS_MATRIX.md`, `CROSS_PACKAGE_DEPENDENCY_MAP.md`, `FLAG_INTEGRATION_AUDIT.md`, `OWNER_QUESTIONS.md`, `CARRYOVER_STATUS.md`.
- `narrative_reconstruction/original_backup/` — 9 резервних копій до інтеграції (6 пакетів + FLAG_REGISTRY + CHARACTERS + GLOBAL_CARRYOVER_REGISTER).

## Прапорці

- Усі 78 ID P31–P36 звірено з текстами й реєстром.
- Виправлено єдину конфліктну комбінацію: `FLAG_P32_Q03_TRAP` + `FLAG_P32_Q03_GROVE`.
- Підтверджено сумісність `FLAG_P33_Q03_HUT` + `FLAG_P33_Q03_BLESSING`.
- Підтверджено взаємовиключність NALIVAYKO-станів; `LAST_STAND` термінальний.
- Зовнішній споживач — лише P01 D-015; `STORM`/`CAUSEWAY` — OBS.

## Причини

- Прохідність: явні вибори для фіналів P31, перехід до фіналу В, візуальні навігаційні гейти P33/P34.
- Канон: предметна логіка коня Збишка; арифметика прикладів P36; `GC-P14-P34-001` закрито.
- Доступність: P33 «сліди» → звук; P34 «сонце/компас» → тепло/запах/вітер.
- Мова: 5 локальних виправлень; без масової уніфікації.
- Документація: 421 запис, синхронізація реєстрів.

## Вплив на інші пакети

- P01: не змінено; D-015 читає NALIVAYKO-стани.
- P05/P21: не змінено; умовна репліка про Соловейка лишається.
- P13/P14: не змінено; Арідник і Пектораль узгоджені.
- P28/P35: не змінено; Сом-Людожер розведений із Цар-Сомом.
- P10/P29/P36: не змінено; Лейби розведені.
- P32/P36: не змінено; `STORM`/`CAUSEWAY` — OBS.

## Невирішене

- Відкритих CRITICAL/HIGH/MEDIUM: 0.
- OBS: 9 (4 передано, 5 прийнято).
- Питання власнику: 0.
- TTS і баланс не тестувалися; числові нагороди — приклади.
