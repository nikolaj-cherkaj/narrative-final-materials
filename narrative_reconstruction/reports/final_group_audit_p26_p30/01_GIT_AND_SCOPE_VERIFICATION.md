# 01. GIT И ПРОВЕРКА ГРАНИЦ ИЗМЕНЕНИЙ

**Дата:** 2026-11-26

**Репозиторий:** `https://github.com/nikolaj-cherkaj/narrative-final-materials`

---

## 1. Контрольные точки

| Роль | Ветка | HEAD | Подтверждение |
|---|---|---|---|
| Интеграционная база | `agent/integration-p26-p30-fix-cd9df80` | `d3dd245459c4913f492fe290211ef0207d8cb30c` | `git rev-parse`, `git cat-file -t` |
| Первоначальный аудит | `agent/group-audit-p26-p30-d3dd245` | `fbe18130fb3c798ab675719c3eebf722a155ee63` | `git rev-parse`; ветка содержит только отчёты |
| Контентная ремедиация | `agent/integration-p26-p30-remediation-d3dd245` | `3c081292cfd97d162e22e7c1de52e3176a7512ce` | `git cat-file -t` |
| Финальный code-fix | та же | `ce7e1a2153cb7d7262fb5d802ce9fc1785ec1201` | `git cat-file -t` |
| **Проверяемый HEAD** | та же | **`d2b4e5dfd25d152f0cfe817355abd90d2c28dd68`** | `git rev-parse HEAD` |
| Remote HEAD | `origin/agent/integration-p26-p30-remediation-d3dd245` | `d2b4e5d` | `git log --oneline` |
| Ветка аудита | `agent/group-audit-p26-p30-d2b4e5d` | создана от `d2b4e5d` | `git switch -c` |

`d3dd245` является предком `d2b4e5d` (`git merge-base --is-ancestor d3dd245 HEAD` → exit 0). `fbe1813` — потомок `d3dd245` и содержит только аудиторские отчёты. История не переписана.

---

## 2. Коммиты между базой и проверяемым HEAD

```
d2b4e5d docs: record final P26-P30 remediation HEAD
ce7e1a2 fix: align P30 Q04 repeat phrase with fern final
024fa57 docs: align P26-P30 carryover line reference
22b7061 docs: finalize P26-P30 remediation git state
75b1dfa docs: record P26-P30 remediation git state and report index
3c08129 fix: targeted remediation P26-P30 (GA-P28-001 horn lifecycle, final actions, state repeats, P29 G/fail); reports integration_p26_p30_remediation
```

Изменённые файлы (30, `git diff --stat d3dd245 HEAD`):

| Категория | Файлы |
|---|---|
| Пакеты P26–P30 | `naratyvni_teksty_paket_26.md`, `27`, `28`, `29`, `30` |
| Пакет P15 | `naratyvni_teksty_paket_15.md` |
| Канон | `canon/CHARACTERS.md`, `canon/FLAG_REGISTRY.md` |
| Глобальный реестр | `reports/GLOBAL_CARRYOVER_REGISTER.md` |
| Отчёт интеграции | `reports/integration_p26_p30/INTEGRATION_REPORT.md` |
| Журнал | `change_log/CHANGELOG_2026-11-26_REMEDIATION_P26_P30.md` |
| Резервные копии | 9 файлов `original_backup/*_pre_remediation_2026-11-26.md` |
| Отчёты ремедиации | 10 файлов `reports/integration_p26_p30_remediation/` |

---

## 3. Проверка границ

| Ожидалось | Фактически | Статус |
|---|---|---|
| P26–P30 | P26–P30 | OK |
| Реестры, отчёты, резервные копии, журнал | Есть | OK |
| P15 только эхо `LIVING_WATER` | **П15 финал А + эхо `LIVING_WATER`** | **Отклонение** |
| P13, P14, P19, P25 не изменять | Не изменены | OK |
| P21–P25 не изменять | Не изменены | OK |
| P31–P36 не изменять | Не изменены | OK |
| `main` не изменять | Не изменена | OK |
| Ветки интеграции/аудита не изменять | Не изменены | OK |
| Промпты пользователя не включать в коммит | Не включены | OK |
| Старые отчёты и резервные копии не удалять | Не удалены | OK |
| Новые механики/флаги не добавлять | Новых FLAG-ID нет; добавлены только сюжетные choice-блоки и Этап 2В | OK |

### 3.1. Отклонение P15

`git diff d3dd245 HEAD -- narrative_reconstruction/revised/naratyvni_teksty_paket_15.md` содержит **два** хунка:

1. **Финал А** (`P15:358–359`):
   - было: «Гравець кладе золотий ріг до вузлика.»
   - стало: «Гравець кладе золотий ріг до вузлика **й забирає вузлик із собою**.»
   - в строке флагов добавлено: «Ріг лишається в героя у вузлику до P28 FOLK-28-02, де герой повертає його владиці.»
2. **Эхо `LIVING_WATER`** (`P15:383–384`):
   - добавлен возврат рога владыке и уточнение, что второго рога нет.

Финал Б (`P15:368–376`) не изменён. SET/CHECK/CLEAR, награды, титулы, числа и NPC P15 не изменены. Это **не игровая регрессия**, но формально это выход за объявленную пользователем границу «P15 только эхо `LIVING_WATER`». Ремедиация сама declares это в `CHANGED_FILES.md:15`, `CHANGELOG...:14`, `GIT_STATE.md:47`; противоречие именно с ограничением задания, а не скрытая правка.

**Рекомендация:** владельцу подтвердить, что уточнение финала А является частью согласованного исправления `GA-P28-001`; иначе откатить финал А и перенести утверждение о владении рогом полностью в P28 (что ослабит доказательство, потому что P15 перестанет явно говорить, что герой забирает вузлик).

---

## 4. Проверка резервных копий

Резервные копии `original_backup/*_pre_remediation_2026-11-26.md` добавлены в коммите. Содержимое сверено с `d3dd245`:

| Копия | Содержимое совпадает с базой |
|---|---|
| `naratyvni_teksty_paket_15_pre_remediation...` | Да |
| `..._26_...` | Да |
| `..._27_...` | Да |
| `..._28_...` | Да |
| `..._29_...` | Да |
| `..._30_...` | Да |
| `FLAG_REGISTRY_pre_remediation...` | Да (различие только CRLF/LF) |
| `CHARACTERS_pre_remediation...` | Да (различие только CRLF/LF) |
| `GLOBAL_CARRYOVER_REGISTER_pre_remediation...` | Да |

Побайтовые SHA-256 для `FLAG_REGISTRY` и `CHARACTERS` различаются из-за CRLF, но `git diff --no-index` не показывает содержательных различий. Это нормально для `core.autocrlf=true`.

---

## 5. Проверка отсутствия неожиданных изменений

- `git diff --name-only d3dd245 HEAD` не содержит P13, P14, P19, P25, P31–P36.
- Не изменены `prompts/02...`, `prompts/03...` в коммите; они остаются локальными незакоммиченными изменениями пользователя.
- Не изменены `main`, интеграционная ветка, ветка первоначального аудита, ветка ремедиации (кроме собственных коммитов ремедиации).
- Новые FLAG-ID не добавлены: 66 внутренних + 5 внешних, все уже были в реестре; `FLAG_P28_Q02_VOICE` не создан.
- Новые механики: только сюжетные choice-блоки и счётчик `[0/1]` Этапа 2В; новых кнопок/QTE/флагов нет.
- Числовые параметры/награды не перебалансированы; изменения чисел носят редакционный характер (16 NPC, «Роса», «карателів», «трипудові»).

---

## 6. Охват

**Полностью прочитано:** P15 Q03, P26–P30 (2 490 строк), `FLAG_REGISTRY.md` §0/§15/§26–§30, `CHARACTERS.md` (целевые карточки/таблицы), `GLOBAL_CARRYOVER_REGISTER.md` §2.10/§3.3, все отчёты `integration_p26_p30` и `integration_p26_p30_remediation`, changelog, резервные копии, целевые места P13, P14, P19, P25.

**Не входило:** TTS, голоса, движки, баланс чисел, полный аудит P01–P12/P16–P25/P31–P36.

---

## 7. Ветка аудита

- Создана от `d2b4e5dfd25d152f0cfe817355abd90d2c28dd68`.
- Имя: `agent/group-audit-p26-p30-d2b4e5d`.
- В ветке сохраняются только отчёты в `narrative_reconstruction/reports/final_group_audit_p26_p30/`.
- Игровые пакеты, канон, резервные копии и журналы не изменяются.
