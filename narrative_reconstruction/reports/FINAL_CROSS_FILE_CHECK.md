# FINAL_CROSS_FILE_CHECK — проход 3 (prompt.txt). Дата: 2026-11-12
Метод: скрипты-реестры по `narrative_reconstruction/revised/` (имена, ID, прапорці) + ручная проверка спорных. Проходы 1–2 — гипотезы, не доказательства.

## 1. Имена (реестр)
- **Сірошапка/Байрачний:** FIXED ранее, VERIFIED проходом 3 (P02 наставник, P04 CLASS, P03 — Байрачний; «Сірошапка» в P03 = 0).
- **Ярема:** 3 особи + топонім (CHARACTERS, без перейменувань).
- **Дорош:** 3 особи; зв'язок писарів Пак.4/Пак.8 НЕ встановлено (не выдумывать).
- **Остап ×7, Самійло, Лаврін, Сава, Микола, Лейба ×3, Грицько, Чорнобог:** VERIFIED (разных лиц разведено, коллизий 0).
- **Брага:** P01 прапорці ≡ P03 фінали A/B/V. Цілісно.
- Новых сущностей в проходе 3: 0 (проверено поиском по 36 файлам; ссылки только на существующих NPC/места).

## 2. Прапорці (12 уникальных)
- `FLAG_MYKHAILO_MET` ×2 (naratyvni_teksty_paket_1.md:453, naratyvni_teksty_paket_1.md:594): SETTER+CONSUMER.
- `FLAG_MYKHAILO_RUN_01` ×3 (naratyvni_teksty_paket_1.md:604, naratyvni_teksty_paket_1.md:605, naratyvni_teksty_paket_1.md:669): SETTER+CONSUMER.
- `FLAG_NALIVAYKO_LAST_STAND` ×2 (naratyvni_teksty_paket_1.md:665, naratyvni_teksty_paket_31.md:649): SETTER+CONSUMER.
- `FLAG_NALIVAYKO_SHADOW_RETREAT` ×2 (naratyvni_teksty_paket_1.md:663, naratyvni_teksty_paket_31.md:661): SETTER+CONSUMER.
- `FLAG_NALIVAYKO_SOLONYTSIA_HERO` ×2 (naratyvni_teksty_paket_1.md:661, naratyvni_teksty_paket_31.md:637): SETTER+CONSUMER.
- `FLAG_PAGAN22_HARVEST_SAVED` ×2 (naratyvni_teksty_paket_1.md:651, naratyvni_teksty_paket_22.md:311): SETTER+CONSUMER.
- `FLAG_Q021_BRAGA_ALLIED` ×2 (naratyvni_teksty_paket_1.md:639, naratyvni_teksty_paket_3.md:343): SETTER+CONSUMER.
- `FLAG_Q021_BRAGA_BRIBED` ×2 (naratyvni_teksty_paket_1.md:643, naratyvni_teksty_paket_3.md:356): SETTER+CONSUMER.
- `FLAG_Q021_BRAGA_EXECUTED` ×2 (naratyvni_teksty_paket_1.md:641, naratyvni_teksty_paket_3.md:330): SETTER+CONSUMER.
- `FLAG_TALES19_TELESYK_SAVED` ×5 (naratyvni_teksty_paket_1.md:647, naratyvni_teksty_paket_19.md:93, naratyvni_teksty_paket_19.md:96): SETTER+CONSUMER.
- `KAZYMIR_EXECUTED` ×3 (naratyvni_teksty_paket_1.md:657, naratyvni_teksty_paket_4.md:426, naratyvni_teksty_paket_4.md:438): SETTER+CONSUMER.
- `KAZYMIR_SPARED` ×4 (naratyvni_teksty_paket_1.md:373, naratyvni_teksty_paket_1.md:655, naratyvni_teksty_paket_4.md:426): SETTER+CONSUMER.
- P01 хаб — доска слухов: закрытый квест меняет 1–2 реплики (Василь/Сава) по существующим флагам. Новое в проходе 3: добавлен потребитель `FLAG_NALIVAYKO_LAST_STAND` (P01 Василь, мирная поминальная реплика) — висячих 0.
- Условные ветки — с отводкой без флага («Не чув такої — спитай…», образец P01 Онисько L453).
- Висячих прапорців: 0.

## 3. ID (226 уникальных кодов `##`)
- Дублей: 0 (скрипт). Префиксный дрейф (Z-/R-/QUEST-/HERO-) — принятая вариантность: переименование = высокий риск, ноль выгоды. Не трогал.
- Список дублей: —.

## 4. Гео/хроно
- Эпохи разные в разных квестах — норма, в хронологию не выстраивать. Не маркировать «фантазия/D».
- Новых противоречий/длублей/заглушек/выдуманных сущностей в проходе 3: 0.

## 5. Самопроверка реконструкции
- Личильник `**Наслідок` ≈ ожидаемому (P01 хаб — диалоги; P05 каталог; P06 сценарии — внутри). MISMATCH: 0.
- Вставные правки прохода 3 не убивают именных NPC, не создают прапорців (кроме сшивки LAST_STAND→существующий флаг), не меняют экономику (числа — примеры).
