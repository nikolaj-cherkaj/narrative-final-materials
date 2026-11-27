# 03. SOURCE DIFF VALIDATION — P01–P36

## 1. Проверенная база

| Параметр | Значение |
|---|---|
| Base реализации | `f12581e13f9546937c1042c8274093278af68463` |
| HEAD реализации | `1a103b0dca2201e7d6ba788b283757fac59ed200` |
| HEAD аудита до отчётов | `11e8f7453723ff90a9f0651fbfde1e220462ba4a` |
| Diff игровых текстов | `f12581e..1a103b0` |
| Файлов в diff | **29** = 28 пакетов + `FLAG_REGISTRY.md` |
| Строк | **278 добавлено / 197 удалено** |
| Новые флаги / ID | **0** |

## 2. Полный список изменённых игровых файлов

- `narrative_reconstruction/canon/FLAG_REGISTRY.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_2.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_3.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_4.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_5.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_6.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_7.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_8.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_9.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_10.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_12.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_13.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_14.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_15.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_16.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_17.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_18.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_19.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_20.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_21.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_23.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_24.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_27.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_31.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_32.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_33.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_34.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_35.md`
- `narrative_reconstruction/revised/naratyvni_teksty_paket_36.md`

Не менялись: P01, P11, P22, P25, P26, P28, P29, P30. Их зависимые места проверены точечно (P01 D-015/D-012; P22/P23 Велес; P25/P26 Устим; P28 рог; P29 Лейба; P30 без активных связей).

## 3. Изменения `FLAG_REGISTRY.md`

Изменены только формулировки двух групп:

1. `FLAG_NALIVAYKO_SOLONYTSIA_HERO`, `_LAST_STAND`, `_SHADOW_RETREAT` — один из трёх, один раз за прохождение, permanent; LAST_STAND терминальный.
2. `FLAG_P35_Q04_DONE` — добавлено пояснение: в финале В крипта открыта механизмом и снова запечатана гулом дзвонов.

**Новые ID не добавлялись; семантика существующих флагов не менялась, кроме уточнения, утверждённого B06/B17.**

## 4. Проверка 35 дефектов `NEW-01…NEW-35`

| ID | Пакет | Фактическое подтверждение в текущем тексте | Статус |
|---|---|---|---|
| NEW-01 | P09 | Перстень после Варіантів 1–4: P09:192, 228, 259; отказ не даёт. | **VERIFIED FIXED** |
| NEW-02 | P31 | Рушник после любой согласии (1–3): P31:47, 55, 63; Олена — запасной. | **VERIFIED FIXED** |
| NEW-03 | P35 | 6 смолоскипов, 5 сгорают, шестой остаётся: P35:69, 72, 84, 114. | **VERIFIED FIXED** |
| NEW-04 | P35 | Этап 3 только после отказа от варты; А/Б/В: P35:442–452, 473/485/496. | **VERIFIED FIXED** |
| NEW-05 | P33 | Судьба Мотри: P33:71–73 (А — громада, В — под вартой Ярины). | **VERIFIED FIXED** |
| NEW-06 | P08 | Оверко сам садится на коня: P08:216. | **VERIFIED FIXED** |
| NEW-07 | P14 | Кованый клин в Этапе 1: P14:174–177; действие в Этапе 2 — P14:183. | **VERIFIED FIXED** |
| NEW-08 | P36 | Горілка/сукно и дишель: P36:447, 456. | **VERIFIED FIXED** |
| NEW-09 | P02/P04 | Кровь в обоих финалах: P02:598–599; P04:1960/1968. | **VERIFIED FIXED**; см. O-01 |
| NEW-10 | P36 | Копия креслення → Кіш → грамота: P36:77, 129, 130. | **VERIFIED FIXED** |
| NEW-11 | P09 | Олия у Тимоша до похода: P09:262. | **VERIFIED FIXED** |
| NEW-12 | P36 | Пакет выдают и при оплате мита: P36:203. | **VERIFIED FIXED** |
| NEW-13 | P17 | Охра/уголь объединены `[0/3, 0/3]`: P17:409; дубль убран. | **VERIFIED FIXED** |
| NEW-14 | P20 | Рекорд без таймера: P20:713, 717, 731–734. | **VERIFIED FIXED** |
| NEW-15 | P33 | Мята/пепел в Этапе 1: P33:61–62, 72. | **VERIFIED FIXED** |
| NEW-16 | P07/P16 | Нумерация P07:2038–2044; P16:291–296. | **VERIFIED FIXED** |
| NEW-17 | P36 | Дишель и заготовки: P36:456. | **VERIFIED FIXED** |
| NEW-18 | P20 | Знак/ниша только Б/В; А без них: P20:185–187, 209, 222, 234. | **VERIFIED FIXED** |
| NEW-19 | P36 | Отдельный маршрут В CRAFT-02: P36:215–216, 259. | **VERIFIED FIXED** |
| NEW-20 | P36 | Выбор А/Б/В после полёта: P36:91, 107, 118, 129. | **VERIFIED FIXED** |
| NEW-21 | P35 | BAKOTA А/Б раздельно: P35:448–452, 473, 485. | **VERIFIED FIXED** |
| NEW-22 | P35 | Сокира в финале Б CARNIVAL-03: P35:324, 358. | **VERIFIED FIXED** |
| NEW-23 | P35 | Голос Антония сквозь гул: P35:442. | **VERIFIED FIXED** |
| NEW-24 | P19 | Петля Дорофия крепит спуск: P19:210, 215. | **VERIFIED FIXED** |
| NEW-25 | P15 | Щит у Крамаря: P15:233, 241. | **VERIFIED FIXED** |
| NEW-26 | P08 | Покупатель в клуне: P08:228. | **VERIFIED FIXED** |
| NEW-27 | P06 | Дым из сырой травы: P06:381. | **VERIFIED FIXED** |
| NEW-28 | P23 | Дар после трёх вопросов: P23:474–478, 520, 526, 533. | **VERIFIED FIXED** (GOD-05; не путать с F-07 в GOD-03) |
| NEW-29 | P33 | Отвар меда/деревия: P33:73, 98. | **VERIFIED FIXED** |
| NEW-30 | P09 | «Варіанти 1–4», отказ без перстня: P09:228. | **VERIFIED FIXED** |
| NEW-31 | P35 | Подпись финала Б: P35:466. | **VERIFIED FIXED** |
| NEW-32 | P35 | Гейт 6/6 при повторе: P35:84. | **VERIFIED FIXED** |
| NEW-33 | P20 | «Записываю заезд для рекорда»: P20:717/722. | **VERIFIED FIXED** |
| NEW-34 | P31 | Шесть действий: P31:75. | **VERIFIED FIXED** |
| NEW-35 | P19 | Три гнезда в трёх дворах: P19:222, 256–257. | **VERIFIED FIXED** |

**Итог:** 35/35 заявленных исправлений подтверждены фактическим текстом. Ни одно исправление не откатилось. Остаточные проблемы F-01…F-09 — новые, не входящие в этот список.

## 5. Контрольные суммы

SHA-256 всех 36 пакетов и `FLAG_REGISTRY.md` находятся в `CHECKSUMS.sha256` этого каталога. Они сняты с текущего состояния `11e8f74` до добавления отчётов.
