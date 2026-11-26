# СПИСОК ЗМІНЕНИХ ФАЙЛІВ — РЕМЕДІАЦІЯ P26–P30

**Дата:** 2026-11-26

**База:** `d3dd245459c4913f492fe290211ef0207d8cb30c`

**Гілка:** `agent/integration-p26-p30-remediation-d3dd245`

---

## 1. Пакети

| Файл | Статус | Що змінено |
|---|---|---|
| `narrative_reconstruction/revised/naratyvni_teksty_paket_15.md` | M | Фінал А: ріг забирається у вузлику; відлуння `LIVING_WATER`: герой повертає ріг владиці; прапорці/повтор узгоджені |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_26.md` | M | Q01E: Варіант 3 → переговори, Етап 2В, фінал В; блоки вибору Q02–Q05; флаг-специфічні повтори; «трипудові» |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_27.md` | M | Блоки вибору Q01–Q04; флаг-специфічні повтори; «чути дряпання нігтем» |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_28.md` | M | P15→P28: чотири стани рога; Крок 3 умовний; фінали А/Б/В; «Роса Зміїного Царя»; блоки вибору Q01/Q03/Q04; повтори |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_29.md` | M | P29 Q02: Етап 3, fail vs фінал Г; блоки вибору Q01–Q03; флаг-специфічні повтори; 16 NPC |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_30.md` | M | Блоки вибору Q01–Q05; флаг-специфічні повтори; перлина — та сама; «на карателів» |

---

## 2. Канон і реєстри

| Файл | Статус | Що змінено |
|---|---|---|
| `narrative_reconstruction/canon/FLAG_REGISTRY.md` | M | v2.24; §0 `GC-P15-P28-001` — CLOSED з фізичним циклом; §15 — один ріг, `NATURE_TONGUE`/`LIVING_WATER`/`GREED_PUNISHED`; §26 — Q01E Етап 2В; §28 — `Q02_DONE`/`BALM`/`WARD`, «Роса»; §29 — fail vs Г; §30 — перлина та сама; флаг-специфічні повтори |
| `narrative_reconstruction/canon/CHARACTERS.md` | M | v2.5; NPC-0254 у зведеній таблиці → `P13 QUEST-13-02`, `P13, P26` |
| `narrative_reconstruction/reports/GLOBAL_CARRYOVER_REGISTER.md` | M | §2.10: 18 MEDIUM; `GC-P15-P28-001` — CLOSED з фізичним циклом; §3.3; історія оновлень |

---

## 3. Документація інтеграції

| Файл | Статус | Що змінено |
|---|---|---|
| `narrative_reconstruction/reports/integration_p26_p30/INTEGRATION_REPORT.md` | M | 17→18 MEDIUM; «2 фінали + відлуння» замість «три фінали» |
| `narrative_reconstruction/change_log/CHANGELOG_2026-11-26_REMEDIATION_P26_P30.md` | A | Журнал адресної ремедіації |

---

## 4. Резервні копії

| Файл | Статус |
|---|---|
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_15_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_26_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_27_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_28_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_29_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/naratyvni_teksty_paket_30_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/FLAG_REGISTRY_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/CHARACTERS_pre_remediation_2026-11-26.md` | A |
| `narrative_reconstruction/original_backup/GLOBAL_CARRYOVER_REGISTER_pre_remediation_2026-11-26.md` | A |

---

## 5. Нові звіти

| Файл | Статус |
|---|---|
| `narrative_reconstruction/reports/integration_p26_p30_remediation/REMEDIATION_REPORT.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/FINDINGS_STATUS_MATRIX.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/GOLDEN_HORN_LIFECYCLE.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/FINAL_OUTCOME_AUDIT.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/STATE_FLAG_RECHECK.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/PLAYER_PATH_REGRESSION.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/CARRYOVER_STATUS.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/CHANGED_FILES.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/GIT_STATE.md` | A |
| `narrative_reconstruction/reports/integration_p26_p30_remediation/OWNER_QUESTIONS.md` | A |

---

## 6. Не включено до коміту

Локальні зміни користувача:
- `narrative_reconstruction/prompts/02_group_integration_and_remediation.md` (M) — параметри запуску;
- `narrative_reconstruction/prompts/03_group_independent_audit.md` (M) — параметри запуску;
- `3 промпт запуск.txt`, `narrative_reconstruction/01_single_package_artistic_revision.md`, `02_group_integration_and_remediation.md`, `03_group_independent_audit.md`, `04_global_flag_registry_repair_p01_p05.md`, `Новый текстовый документ.txt` (??) — не стосуються ремедіації.

Ці файли не видалені й не перезаписані.

---

## 7. Перевірка

- `git diff --check` — без помилок (лише CRLF-попередження Git).
- Усі змінені пакети мають резервні копії.
- `main`, інтеграційна та аудиторська гілки не змінювалися.
