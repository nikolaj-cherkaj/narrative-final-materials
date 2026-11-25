# CHANGELOG — ремонт P11–P15 за аудитом `dc18f83`

**Ветка:** `agent/integration-p11-p15-fix-7df7147` (от `7df7147`). **Дата:** 2026-11-25.

## Коммиты

- `4087745` — `chore: backup P11-P15 pre-remediation state for audit fix (dc18f83)`: 5 бекапов `original_backup/naratyvni_teksty_paket_NN_pre_remediation_p11_p15_fix_2026-11-25.md` (NN = 11–15; прежние бекапы не перезаписаны).
- `fb67a9f` — `fix: remediate group audit P11-P15 findings GA-P13-001, GA-P14-001/002/004, GA-P12-001/002/003, GA-P15-001/002/003, GA-P11-001`: 19 вставок / 15 удалений в 5 файлах `revised/` (только строки из таблицы ниже; финалы, флаги, награды, триггеры не менялись).
- `4524132` — `docs: sync FLAG_REGISTRY (v2.3) and GLOBAL_CARRYOVER_REGISTER for P11-P15 audit fix`: реестр флагов (версія 2.3; §0, §12, §14, §15) + §2.5/уточнения `GC-P12-P20-001`, `GC-P15-P28-001`/история в глобальном реестре.
- (отчёты — следующим коммитом): `reports/integration_p11_p15_fix/` — `INTEGRATION_REPORT.md`, `REMEDIATION_RESULT.md`, `FLAG_CHECK.md`, `CARRYOVER_HANDOFF.md`, `OWNER_DECISION_BRIEF.md`, `CHANGELOG.md`.

## Изменённые файлы (тексты)

| Файл | Строки (после) | Суть |
|---|---|---|
| `revised/naratyvni_teksty_paket_11.md` | :57 | Ремінь-страховка від Ратибора (GA-P11-001) |
| `revised/naratyvni_teksty_paket_12.md` | :97; :121; :146; :161; :175; :333 | Сетап авангарду; меч «на час оборони» + повернення у 3 фіналах; пороховий погріб |
| `revised/naratyvni_teksty_paket_13.md` | :92; :95; :115 | Видача мольфи на початку розмови |
| `revised/naratyvni_teksty_paket_14.md` | :91; :121; :194; :216 | Вість Семенка; вузол «обмін»; оклик Созонта; «До весел!» |
| `revised/naratyvni_teksty_paket_15.md` | :217; :341; :370 | Retry струни; retry Здвиження; ріг — Царю-Вужу |

`git diff --check` — чисто. Исторические отчёты (`integration_p11_p15/`, `group_audit_*`), main и чужие пакеты не тронуты.
