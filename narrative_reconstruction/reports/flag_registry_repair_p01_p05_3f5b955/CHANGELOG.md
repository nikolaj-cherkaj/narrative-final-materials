# CHANGELOG — ремонт реєстру P01–P05 (промпт 4)

- База: `agent/integration-p01-p05-fix-2@3f5b955`; нова гілка `agent/flag-registry-p01-p05-3f5b955`.
- Створено: `narrative_reconstruction/canon/FLAG_REGISTRY.md` v1.0 (єдиний канон; P01–P05, 50 реальних ID + 2 шаблони-скорочення).
- Додано/перевірено 4 цільові: `FLAG_D020_ERRAND_1` (P02:1044,1079,1084,1185,990–991), `FLAG_D020_ERRAND_2` (P02:1090–1091,1131,1136), `FLAG_D020_ERRAND_3` (P02:1142–1143,1178,1183), `FLAG_P01_MYKHAILO_RUN_DONE` (P01:1008–1009 SET; P01:524,530,1079–1080 CHECK).
- Додано відсутні: LORE_REWARDED (P01:1112–1116), D006_REWARDED (P01:628–630), ART_001_FOUND (P05:367–369), ART_003_FOUND (P05:434–436, лише після взяття); звірені решта 40+ флагів з актуальними рядками.
- Пакети P01–P05 не редагувались (дефектів SET/CHECK/CLEAR не знайдено). Рішення власника 2026-11-25 збережені без змін.
- Оновлено: `reports/integration_p01_p05/FLAG_DEPENDENCY_MAP.md` (посилання на `canon/FLAG_REGISTRY.md` як джерело істини); створено `change_log/CHANGELOG_2026-11-25_FLAG_REGISTRY_P01_P05.md`.
- Історичні `GLOBAL_FLAG_AUDIT.md`, `FLAG_LIFECYCLE_*`, старі звіти — не переписані.
