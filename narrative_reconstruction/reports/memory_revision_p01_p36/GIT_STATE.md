# GIT STATE — MEMORY REVISION P01–P36

- **Вихідна підтверджена база:** `55f218c` — гілка `agent/global-memory-audit-p01-p36-20261126`, вершина аудиту пам'яті P01–P36 на основі інтеграції P31–P36 (`4d752bf`) та художніх редакцій P01–P36.
- **Вихідна робоча копія:** `D:\audiotale тз\narrative-final-materials` на `c21dbd1` (не використовувалася; має сторонні незакоммічені файли).
- **Робочий worktree:** `D:\audiotale тз\memory-revision-p01-p36-20261126`.
- **Нова унікальна гілка:** `agent/memory-revision-p01-p36-20261126`.
- **Базова гілка не змінювалася:** `main`, `agent/global-memory-audit-p01-p36-20261126` та інші гілки залишені без змін.
- **Деструктивні операції:** не виконувалися (без reset, clean, force-push, переписування історії).

## Коміт

- **Commit:** цей commit (див. `git log -1 --format=%H`).
- **Final SHA:** `HEAD` цієї гілки після коміту; точне значення — у виводі `git log -1 --format=%H` та в фінальному повідомленні сесії.
- **Push:** `git push -u origin agent/memory-revision-p01-p36-20261126`; статус — у виводі команди.

## Змінені ігрові пакети

P01, P02, P03, P04, P05, P07, P08, P09, P10, P11, P12, P13, P14, P15, P16, P17, P18, P19, P20, P21, P22, P23, P24, P25, P26, P27, P28, P29, P30, P31, P32, P33, P34, P35, P36.

**P06 не змінювався:** у ньому не було цільових формул пам'яті або повторних заглушок.

## Створені звіти

- `MEMORY_REVISION_SUMMARY.md`
- `MEMORY_REVISION_CHANGELOG.md`
- `REPEAT_DIALOGUE_STANDARD.md`
- `MEMORY_REACTION_STANDARD.md`
- `ECHO_FAME_REVIEW.md`
- `P01_GAVRYLO_REACTION_REVIEW.md`
- `UNCONFIRMED_NARRATIVE_PROMISES.md`
- `OWNER_DECISIONS_REQUIRED.md`
- `FINAL_VALIDATION.md`
- `GIT_STATE.md`

## Перевірки перед комітом

- `FLAG_*`: 489 до / 489 після; відсутніх або нових немає.
- `NPC-####`: 308 до / 308 після; відсутніх або нових немає.
- `SET `: 337 / 337; `CHECK`: 355 / 355; `CLEAR`: 292 / 292.
- Канонічні документи, `FLAG_REGISTRY`, `GLOBAL_CARRYOVER_REGISTER`, нагороди й механіки не змінювалися.
- У тригерах і повторних зверненнях формула «X пам'ятає Y» відсутня.
- «Лише пам'ять» у пакетах відсутня.
- Залишені 37 входжень «пам'ятає/пам'ятають» — пряма мова, лор, відкладена обіцянка або предмет-протокол; перелік у `FINAL_VALIDATION.md`.
- У commit включено лише `narrative_reconstruction/revised/` і `narrative_reconstruction/reports/memory_revision_p01_p36/`.
