# 04 — CHANGE SCOPE AND GIT

**Дата:** 2026-11-26
**Исходная ветка:** `agent/group-audit-p21-p25-932e544`
**Исходный SHA:** `5ed927ba4cc756a92f74be3bbaa1ab900fb78d77`
**Рабочая ветка:** `agent/integration-p21-p25-fix-5ed927b` (создана от `5ed927b`)

---

## 1. Проверка исходной базы

```text
$ git status
On branch agent/group-audit-p21-p25-932e544
HEAD 5ed927ba4cc756a92f74be3bbaa1ab900fb78d77

$ git fetch origin --prune
$ git rev-parse origin/agent/group-audit-p21-p25-932e544
5ed927ba4cc756a92f74be3bbaa1ab900fb78d77
```

Локальный HEAD и `origin` совпадают. История:

```text
5ed927b docs: independent group audit P21-P25 (932e544) - GROUP AUDIT NO-GO
932e544 fix: soften P22 Marena recognition to cover all P23 GOD-11 finals
fb2c350 docs: align Mokosh recognition wording and refresh checksums
f2beaed fix: correct P22->P23 recognition references and refresh checksums
9aebb71 fix: remediate P21-P25 audit 7a1db2c - PACT/BURNED, PODIL mines...
702f3b8 docs: align P21-P25 audit notes on reward titles and diff check
```

`702f3b8` — предыдущий аудит; `9aebb71..932e544` — вторая ремедиация. Новая ветка создана от подтверждённого `5ed927b`; старые ветки не переиспользовались, история не переписывалась.

---

## 2. Изменённые исходные файлы

| Файл | Строки | Diff | Причина |
|---|---:|---|---|
| `narrative_reconstruction/revised/naratyvni_teksty_paket_23.md` | 460 | 1 строка заменена | `GA2-P23-001`: убрать ложную память Велеса |
| `narrative_reconstruction/revised/naratyvni_teksty_paket_24.md` | 314, 344 | 2 строки заменены | `GA2-P24-001`: убрать противоречие Наталки-проводника |

Полный diff:

```diff
P23:460
-«Ти вже стояв у моєму колі в Чорному Яру. Тоді я питав, що дорожче за золото, — і ти відповів. Не буду питати двічі...»
+«Ти вже стояв у моєму колі в Чорному Яру. Тоді ти приніс дари й вистояв перед Рогатим Володарем. Не буду питати двічі...»

P24:314
-«...Приходь, коли серце буде готовим, — тоді й підемо на болото.»
+«...Приходь, коли серце буде готовим, — тоді й рушиш на болото.»

P24:344
-«Наталка йде попереду й на кожній прикметі називає наступну вголос... якщо збився, Наталка повторює назву...»
+«Наталка лишається в хаті біля колиски й перед дорогою називає п'ять прикмет по порядку...»
```

---

## 3. Файлы, которые не изменялись

Проверено `git diff 5ed927b -- <path>` — пусто:

- `revised/naratyvni_teksty_paket_21.md`
- `revised/naratyvni_teksty_paket_22.md`
- `revised/naratyvni_teksty_paket_25.md`
- `revised/naratyvni_teksty_paket_5.md`
- `canon/FLAG_REGISTRY.md`
- `canon/CHARACTERS.md`
- `reports/GLOBAL_CARRYOVER_REGISTER.md`
- P01–P04, P16–P20, P26–P36 (не открывались/не изменялись)

P05 BEST-005 / `GC-P21-P05-001` не затронут. P25 / `GC-P25-P26-001` не затронут.

---

## 4. Новые отчёты

Создан каталог `narrative_reconstruction/reports/integration_p21_p25_remediation_3/`:

- `00_REMEDIATION_SUMMARY.md`
- `01_GA2-P23-001_VELES.md`
- `02_GA2-P24-001_NATALKA.md`
- `03_REGRESSION_CHECK.md`
- `04_CHANGE_SCOPE_AND_GIT.md`

Старые отчёты и backup-файлы не изменялись.

---

## 5. Коммит и push

Коммит ремедиации создан в ветке `agent/integration_p21-p25-fix-5ed927b` после подготовки отчётов. SHA коммита и статус push: `7c3e9760e874016fbc8ce2cc20d02d85cb35ab5e`; `origin/agent/integration-p21-p25-fix-5ed927b` указывает на этот SHA; в `main` ничего не сливалось.

История после коммита:

```text
7c3e976 docs: targeted remediation P21-P25 (GA2-P23-001, GA2-P24-001) ...
5ed927b docs: independent group audit P21-P25 (932e544) - GROUP AUDIT NO-GO ...
932e544 fix: soften P22 Marena recognition to cover all P23 GOD-11 finals
...
```

---

## 6. Проверка diff

| Проверка | Результат |
|---|---|
| P23 изменён только в строке 460 | **PASS** |
| P24 изменён только в строках 314 и 344 | **PASS** |
| P21/P22/P25/P05 не изменялись | **PASS** |
| Канон/реестры не изменялись | **PASS** |
| Новые флаги/механики/персонажи/локации не добавлены | **PASS** |
| `git diff --check` — без whitespace-ошибок | **PASS** (только CRLF-предупреждение) |
| Код-фенсы P23/P24 чётные | **PASS** (60/20) |
| В `main` ничего не сливалось | **PASS** |

---

## 7. Ограничения

- Аудит/ремедиация статические; TTS, голоса, скринсдеры, движок, баланс и числовые награды не тестировались.
- P26–P30 проверялись только в объёме `GC-P25-P26-001`; полный аудит не выполнялся.
- LOW/OBS-замечания (`GA2-P24-002`, `GA2-DOC-001`, `GA2-P25-001`, `GA2-P24-003`, `GA2-DOC-002`, `GA2-P25-002`, `GA2-P22-001`, `GA2-P24-004`) не исправлялись по условиям задания.
