# АУДИТ ФЛАГІВ P31–P36

**Дата:** 2026-11-26
**Перевірений HEAD:** `4d752bfe820c3fc33111e3713310d3f8457d769d`
**Реєстр:** `canon/FLAG_REGISTRY.md` v2.31
**Перевірено ID:** 78 (P31 — 18, P32–P36 — по 12)

---

## 1. Загальна картина

| Пакет | DONE one-shot | State-пам’ять | Разом | Зовнішні споживачі |
|---|---:|---:|---:|---|
| P31 | 5 (`Q01…Q05`) + 3 `NALIVAYKO` | 10 | 18 | P01 D-015 читає `NALIVAYKO_HERO`/`SHADOW_RETREAT`; `LAST_STAND` — лише епілог |
| P32 | 4 | 8 | 12 | Немає обов’язкових; `STORM`/`CAUSEWAY` — OBS |
| P33 | 4 | 8 | 12 | Немає |
| P34 | 4 | 8 | 12 | Немає (предметний CHECK P14 — не флаг) |
| P35 | 4 | 8 | 12 | Немає |
| P36 | 4 | 8 | 12 | Немає |

**Усього:** 28 DONE/епопейних + 50 state = 78 ID.

**Незалежна звірка:** усі 78 ID з текстів присутні в реєстрі; усі 78 карток реєстру присутні в текстах; дублікатів немає; зайвих ID немає.

---

## 2. Повний перелік і життєвий цикл

### P31 — 18

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P31_Q01_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P31_Q01_SPOKUTA` | B + DONE | повтор | —; excl. LITOPYS | OK; текст/реєстр мають «капище/каплиця» — `GA-P31-003` |
| `FLAG_P31_Q01_LITOPYS` | C + DONE | повтор | —; excl. SPOKUTA | OK |
| `FLAG_P31_Q02_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P31_Q02_LADAN` | B + DONE | повтор | —; excl. TABAK | OK |
| `FLAG_P31_Q02_TABAK` | C + DONE | повтор | —; excl. LADAN | OK |
| `FLAG_P31_Q03_DONE` | A/B/echo | тригер; повтор | — | OK |
| `FLAG_P31_Q03_WINDBANE` | B + DONE | повтор | —; excl. WEDDING | OK |
| `FLAG_P31_Q03_WEDDING` | echo + DONE | повтор | —; excl. WINDBANE | OK; калька в реєстрі — `GA-P31-005` |
| `FLAG_P31_Q04_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P31_Q04_THUNDER` | B + DONE | повтор | —; excl. ANVIL | OK |
| `FLAG_P31_Q04_ANVIL` | C + DONE | повтор | —; excl. THUNDER | OK |
| `FLAG_P31_Q05_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P31_Q05_PYRE` | B + DONE | повтор | —; excl. SECOND | OK |
| `FLAG_P31_Q05_SECOND` | C + DONE | повтор | —; excl. PYRE | OK |
| `FLAG_NALIVAYKO_SOLONYTSIA_HERO` | A HIST | P01 D-015 | —; excl. LAST/SHADOW | OK |
| `FLAG_NALIVAYKO_LAST_STAND` | B HIST | епілог; без P01 | —; terminal | OK |
| `FLAG_NALIVAYKO_SHADOW_RETREAT` | echo HIST | P01 D-015 | —; excl. HERO/LAST | OK |

### P32 — 12

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P32_Q01_DONE` | A/B/C | тригер; повтор | — | OK; щит у B/C — OBS |
| `FLAG_P32_Q01_BEACON` | B + DONE | повтор | —; excl. PACT | OK |
| `FLAG_P32_Q01_PACT` | C + DONE | повтор | —; excl. BEACON | OK |
| `FLAG_P32_Q02_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P32_Q02_WARDEN` | B + DONE | повтор | —; excl. STORM | OK |
| `FLAG_P32_Q02_STORM` | C + DONE | повтор | —; excl. WARDEN | OK; external OBS |
| `FLAG_P32_Q03_DONE` | A/B/echo | тригер; повтор | — | OK |
| `FLAG_P32_Q03_TRAP` | B + DONE | повтор | —; **combines GROVE** | OK |
| `FLAG_P32_Q03_GROVE` | echo + DONE | повтор | —; **combines TRAP** | OK |
| `FLAG_P32_Q04_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P32_Q04_HEART` | B + DONE | повтор | —; excl. CAUSEWAY | OK |
| `FLAG_P32_Q04_CAUSEWAY` | C + DONE | повтор | —; excl. HEART | OK; external OBS |

### P33 — 12

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P33_Q01_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P33_Q01_ROSA` | B + DONE | повтор | —; excl. GRIMOIRE | OK |
| `FLAG_P33_Q01_GRIMOIRE` | C + DONE | повтор | —; excl. ROSA | OK |
| `FLAG_P33_Q02_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P33_Q02_PACK` | B + DONE | повтор | —; excl. OUTPOST | OK |
| `FLAG_P33_Q02_OUTPOST` | C + DONE | повтор | —; excl. PACK | OK |
| `FLAG_P33_Q03_DONE` | A/B/echo | тригер; повтор | — | OK |
| `FLAG_P33_Q03_HUT` | B + DONE | повтор | —; **combines BLESSING** | OK |
| `FLAG_P33_Q03_BLESSING` | echo + DONE | повтор | —; **combines HUT** | OK |
| `FLAG_P33_Q04_DONE` | A/B/C | тригер; повтор | — | **Проблема:** картка «титана знешкоджено», але B не знешкоджує — `GA-P33-001` |
| `FLAG_P33_Q04_WINGS` | B + DONE | повтор | —; excl. SALT | OK як стан, але B неповний |
| `FLAG_P33_Q04_SALT` | C + DONE | повтор | —; excl. WINGS | OK |

### P34 — 12

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P34_Q01_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P34_Q01_TRIUMPH` | B + DONE | повтор | —; excl. LEGACY | OK |
| `FLAG_P34_Q01_LEGACY` | C + DONE | повтор | —; excl. TRIUMPH | OK |
| `FLAG_P34_Q02_DONE` | A/B/C | тригер; повтор | — | OK; назва «Бабу замирено» неточна для B (документаційна нюансировка) |
| `FLAG_P34_Q02_GOLEM` | B + DONE | повтор | —; excl. BEACON | OK |
| `FLAG_P34_Q02_BEACON` | C + DONE | повтор | —; excl. GOLEM | OK |
| `FLAG_P34_Q03_DONE` | A/B/echo | тригер; повтор | — | **Проблема:** Акт II зобов’язує взяти Пектораль, B/echo — ні — `GA-P34-001` |
| `FLAG_P34_Q03_SEALED` | B + DONE | повтор | —; excl. BRONZE | OK як стан; бракує точки вибору |
| `FLAG_P34_Q03_BRONZE` | echo + DONE | повтор | —; excl. SEALED | OK як стан; бракує точки вибору |
| `FLAG_P34_Q04_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P34_Q04_POWDER` | B + DONE | повтор | —; excl. FREEDOM | OK |
| `FLAG_P34_Q04_FREEDOM` | C + DONE | повтор | —; excl. POWDER | OK |

### P35 — 12

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P35_Q01_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P35_Q01_FROST` | B + DONE | повтор | —; excl. FEAST | OK |
| `FLAG_P35_Q01_FEAST` | C + DONE | повтор | —; excl. FROST | OK |
| `FLAG_P35_Q02_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P35_Q02_SWIFT` | B + DONE | повтор | —; excl. PEACE | OK |
| `FLAG_P35_Q02_PEACE` | C + DONE | повтор | —; excl. SWIFT | OK |
| `FLAG_P35_Q03_DONE` | A/B/echo | тригер; повтор | — | OK |
| `FLAG_P35_Q03_CRYSTAL` | B + DONE | повтор | —; excl. RUSHNYK | OK |
| `FLAG_P35_Q03_RUSHNYK` | echo + DONE | повтор | —; excl. CRYSTAL | OK |
| `FLAG_P35_Q04_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P35_Q04_SOM` | B + DONE | повтор | —; excl. RESONANCE | OK |
| `FLAG_P35_Q04_RESONANCE` | C + DONE | повтор | —; excl. SOM | OK |

### P36 — 12

| ID | SET | CHECK | CLEAR / сумісність | Вердикт |
|---|---|---|---|---|
| `FLAG_P36_Q01_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P36_Q01_STORM` | B + DONE | повтор | —; excl. WATCH | OK |
| `FLAG_P36_Q01_WATCH` | C + DONE | повтор | —; excl. STORM | OK |
| `FLAG_P36_Q02_DONE` | A/B/C | тригер; повтор | — | OK |
| `FLAG_P36_Q02_BOARD` | B + DONE | повтор | —; excl. CHART | OK |
| `FLAG_P36_Q02_CHART` | C + DONE | повтор | —; excl. BOARD | OK |
| `FLAG_P36_Q03_DONE` | A/B/echo | тригер; повтор | — | OK |
| `FLAG_P36_Q03_DEAL` | B + DONE | повтор | —; excl. LAB | OK |
| `FLAG_P36_Q03_LAB` | echo + DONE | повтор | —; excl. DEAL | OK |
| `FLAG_P36_Q04_DONE` | A/B/C | тригер; повтор | — | OK; арифметика — `GA-P36-001` |
| `FLAG_P36_Q04_TRAIN` | B + DONE | повтор | —; excl. MERCY | OK |
| `FLAG_P36_Q04_MERCY` | C + DONE | повтор | —; excl. TRAIN | OK |

---

## 3. SET без CHECK / CHECK без SET

- **SET без CHECK:** не знайдено. Кожен DONE читається тригером і повтором; кожен state читається повтором; NALIVAYKO — P01 D-015/тригером.
- **CHECK без SET:** не знайдено.
- **Тимчасові флаги без CLEAR:** не знайдено; усі state — постійна пам’ять, CLEAR — «—».
- **CLEAR, що стирає потрібне:** не знайдено; NALIVAYKO explicitly replaces the other two states, as intended.
- **Кілька флагів на одне state:** лише documented pairs `P32 TRAP+GROVE`, `P33 HUT+BLESSING`; решта — mutually exclusive.
- **Неможливі/взаємовиключні комбінації:** перевірені; єдина проблема — P33 Q04 B/DONE (стан титана), P34 Q03 B/echo (предметний стан), P31 Q01 B (хата).

---

## 4. Зовнішні залежності

| Флаг | Джерело | Споживач | Статус |
|---|---|---|---|
| `FLAG_NALIVAYKO_SOLONYTSIA_HERO` | P31 HIST-31-01 A | P01 D-015 | Узгоджено |
| `FLAG_NALIVAYKO_SHADOW_RETREAT` | P31 HIST-31-01 echo | P01 D-015 | Узгоджено |
| `FLAG_NALIVAYKO_LAST_STAND` | P31 HIST-31-01 B | P01 D-015 — TECH, без реакції | Узгоджено; термінальний |
| `FLAG_P32_Q02_STORM` | P32 SEA-32-02 C | Немає обов’язкового | OBS |
| `FLAG_P32_Q04_CAUSEWAY` | P32 SALT-32-04 C | Немає обов’язкового | OBS |

Інших зовнішніх споживачів P31–P36 не знайдено (пошук по всіх 36 пакетах).

---

## 5. Висновок

- **78/78** ID зареєстровані, мають SET/CHECK/CLEAR і відповідають текстам.
- Дублікатів, зайвих ID і CHECK без SET немає.
- `TRAP`+`GROVE` і `HUT`+`BLESSING` — коректні сумісні пари.
- `NALIVAYKO`-стани взаємовиключні; `LAST_STAND` термінальний.
- Проблеми, що впливають на сенс флагів: `P33_Q04_DONE` (`GA-P33-001`), `P34_Q03_*` (`GA-P34-001`), `P31_Q01_*` (`GA-P31-001`).
- Документаційні нюанси: `P31_Q03_WEDDING` (`GA-P31-005`), `P34_Q02_DONE` назва, `P32_Q01_DONE` щит OBS.
- **Статус:** FLAG AUDIT — `CONDITIONAL`; блокерів немає, але три флагові лінії потребують узгодження з текстом.
