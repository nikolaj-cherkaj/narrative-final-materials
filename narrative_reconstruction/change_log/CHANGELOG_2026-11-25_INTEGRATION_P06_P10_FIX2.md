# CHANGELOG — інтеграція P06–P10 fix2 (усунення findings аудиту 0070a2a)

**Дата:** 2026-11-25
**База:** `agent/group-audit-p06-p10-c3aca43 @ 0070a2a` → **робоча:** `agent/integration-p06-p10-fix-0070a2a`
**Джерело завдань:** `reports/group_audit_p06_p10_c3aca43/ADDITIONAL_FINDINGS.md` (10 MEDIUM + 15 LOW + 5 OBS).

## Змінені файли пакетів (5)

- `revised/naratyvni_teksty_paket_6.md` — SOC CLEAR/відмови/обручки (F1/F7/F8); борг CLEAR/напад/перстень-татарка/наріст (F2/F9); Літопис (F3); півверсти/вузол (F4/F5); служба бортника (F10).
- `revised/naratyvni_teksty_paket_7.md` — Серце (F1); «Рушаймо» ×3 (F4); гейти ×4 (F5); гостинність TECH (F2); сяйво (F3).
- `revised/naratyvni_teksty_paket_8.md` — `PRAYER_KNOWN` + CHECK (F1/F6); тригер/мак (F5); сварка/BLOWN/Око (F7); жили/варта/кістка (F4/F8/F3); статистика 18 + гостинність TECH.
- `revised/naratyvni_teksty_paket_9.md` — перстень/свідки/порядок/золото (F1/F3); щілина/фільтри/смолоскип (F3); Відлуння → Фінал В, 9 фіналів (F3); нива (F2).
- `revised/naratyvni_teksty_paket_10.md` — вигнання/пожертва/тавро/шнури/бранці/бідність (F2).

## Реєстр

- `canon/FLAG_REGISTRY.md` — +`FLAG_P08_PRAYER_KNOWN` (§8, 18 ID); MAIN003-залежність; §8-інтро; PACT — «фінал В (пакт)» (§9).

## Бекапи (до правок, не перезаписують старі)

- `original_backup/naratyvni_teksty_paket_{6,7,8,9,10}_pre_integration_p06_p10_fix2_2026-11-25.md`

## Звіти (нові, старі не чіпались)

- `reports/integration_p06_p10_fix2/` — 6 документів (REPORT, MATRIX, FLAGS, PATHS, PLAN, RESULT).

## Механіки/канон/баланс

- Не змінювались: ворота MAIN (O-001 — спостереження), економіка (числа — приклади TBD), канон/NPC-ID (крім +1 флаг знання), пороги/репозиційні семантики.
- Регресії §11: 8/8 PASS. Власнику: питань немає.
