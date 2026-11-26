# QUEST STATE MACHINES — P21–P25

**Дата:** 2026-11-26
**SHA:** `7a1db2c`
**Метод:** состояния выведены только из текста; новых условий не добавлено. Общие состояния: `LOCKED` — DONE активен; `AVAILABLE` — DONE не активен; `IN_PROGRESS` — сцена начата; `FAIL` — провал без флага; `REFUSED` — Варіант 4 без флага; `FINAL_A/B/C` — выбранный финал; `DONE` — соответствующий DONE-флаг установлен.

---

## 1. P21 — CRAFT-21-01…04

### CRAFT-21-01 «Золота борть»

```
LOCKED (CRAFT01_DONE) ── повтор ──► MEMORY_ONLY
AVAILABLE ── диалог Демида (В1/В2/В3) ──► IN_PROGRESS
IN_PROGRESS ── провал (рій) ──► FAIL ──► IN_PROGRESS (димар/лезиво збережено)
IN_PROGRESS ── В4 ──► REFUSED ──► AVAILABLE
IN_PROGRESS ── этап 3 A ──► FINAL_A ──► DONE (CRAFT01_DONE)
IN_PROGRESS ── этап 3 B ──► FINAL_B ──► DONE + BEAR_ALLIED
IN_PROGRESS ── этап 3 C ──► FINAL_C ──► DONE + MONASTERY_WAX
```

Проверка: DONE ставится любым финалом; FAIL/REFUSED не ставят; повтор при DONE — только память (P21:26, 101–125).

### CRAFT-21-02 «Синя глина»

```
AVAILABLE ── Терешко (В1–В3) ──► IN_PROGRESS
FAIL (горн) ──► IN_PROGRESS; REFUSED ──► AVAILABLE
A ──► DONE; B ──► DONE + MAKITRA_OWNED; C ──► DONE + POTTERY_SHOP
```

P21:146, 213–245.

### CRAFT-21-03 «Червона та чорна нитка»

```
AVAILABLE ── Ганна (В1–В3) ──► IN_PROGRESS
FAIL (основа) ──► IN_PROGRESS; REFUSED ──► AVAILABLE
A ──► DONE; B ──► DONE + RUSHNYK_BLESSING; C ──► DONE + BANNER_GIVEN
```

P21:257, 326–358.

### CRAFT-21-04 «Перша паляниця»

```
AVAILABLE ── Прокіп на ниві (В1–В3) ──► IN_PROGRESS
FAIL (підгорів) ──► IN_PROGRESS; REFUSED ──► AVAILABLE
A ──► DONE; B ──► DONE + MILL_RESTORED; C ──► DONE + SICH_SUPPLIER
```

P21:379, 443–475. Проверка: Прокіп приходит на зажинки (P21:376), затем у мельницы; пространство согласовано.

---

## 2. P22 — PAGAN-22-01…04

| Квест | AVAILABLE / вход | FAIL | REFUSED | FINAL A | FINAL B | FINAL C |
|---|---|---|---|---|---|---|
| PAGAN-22-01 | нет `P22_Q01_DONE` (P22:30) | морок → retry (P22:81) | В4 → AVAILABLE (P22:55) | `Q01_DONE` (P22:104) | `Q01_DONE` + `Q01_BEAR` (P22:116) | `Q01_DONE` + `Q01_SHIELD` (P22:128) |
| PAGAN-22-02 | нет `P22_Q02_DONE` (P22:144) | нить порвалась → retry (P22:197) | В4 (P22:169) | `Q02_DONE` (P22:220) | `Q02_DONE` + `Q02_MIRROR` (P22:232) | `Q02_DONE` + `Q02_LADA` (P22:244) |
| PAGAN-22-03 | нет `HARVEST_SAVED` (P22:259) | буран → retry (P22:292) | В4 (P22:283) | `HARVEST_SAVED` (P22:336) | `HARVEST_SAVED` + `Q03_LATY` (P22:350) | `HARVEST_SAVED` + `Q03_GRAIN` (P22:362) |
| PAGAN-22-04 | нет `P22_Q04_DONE` (P22:378) | Крада не зайнялась → retry (P22:430) | В4 (P22:403) | `Q04_DONE` (P22:453) | `Q04_DONE` + `Q04_SOKIL` (P22:465) | `Q04_DONE` + `Q04_VALY` (P22:477) |

**Особенность:** Q03 использует `FLAG_PAGAN22_HARVEST_SAVED` как DONE; отдельного `Q03_DONE` нет. Это соответствует реестру.

**Дефект:** ветки памяти P22 Q01–Q04 (P22:30, 144, 259, 378) не меняют TTS-диалоги; сценарий D/G показывает «первую встречу».

---

## 3. P23 — GOD-01…GOD-15

Общая модель для каждого GOD-XX:

```
AVAILABLE (нет GODxx_DONE) ── вход/диалог ──► IN_PROGRESS
IN_PROGRESS ── FAIL ──► IN_PROGRESS (retry)
IN_PROGRESS ── В4 ──► REFUSED ──► AVAILABLE
IN_PROGRESS ── A ──► DONE
IN_PROGRESS ── B/тайный ──► DONE + state_B
IN_PROGRESS ── C/эхо ──► DONE + state_C
DONE ── повтор ──► MEMORY_ONLY
```

| Квест | DONE | Состояния B/C или эхо | Внешний CHECK |
|---|---|---|---|
| GOD-01 Сварог | `GOD01_DONE` | `BLADE` (B), `RINGS` (C) | — |
| GOD-02 Перун | `GOD02_DONE` | `STANDARD` (B), `GROVE` (C) | **должен быть `P22_Q04_DONE` — отсутствует** |
| GOD-03 Дажбог | `GOD03_DONE` | `SOKIL` (B), `HORSES` (C) | P24 Q05 — канон-разметка |
| GOD-04 Хорс | `GOD04_DONE` | `MIRROR` (B), `PATH` (эхо) | — |
| GOD-05 Велес | `GOD05_DONE` | `RUNO` (B), `WOLF` (эхо) | `P22_Q01_DONE` (только trigger) |
| GOD-06 Стрибог | `GOD06_DONE` | `STORM` (B), `FROST` (эхо) | — |
| GOD-07 Мокош | `GOD07_DONE` | `SPINDLE` (B), `SPRING` (C) | `P22_Q02_DONE` (только trigger) |
| GOD-08 Лада | `GOD08_DONE` | `WREATH` (B), `HEARTH` (эхо) | — |
| GOD-09 Леля | `GOD09_DONE` | `TEAR` (тайный), `SOURCE` (эхо) | — |
| GOD-10 Ярило | `GOD10_DONE` | `HARVEST` (B), `STEED` (эхо) | — |
| GOD-11 Марена | `GOD11_DONE` | `ARMOR` (B), `PACT` (эхо) | `HARVEST_SAVED` (только trigger) |
| GOD-12 Чорнобог | `GOD12_DONE` | `BLADE` (тайный), `SEAL` (эхо) | — |
| GOD-13 Білобог | `GOD13_DONE` | `SWORD` (B), `PEACE` (C) | — |
| GOD-14 Семаргл | `GOD14_DONE` | `FALCON` (B), `FORGE` (эхо) | `HARVEST_SAVED` (только trigger) |
| GOD-15 Род | `GOD15_DONE` | `BLESSING` (B), `BOOK` (C) | — |

**Взаимные исключения:** B/C или B/эхо внутри одного квеста; A не ставит state. Проверено по финальным блокам P23:92–1551.

**Дефекты:** GOD-02 не читает `P22_Q04_DONE`; GOD-05/07/11/14 CHECK только в триггере, не в диалоге; GOD-05 при `P22_Q01_DONE` всё равно повторяет загадку (P23:454).

---

## 4. P24 — DARK-24-01…05

### DARK-24-01 «Борозна двох близнюків»

```
AVAILABLE (нет Q01_DONE) ── Овсій ──► IN_PROGRESS
IN_PROGRESS ── FAIL (борозну перервано) ──► IN_PROGRESS
IN_PROGRESS ── В4 ──► REFUSED ──► AVAILABLE
IN_PROGRESS ── A ──► DONE
IN_PROGRESS ── B ──► DONE + SHADOW_SLAIN
IN_PROGRESS ── C ──► DONE + BARROW_SEALED
```

- PACT: в A/B/C — условные реплики, метка/долг сохраняются (P24:99, 109, 118). PACT не сбрасывается.
- BURNED: **не проверяется**; сцена всегда живая Моровица → `GA-P24-001`.
- Повтор при DONE: только «Борозна пам'ятає твій крок»; PACT-реакция не повторяется → `GA-P24-001`.

### DARK-24-02 «Синє полум'я кургану»

```
AVAILABLE ── Охрім ──► IN_PROGRESS
FAIL (коло розімкнуто) ──► IN_PROGRESS; В4 ──► AVAILABLE
A ──► DONE; B ──► DONE + WRAITH_SLAIN; C ──► DONE + GOLD_SEALED
```

P24:198–222.

### DARK-24-03 «Ясенова колиска»

```
AVAILABLE ── Наталка ──► IN_PROGRESS
IN_PROGRESS ── шаг 1 (пошук слідів) ──► [ВИЗУАЛЬНЫЙ ГЕЙТ] ──► шаг 2 ──► шаг 3
FAIL (обряд зірвано) ──► IN_PROGRESS; В4 ──► AVAILABLE
A ──► DONE; B ──► DONE + MAMUNA_BANISHED; C ──► DONE + ODMINOK_HEALED
```

- Внешний CHECK: только `FLAG_P18_Q02_ASHES` (P24:242); `P18_Q02_DONE` не читается → `GA-P24-002`.
- Шаг 1 P24:276 — обязательный визуальный поиск → `GA-P24-003`.
- Реплики Мамуны в P24 нет; память кривдника не доставлена.

### DARK-24-04 «Зелені вінки»

```
AVAILABLE ── Роксана ──► IN_PROGRESS
FAIL (дарунок відкинуто) ──► IN_PROGRESS; В4 ──► AVAILABLE
A ──► DONE; B ──► DONE + WORMWOOD_BANISHED; C ──► DONE + WHIRLPOOL_CONQUERED
```

P24:414–437. «Дана» — незарегистрированный канон (`GA-P24-004`).

### DARK-24-05 «Короткий день»

```
AVAILABLE ── Світозар ──► IN_PROGRESS
FAIL (ватра згасла) ──► IN_PROGRESS; В4 ──► AVAILABLE
A ──► DONE; B ──► DONE + MACE_BROKEN; C ──► DONE + BREAD_PEACE
```

P24:517–540. Размежевание с P23 GOD-03/GOD-11 — P24:456 (канон-уровень).

---

## 5. P25 — TRYPIL / PODIL / KANIV

### TRYPIL-25-01

```
AVAILABLE (нет Q01_DONE) ── Велемира ──► IN_PROGRESS
FAIL (туман закрив розкоп) ──► IN_PROGRESS; В4 ──► AVAILABLE
A ──► DONE (без state)
B ──► DONE + BINOCLE
C ──► DONE + TEMPLE
DONE ── повтор ──► благословення без нагород
```

P25:66–164. BINOCLE/TEMPLE взаимоисключающие; A — только DONE.

### PODIL-25-02

```
AVAILABLE (нет Q02_DONE) ── рада в Рожанці ──► IN_PROGRESS
ШАГ 1: спуск у каньйон
ШАГ 2: прорив до Руської Брами
ШАГ 3: підйом шандор (затоплення)
FAIL (течія зірвала заслінку) ──► ШАГ 3 (retry)
В4 ──► REFUSED ──► AVAILABLE
A (все 3 шаги) ──► DONE
B (замість затоплення) ──► DONE + CHARGE   [мины не сняты]
C (рейд) ──► DONE + ALLIANCE               [мины/шлюзы не определены]
```

P25:237–258. **Дефект:** B/C не нейтрализуют 100 бочек под Рожанкой; B не описывает возврат из каньона к коннице; C не говорит, открыты ли шлюзы → `GA-P25-001`.

### KANIV-25-03

```
AVAILABLE (нет Q03_DONE) ── Остап ──► IN_PROGRESS
ШАГ 1: спорядження/дорога; ШАГ 2: слух дзвонів; ШАГ 3: клятва
FAIL (дзвони мовчать) ──► ШАГ 2 (retry); В4 ──► AVAILABLE
A ──► DONE
B ──► DONE + BANDURA
ЭХО ──► DONE + ECHO
```

P25:350–371. BANDURA/ECHO взаимоисключающие; A — только DONE.

---

## 6. Сводная проверка состояний

| Проверка | Результат |
|---|---|
| Все 31 квест имеют AVAILABLE/IN_PROGRESS/финалы/DONE | PASS |
| FAIL/REFUSED не ставят флаги | PASS |
| Повтор при DONE не выдаёт награды | PASS |
| B/C/эхо взаимоисключающие | PASS |
| P25 Q02 B/C завершают квест логически | **FAIL** |
| P24 Q03 шаг 1 доступен без зрения | **FAIL** |
| P24 Q01 BURNED-ветка | **FAIL** |
| P22/P23 узнавание в TTS | **FAIL (MEDIUM)** |
