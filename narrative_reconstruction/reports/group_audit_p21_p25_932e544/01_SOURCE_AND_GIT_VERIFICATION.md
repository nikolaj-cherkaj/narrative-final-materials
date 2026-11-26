# 01 — SOURCE AND GIT VERIFICATION

**Дата:** 2026-11-26
**Аудиторская ветка:** `agent/group-audit-p21-p25-932e544`
**Проверяемый SHA:** `932e54469bd28cc525872675255df2237541f9dd`

---

## 1. Исходное состояние рабочей копии

До начала аудита:

```text
On branch agent/integration-p21-p25-fix-702f3b8
Your branch is up to date with 'origin/agent/integration-p21-p25-fix-702f3b8'.

Changes not staged for commit:
  modified:   narrative_reconstruction/prompts/03_group_independent_audit.md

Untracked files:
  "3 промпт запуск.txt"
  narrative_reconstruction/01_single_package_artistic_revision.md
  narrative_reconstruction/02_group_integration_and_remediation.md
  narrative_reconstruction/03_group_independent_audit.md
  narrative_reconstruction/04_global_flag_registry_repair_p01_p05.md
  "Новый текстовый документ.txt"
```

Это пользовательские изменения/заметки. Они **не включались** в аудит, не коммитились и не изменялись. Аудиторские отчёты созданы отдельно в `reports/group_audit_p21_p25_932e544/`.

**HEAD до создания ветки:**

```text
$ git rev-parse HEAD
932e54469bd28cc525872675255df2237541f9dd
```

---

## 2. Fetch и удалённые ветки

Выполнено:

```text
$ git fetch origin --prune
$ git rev-parse origin/agent/integration-p21-p25-fix-702f3b8
932e54469bd28cc525872675255df2237541f9dd
```

Удалённая ветка совпадает с локальной проверяемой веткой. Ошибки `b857a7f` (аудит P16–P20) не использовались.

Ключевые remote-ветки:

| Ветка | Назначение | SHA |
|---|---|---|
| `origin/agent/integration-p21-p25-fix-702f3b8` | вторая ремедиация P21–P25 | `932e544` |
| `origin/agent/group-audit-p21-p25-7a1db2c` | предыдущий независимый аудит | `702f3b8` |
| `origin/agent/integration-p21-p25-fix-be57fe0` | исходная интеграция P21–P25 | `7a1db2c` |
| `origin/agent/package-p21-20261125-b857a7f` | индивидуальная редактура P21 | `e564365` |
| `origin/agent/package-p22-20261125-e564365` | индивидуальная редактура P22 | `6e03ce4` |
| `origin/agent/package-p23-20261125-6e03ce4` | индивидуальная редактура P23 | `a67e2c7` |
| `origin/agent/package-p24-20261125-a67e2c7` | индивидуальная редактура P24 | `c0495b6` |
| `origin/agent/package-p25-20261125-c0495b6` | индивидуальная редактура P25 | `be57fe0` |

---

## 3. Родословная коммитов второй ремедиации

Проверено:

```text
$ git log --oneline --reverse 702f3b8..932e544
9aebb71 fix: remediate P21-P25 audit 7a1db2c - PACT/BURNED, PODIL mines, accessibility, P18/P22/P23 recognition; sync registries; reports integration_p21_p25_remediation_2
f2beaed fix: correct P22->P23 recognition references and refresh checksums
fb2c350 docs: align Mokosh recognition wording and refresh checksums
932e544 fix: soften P22 Marena recognition to cover all P23 GOD-11 finals; refresh checksums
```

Родители:

| Коммит | Родитель | Комментарий |
|---|---|---|
| `9aebb71` | `702f3b8` | Основной ремонт; родитель — docs-align предыдущего аудита |
| `f2beaed` | `9aebb71` | Правка P22→P23 recognition |
| `fb2c350` | `f2beaed` | Правка формулировки Мокош |
| `932e544` | `fb2c350` | Смягчение P22 Марены; HEAD |

Проверка ancestry:

```text
$ git merge-base --is-ancestor 702f3b8 932e544
(exit 0 — 702f3b8 является предком 932e544)
```

Итог: проверяемая база действительно содержит **все четыре коммита** второй ремедиации и **все 13 отчётов** предыдущего аудита (`reports/group_audit_p21_p25_7a1db2c/` — 13 файлов). Название ветки не использовалось как единственный критерий; проверены SHA, родители и содержимое.

---

## 4. Новая аудиторская ветка

Создана от подтверждённого HEAD:

```text
$ git switch -c agent/group-audit-p21-p25-932e544
$ git rev-parse HEAD
932e54469bd28cc525872675255df2237541f9dd
```

Старая ветка аудита не переиспользовалась, история не переписывалась.

---

## 5. Охват файлов второй ремедиации

`git diff --name-status 702f3b8..932e544` — 26 файлов:

### 5.1. Игровые тексты (5)

| Файл | Изменение | Net строк |
|---|---|---:|
| `revised/naratyvni_teksty_paket_22.md` | recognition-реплики, «хуртовина», «останній подих» | +12 |
| `revised/naratyvni_teksty_paket_23.md` | GOD-02 CHECK/реплики, GOD-05/07/11/14 реплики | +15 |
| `revised/naratyvni_teksty_paket_24.md` | PACT/BURNED, DARK-24-03 маршрут/Мамуна, «Вербовий вир», Бориско | +68 |
| `revised/naratyvni_teksty_paket_25.md` | обязательные Кроки 3–4, переход, P26-смягчение | +3 |
| `revised/naratyvni_teksty_paket_5.md` | одна строка BEST-005 | 0 (1/1) |

P21 не изменялся. P01–P04 не изменялись. P26–P36 не изменялись.

### 5.2. Канон и реестры (3)

- `canon/CHARACTERS.md` — v2.1, 417 записей, шапка/футер.
- `canon/FLAG_REGISTRY.md` — v2.17, §0, §9, §22–§25.
- `reports/GLOBAL_CARRYOVER_REGISTER.md` — §1, §2.9, §3.2, история.

### 5.3. Резервные копии (9)

Созданы в `original_backup/` для P05, P21–P25, CHARACTERS, FLAG_REGISTRY, GLOBAL_CARRYOVER_REGISTER. Прежние backup-файлы не перезаписывались.

### 5.4. Отчёты второй ремедиации (9)

`ACCESSIBILITY_REVIEW.md`, `AUDIT_CHECKSUMS.sha256`, `CHANGELOG.md`, `CROSS_PACKAGE_DEPENDENCIES.md`, `FINDING_REMEDIATION_MATRIX.md`, `FLAG_LIFECYCLE_AUDIT.md`, `OWNER_DECISIONS.md`, `PLAYER_PATH_TESTS.md`, `REMEDIATION_REPORT.md`.

Итого 5 + 3 + 9 + 9 = **26 файлов**.

---

## 6. Контрольные суммы

`reports/integration_p21_p25_remediation_2/AUDIT_CHECKSUMS.sha256` содержит 18 записей. Проверка по git-блобам HEAD:

```text
bad = 0
```

Все 18 SHA-256 совпадают с содержимым `HEAD:path`. Три файла в рабочей копии имеют CRLF (`P24`, `FLAG_REGISTRY`, `CHARACTERS`), поэтому побайтовый `Get-FileHash` рабочей копии для них отличается от LF-блоба; это line-ending артефакт, а не расхождение содержимого. Контрольные суммы корректны для репозиторного содержимого.

---

## 7. Проверка отсутствия запрещённых изменений

```text
$ git diff --stat 702f3b8..932e544 -- reports/group_audit_p21_p25_7a1db2c
(пусто)

$ git diff --stat 702f3b8..932e544 -- revised/naratyvni_teksty_paket_1.md ... _4.md
(пусто)
```

- 13 отчётов предыдущего аудита не изменялись.
- P01–P04 не изменялись.
- P05 изменён ровно на 1 строку (1 добавлена, 1 удалена).
- P21 не изменялся.
- Канон/реестры изменены только в объёме, заявленном второй ремедиацией.

---

## 8. Ограничения

- Аудит статический, по тексту и Git.
- TTS, голоса, скринсдеры, игровой движок, баланс, XP/валюта/карма/ресурсы не тестировались.
- P26–P30 проверялись только в объёме перенесённых обязательств; полный аудит этих пакетов не выполнялся.
- Строки указаны по текущему SHA `932e544`; при дальнейших правках номера могут сместиться.
