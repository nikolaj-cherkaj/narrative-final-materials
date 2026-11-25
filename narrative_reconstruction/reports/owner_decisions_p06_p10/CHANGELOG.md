# CHANGELOG — OWNER DECISIONS P06–P10

**Дата:** 2026-11-25
**Вихідна гілка:** `agent/integration-p06-p10-fix-2aa9766`
**Вихідний SHA:** `cfccb15cd0cd32ea7191326910bbd1ad3d3d03ab`
**Робоча гілка:** `agent/owner-decisions-p06-p10-20261125-cfccb15`
**Робочий коміт:** `863d122` (змістовний коміт); фінальний коміт із цим CHANGELOG — наступний у гілці.

---

## 1. Канон

| Файл | Що змінено |
|---|---|
| `canon/TERMINOLOGY.md:17` | Замінено суперечливий §17 єдиним правилом: історичні міри — колорит; практично важлива величина — один короткий сучасний еквівалент при першому вживанні в сцені; без повторів і механічної заміни |
| `canon/TERMINOLOGY.md:36–37` | Старий §37 перетворено на уточнення до §17: перерахунок лише для практично важливої величини; колорит/ідіоми/гіперболи не перераховуються |
| `canon/FLAG_REGISTRY.md:4–5` | Версія 1.5 → 1.6; база — `cfccb15`; зафіксовані рішення Q1/Q2/Q3 |
| `canon/FLAG_REGISTRY.md` §0 | Додано реєстр зовнішніх залежностей; PACT → P24 |
| `canon/FLAG_REGISTRY.md` §8 | Строга послідовність MAIN-003 → MAIN-004 → MAIN-005; CHECK/залежності; перераховані рядки P08; `BASTION_BLOWN` отримав споживача P08:510 |
| `canon/FLAG_REGISTRY.md` §9 | `FLAG_P09_Q03_PACT` — CARRYOVER-абзац із посиланням на P24 |
| `reports/GLOBAL_MEASUREMENT_STANDARDS.md` | Додано статус-уточнення 2026-11-25: §17/§37 уніфіковано; пункт 3.3.2 читати з новим правилом |

---

## 2. Художні тексти — Q1 (історичні міри)

| Файл:рядок | Зміна |
|---|---|
| `revised/naratyvni_teksty_paket_1.md:41` | пів версти → + «десь пів кілометра» |
| `revised/naratyvni_teksty_paket_1.md:43` | півтори версти → + «десь півтора кілометра» |
| `revised/naratyvni_teksty_paket_1.md:71` | пів версти → + «десь за пів кілометра» |
| `revised/naratyvni_teksty_paket_1.md:258` | півверсти → + «десь пів кілометра» |
| `revised/naratyvni_teksty_paket_2.md:569` | півверсти → + «десь за пів кілометра» |
| `revised/naratyvni_teksty_paket_2.md:760` | півверсти → + «десь за пів кілометра» |
| `revised/naratyvni_teksty_paket_6.md:46` | півверсти → + «десь за пів кілометра» |
| `revised/naratyvni_teksty_paket_11.md:25` | три версти → + «десь три кілометри» |
| `revised/naratyvni_teksty_paket_11.md:26` | сорок сажнів → + «десь вісімдесят п'ять метрів» |
| `revised/naratyvni_teksty_paket_11.md:172` | пів версти → + «десь за пів кілометра» |
| `revised/naratyvni_teksty_paket_11.md:179` | верста → + «десь за кілометр» |
| `revised/naratyvni_teksty_paket_12.md:96` | п’ятнадцятисажневий → + «десь тридцятидвометровий» |
| `revised/naratyvni_teksty_paket_14.md:36` | півторасажнева → + «понад три метри заввишки» |
| `revised/naratyvni_teksty_paket_14.md:300` | п’ятнадцятисажневу → + «десь тридцятидвометрову» |
| `revised/naratyvni_teksty_paket_15.md:244` | три сажні → + «десь шість із половиною метрів» |
| `revised/naratyvni_teksty_paket_15.md:272` | двадцять п’ять сажнів → + «десь п'ятдесят три метри» |
| `revised/naratyvni_teksty_paket_16.md:273` | двісті сажнів → + «десь за чотириста двадцять шість метрів» |
| `revised/naratyvni_teksty_paket_19.md:132` | сорокапудова → + «шістсот п'ятдесятикілограмова» |
| `revised/naratyvni_teksty_paket_19.md:165` | 50 сажнів / 150 сажнів → + «по 107 метрів» / «320 метрів» |
| `revised/naratyvni_teksty_paket_20.md:641` | дві версти → + «десь два кілометри» |
| `revised/naratyvni_teksty_paket_23.md:62` | двопудовий → + «тридцятидвокілограмовий» |
| `revised/naratyvni_teksty_paket_30.md:264` | три сажні → + «понад шість метрів» |
| `revised/naratyvni_teksty_paket_35.md:249` | півторасажневий → + «понад триметровий» |
| `revised/naratyvni_teksty_paket_35.md:273` | глибина ліктя → + «десь пів метра» |

Разом: 24 точкові правки у 13 пакетах.

---

## 3. Художні тексти — Q2 (послідовність MAIN)

| Файл:рядок | Зміна |
|---|---|
| `revised/naratyvni_teksty_paket_8.md:6` | Додано шапкову фіксацію рішення Q2 і правило відкладеного входу |
| `revised/naratyvni_teksty_paket_8.md:359` | MAIN-004: вхід лише при `FLAG_P08_MAIN003_DONE`; зрозуміла репліка відкладеного входу |
| `revised/naratyvni_teksty_paket_8.md:469` | MAIN-005: вхід лише при `FLAG_P08_MAIN004_DONE` + ланцюгово `FLAG_P08_MAIN003_DONE`; зрозумілі репліки |

Самі Fail & Retry-блоки P08 не переписувалися.

---

## 4. Художні тексти — Q3 (Fail & Retry / accessibility)

| Файл:рядок | Було | Стало |
|---|---|---|
| `revised/naratyvni_teksty_paket_7.md:472` | «встигни озирнутися» | «встигни обернутися на голос» |
| `revised/naratyvni_teksty_paket_10.md:268` | «встигни озирнутися й присісти» | «встигни обернутися на голос і присісти» |
| `revised/naratyvni_teksty_paket_10.md:424` | «встигни озирнутися й зупинити удар» | «встигни відсахнутися від ковадла й зупинити удар» |

Інші блоки не уніфікувалися.

---

## 5. Нові звіти

| Файл | Призначення |
|---|---|
| `reports/owner_decisions_p06_p10/OWNER_DECISIONS_IMPLEMENTATION.md` | Що застосовано і де |
| `reports/owner_decisions_p06_p10/GLOBAL_HISTORICAL_MEASURES_AUDIT.md` | Аудит 36 пакетів |
| `reports/owner_decisions_p06_p10/MAIN_SEQUENCE_VALIDATION.md` | Матриця шляхів MAIN |
| `reports/owner_decisions_p06_p10/FLAG_REGISTRY_VALIDATION.md` | Звірка реєстру й текстів |
| `reports/owner_decisions_p06_p10/PACT_P24_CARRYOVER.md` | Передача PACT → P24 |
| `reports/owner_decisions_p06_p10/OWNER_DECISION_BRIEF.md` | Нові питання власнику (немає) |
| `reports/owner_decisions_p06_p10/CHANGELOG.md` | Цей файл |

---

## 6. Що не змінювалося

- `revised/naratyvni_teksty_paket_24.md` — не редагувався (PACT передано в P21–P25).
- P06–P10: раніше виправлені результати інтеграції збережені; масового художнього переписування немає.
- TTS, числовий баланс, XP, валюта, нагороди, ресурси — не тестувалися й не перебалансовувалися.
- Статуси `BALANCE VERIFIED`, `BALANCE PENDING`, `TTS VERIFIED`, `TTS PENDING` не створювалися.
- Історичні аудити й старі звіти не переписувалися.

---

## 7. Перевірки

```text
git diff --check
git status --short
grep -n "FLAG_P08_MAIN003_DONE\|FLAG_P08_MAIN004_DONE\|FLAG_P08_MAIN005_DONE" narrative_reconstruction/revised/naratyvni_teksty_paket_8.md
grep -n "гейт MAIN-004\|гейт MAIN-005" narrative_reconstruction/canon/FLAG_REGISTRY.md
```

Результат: `git diff --check` без помилок (лише попередження Git про CRLF); P08 має CHECK попереднього DONE; реєстр посилається на актуальні рядки.

---

## 8. Відомі обмеження

1. P24 не реалізує CHECK `FLAG_P09_Q03_PACT` — це завдання циклу P21–P25.
2. Старі сейви з `MAIN004_DONE` без `MAIN003_DONE` мають завершити MAIN-003 перед MAIN-005.
3. Повний ланцюг MAIN-001 → MAIN-002 → MAIN-003 не гейтувався; Q2 цього не вимагає.
4. Старі звіти про «вільний порядок MAIN-003–005» — історичні; актуальний стан у P08 і `FLAG_REGISTRY.md`.
