# PACKAGE READINESS MATRIX V2 — FOUNDATION FREEZE
## Готовность 36 пакетов к художественной редактуре

**Версия:** `ac2b8de48a74186a1c43dca18882d0e080200366`  
**Статусы:** `READY` — полностью проверен, проблем нет; `READY WITH MINOR ISSUES` — только MEDIUM/LOW, не блокируют редактуру; `BLOCKED` — есть HIGH-проблема; `NOT FULLY AUDITED` — не присвоен ни одному пакету.  
**Связанные отчёты:** `FOUNDATION_FREEZE_REPORT.md`, `AUDIT_COVERAGE_MATRIX.md`, `FLAG_LIFECYCLE_MATRIX.md`.

---

## 1. Матрица

| Пакет | Полностью проверен | Квесты/сцены | Флаги | Зависимости | Найденные проблемы | Критические блокеры | Статус |
|---|---|---|---|---|---|---|---|
| P01 | Да | Z-001…Z-013, D-001…D-015; мини-квесты D-005/D-006/D-011 | 34 упоминания; ключевые `SAVA_DEBT_*`, `ILARION_*`, `CHARCOAL_*`, `LISOVYK`, `CHUHAYSTER`, `UPYR` | P06 долг, P02 LISOVYK, P05 UPYR/CHUHAYSTER, P03 Q-021, P19/P22/P31 слухи, P08 Радомир | FF-HIGH-P01-P06-DEBT-001; FF-LOW-P01-D015-001; FF-LOW-P01-P06-LORE-001 | HIGH: долг | **BLOCKED** |
| P02 | Да | Q-001, Q-002, Q-010, R-001…R-005, D-020…D-022 | `Q001_*`, `Q002_PATH`, `D020_SWORN`, `LISOVYK`, `CHARCOAL_*` | P03 Q-030, P04 Q-002/CLASS, P01 Z-002/D-015, P06 долг | FF-HIGH-P02-ARENA-001; FF-MED-P02-D020-001; FF-MED-P02-D022-001; FF-MED-P02-R001-002 | HIGH: арены | **BLOCKED** |
| P03 | Да | E-001…E-004, I-001…I-004, Q-020, Q-021, Q-030 | `Q021_BRAGA_*` | P02 D-021 (Зуб), P01 D-015 (Брага) | FF-HIGH-P03-Q030-001 | HIGH: Q-030 | **BLOCKED** |
| P04 | Да | CLASS-01…09, SEA-001, M-001, M-002, BOSS-WORLD-01 | `KAZYMIR_*`, `D020_SWORN`, `P04_CLASS_CHOSEN`, `Q002_PATH`, `Q001_GATE`, `LISOVYK` | P02 Q-001/Q-002, P01 D-005/D-015 | FF-MED-P04-CLASS-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P05 | Да | BEST-001…008, ART-001…004, HOUSE-001…003 | `CHUHAYSTER_KILLED/ABSENT`, `UPYR_RESTED` | P13 QUEST-13-02/03, P01 Z-006/D-015, P06 SOC-001, P32 Грива | FF-MED-P05-CHUHAYSTER-001; FF-LOW-P05-DOC-001 | — | **READY WITH MINOR ISSUES** |
| P06 | Да | SOC-001/002, SURV-001…003, CRAFT-001/002, LORE-001…005 | `SAVA_DEBT_*`, `P06_DEBT_*`, `SOC_*`, `SURV_FAINTED`, `CRAFT_BLADE_*`, `LORE_*` | P01 D-005/D-006/D-011/D-015, P05 UPYR | FF-HIGH-P01-P06-DEBT-001; FF-LOW-P01-P06-LORE-001 | HIGH: долг | **BLOCKED** |
| P07 | Да | PROF-001…003, DUN-001/002, COSMO-001…003, PK-001/002 | 0 | P01 Онисько/Грицько/Тарас, P05 Водяник | FF-LOW-P07-KARMA-001; FF-MED-SYS-FAILTAIL-001 (2) | — | **READY WITH MINOR ISSUES** |
| P08 | Да | MAIN-001…005, RIT-001/002 | 0 | P01 Радомир, P09 Морена, P23 боги | FF-HIGH-P08-MAIN003-001; FF-MED-P08-RIT001-001; FF-MED-SYS-MAGIC-001; FF-MED-SYS-FAILTAIL-001 (1) | HIGH: доступность | **BLOCKED** |
| P09 | Да | QUEST-01…03 | 0 | P23 GOD-11 (Марена), P24 Моровиця | — | — | **READY** |
| P10 | Да | QUEST-10-01…03 | 0 | — | — | — | **READY** |
| P11 | Да | QUEST-11-01…03 | 0 | — | — | — | **READY** |
| P12 | Да | Z-KYIV-01/02, QUEST-12-01…03 | 0 | — | FF-MED-SYS-MAGIC-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P13 | Да | Z-CARP-01/02, QUEST-13-01…03 | `CHUHAYSTER_KILLED/ABSENT` | P05 BEST-001, P26 Бойчук, P33 Арідник | — | — | **READY** |
| P14 | Да | Z-STEP-01/02, QUEST-14-01…03 | 0 | — | — | — | **READY** |
| P15 | Да | QUEST-15-01…03 | 0 | P28 Цар-Вуж | FF-MED-P28-VUZH-001; FF-MED-SYS-FAILTAIL-001 (2) | — | **READY WITH MINOR ISSUES** |
| P16 | Да | Z-SAND-01, QUEST-16-01…03 | 0 | P20 Оксен | FF-MED-P16-TEXT-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P17 | Да | Z-CHERN-01, Z-PUTYVL-01, QUEST-17-01…03 | 0 | — | — | — | **READY** |
| P18 | Да | QUEST-18-01…03 | 0 | P24 Мамуна | FF-MED-P18-STAKES-001; FF-MED-SYS-MAGIC-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P19 | Да | QUEST-19-01…03 | `TALES19_*` | P01 D-015 (Телесик) | FF-MED-P19-NPC-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P20 | Да | DAILY-20-01…03, WEEKLY-20-01/02, RADIANT-20-01…04 | 0 | P16 Оксен | FF-LOW-P20-SPIRIT-001; FF-MED-SYS-FAILTAIL-001 (5) | — | **READY WITH MINOR ISSUES** |
| P21 | Да | CRAFT-21-01…04 | 0 | — | FF-MED-SYS-FAILTAIL-001 (4) | — | **READY WITH MINOR ISSUES** |
| P22 | Да | PAGAN-22-01…04 | `PAGAN22_HARVEST_SAVED` | P01 D-015, P23 боги | — | — | **READY** |
| P23 | Да | GOD-01…15 | 0 | P22 боги, P13 Арідник, P09 Марена | FF-LOW-P23-LANG-001; FF-MED-SYS-FAILTAIL-001 (13) | — | **READY WITH MINOR ISSUES** |
| P24 | Да | DARK-24-01…05 | 0 | P18 Мамуна | FF-MED-P24-DIALOG-001; FF-MED-SYS-FAILTAIL-001 (5) | — | **READY WITH MINOR ISSUES** |
| P25 | Да | Z-PODIL-01, Z-KANIV-01, TRYPIL-25-01, PODIL-25-02, KANIV-25-03 | 0 | — | FF-MED-P25-DIALOG-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P26 | Да | HERO-26-01…05 | 0 | P13 Бойчук | — | — | **READY** |
| P27 | Да | Z-KHOLOD-01, KHOLOD-27-01…04 | 0 | — | FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P28 | Да | FOLK-28-01…04 | 0 | P15 Цар-Вуж | FF-MED-P28-VUZH-001; FF-MED-SYS-FAILTAIL-001 (4) | — | **READY WITH MINOR ISSUES** |
| P29 | Да | Z-KORCH-01, SATIR-29-01, DRAMA-29-02, SOC-29-03 | 0 | — | FF-LOW-P29-FINALS-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P30 | Да | ROM-30-01…05 | 0 | — | FF-MED-P30-FENCE-001; FF-MED-SYS-MAGIC-001; FF-MED-SYS-FAILTAIL-001 (2) | — | **READY WITH MINOR ISSUES** |
| P31 | Да | HEARTH-31-01…05, HIST-31-01 | `NALIVAYKO_*` | P01 D-015 | — | — | **READY** |
| P32 | Да | SEA-32-01…04 | 0 | P05 Грива | FF-MED-P32-SIREN-001; FF-MED-SYS-FAILTAIL-001 (4) | — | **READY WITH MINOR ISSUES** |
| P33 | Да | WITCH-33-01, WOLF-33-02, FOREST-33-03, PEAK-33-04 | 0 | P13 Арідник | FF-MED-P33-FENCE-001; FF-LOW-P33-NPC-001; FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P34 | Да | SCYTH-34-01…03, CATACOMB-34-04 | 0 | — | FF-MED-SYS-MAGIC-001; FF-MED-SYS-FAILTAIL-001 (4) | — | **READY WITH MINOR ISSUES** |
| P35 | Да | CARNIVAL-35-01…03, BAKOTA-35-04 | 0 | — | FF-MED-SYS-FAILTAIL-001 (3) | — | **READY WITH MINOR ISSUES** |
| P36 | Да | CRAFT-36-01/02, GATHER-36-03, ECON-36-04 | 0 | — | FF-MED-SYS-FAILTAIL-001 (5) | — | **READY WITH MINOR ISSUES** |

---

## 2. Сводка

| Статус | Количество | Пакеты |
|---|---:|---|
| **BLOCKED** | **5** | P01, P02, P03, P06, P08 |
| **READY WITH MINOR ISSUES** | **22** | P04, P05, P07, P12, P15, P16, P18, P19, P20, P21, P23, P24, P25, P27, P28, P29, P30, P32, P33, P34, P35, P36 |
| **READY** | **9** | P09, P10, P11, P13, P14, P17, P22, P26, P31 |
| **NOT FULLY AUDITED** | **0** | — |

**Проверка суммы:** 5 + 22 + 9 = 36. Статус каждого пакета соответствует строке таблицы выше: P35/P36 имеют только системный fail-tail (MEDIUM), поэтому они в `READY WITH MINOR ISSUES`, а не в `READY`.

---

## 3. Почему пакеты BLOCKED

| Пакет | Блокер | Что нужно |
|---|---|---|
| P01 | FF-HIGH-P01-P06-DEBT-001 | Исправить state machine долга; убрать двойную выдачу LORE |
| P02 | FF-HIGH-P02-ARENA-001 | Описать выход после победы во всех аренах |
| P03 | FF-HIGH-P03-Q030-001 | Проверять текущую репутацию LB в ветке Зуба |
| P06 | FF-HIGH-P01-P06-DEBT-001 | То же; синхронизировать CRAFT-002 и D-005 |
| P08 | FF-HIGH-P08-MAIN003-001 | Аудио-эквивалент «Ока Відьми» или замена механики |

---

## 4. Почему остальные не BLOCKED

- **MEDIUM** (P04 class, P05 Chuhayster, P12/P18/P30/P34 magic, P15/P28 Tsar-Vuzh, P16 text, P18 stakes, P19 rename, P24/P25 dialogue, P30/P33 fence, P32 sirens, SYS fail-tail) не делают обязательный квест невозможным; они ухудшают целостность, но не блокируют редактуру.
- **LOW** (русизмы, P07 karma, P20 spirituality, P29 finals, P05 doc, P01/P06 lore duplication, NPC-0428 duplicate) — редакционные/регистрационные.
- **Tsar-Vuzh** требует решения владельца, но оба квеста проходимы по отдельности; поэтому пакеты не BLOCKED, а READY WITH MINOR ISSUES + owner decision.

---

## 5. Вывод

Фундамент **не готов** к художественной редактуре в пяти пакетах: P01, P02, P03, P06, P08. Остальные 31 пакет можно редактировать после устранения системных MEDIUM (особенно fail-tail, P19 rename, P30/P33 fence, P32 sirens) и фиксации owner-решений по Tsar-Vuzh и классам. Но поскольку HIGH-проблемы затрагивают межпакетные цепочки, начинать редактуру всех 36 пакетов до их исправления нельзя: изменения в P01/P02/P03/P06/P08 могут потребовать правок в соседних пакетах.
