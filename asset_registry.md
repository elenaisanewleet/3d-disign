# Asset registry v1.1

Реестр для Claude Design / 3D. Это не каталог SKU. Он отделяет то, что **видно/подтверждено**, от того, что **вероятно**, и задаёт fidelity при моделировании.

## Confidence legend

- `USER-CONFIRMED` — факт прямо подтверждён пользователем.
- `CONFIRMED` — тип объекта уверенно читается по фотобазе.
- `LIKELY` — вероятная идентификация по форме/контексту.
- `UNRESOLVED` — геометрия понятна, точная функция не установлена.
- `MUST-KEEP` — обязательный identity anchor.

---

# P0 — identity anchors

## P-001 — Картина-натюрморт в деревянной раме
- category: personal artifact
- confidence: `USER-CONFIRMED`
- priority: `MUST-KEEP / P0`
- 3D fidelity: **very high**
- instruction: смоделировать именно этот объект; повесить на стену; не заменять похожей картиной.

## P-002 — Ножницы на круглом абразивном/отрезном диске
- category: wall artifact / functional found object
- confidence: `USER-CONFIRMED`
- priority: `MUST-KEEP / P0`
- 3D fidelity: **very high**
- instruction: сохранить ножницы, реальный круг и логику подвеса; можно очистить и дать хороший локальный свет; не превращать в logo sculpture.

## P-003 — Чёрная сумка с котом
- category: personal artifact
- confidence: `USER-CONFIRMED`
- priority: `MUST-KEEP / P0`
- 3D fidelity: high

## P-004 — Реальные книги
- category: personal/cultural artifact
- confidence: `CONFIRMED`
- priority: `MUST-KEEP / P0`
- identified families: Пушкин, Бальзак, Достоевский, русско-английский словарь, пособие по элементарной физике
- instruction: не заменять generic luxury books.

## P-005 — Стена реальных пил и ножовок
- category: hand-tool composition
- confidence: `CONFIRMED`
- priority: `MUST-KEEP / AUTHENTICITY ANCHOR`
- 3D fidelity: high
- instruction: моделировать как композиционный объект стены, сохраняя разнообразие реальных пил.

## P-006 — Самодельный приводной агрегат
- category: machine / custom tooling
- confidence: `CONFIRMED geometry / UNRESOLVED exact process`
- priority: `MUST-KEEP / P0`
- 3D fidelity: **very high**
- visible: электродвигатель, ременная передача, вал, подшипниковые опоры, рабочий круг/диск
- instruction: не заменять магазинным станком.

## P-007 — Трёхкомнатная последовательность
- category: spatial
- confidence: `USER-CONFIRMED`
- priority: `MUST-KEEP / P0`
- sequence: ROOM 1 входная → ROOM 2 основная рабочая → ROOM 3 складско-бытовая с розовым диваном.

## P-008 — Реальный сад как внешний контекст
- category: spatial/environmental
- confidence: `CONFIRMED`
- priority: `MUST-KEEP`
- instruction: новые большие окна могут кадрировать реальную зелень; сад — источник света/атмосферы, не декоративная выдумка.

---

# Машины и стационарная оснастка

## A-001 — Ручной рычажный пресс с индивидуальной оснасткой
- confidence: `CONFIRMED`
- 3D fidelity: high
- visible: тяжёлая C-образная рама, длинный рычаг, возвратная пружина, вертикальный шток, матрица/пуансон, основание с отверстиями/упорами
- likely function: повторяемая операция с позиционированием заготовки
- exact operation: `UNRESOLVED`
- replace: **no**
- restore/clean: yes

## A-002 — Вертикальный сверлильный станок / drill press
- confidence: `CONFIRMED`
- 3D fidelity: high
- visible: колонна, шпиндель, патрон, ручная вертикальная подача, массивная база, деревянная установочная площадка
- replace with modern branded machine: **no**

## A-003 — Красно-зелёная powered drilling/pressing station with dedicated jig
- confidence: `CONFIRMED geometry / UNRESOLVED exact process`
- 3D fidelity: **very high**
- visible: электропривод, вертикальная рабочая часть, патрон/инструмент, позиционирующая оснастка
- nearby evidence: партии одинаковых металлических пластин
- naming rule: не назначать точное изделие/операцию без подтверждения

## A-004 — Двухсторонний точильно-шлифовальный станок / bench grinder
- confidence: `CONFIRMED`
- 3D fidelity: high
- function: заточка/доводка
- replace: no

## A-005 — Торцовочная/усовочная пила
- confidence: `CONFIRMED`
- 3D fidelity: high
- function: точный поперечный/угловой распил деревянных деталей
- replace: no

## A-006 — Большие слесарные тиски
- confidence: `CONFIRMED`
- function: фиксация/подгонка/доводка
- fidelity: high

## A-007 — Малые машинные зажимные приспособления / машинные тиски
- confidence: `CONFIRMED`
- function: точная фиксация заготовок
- fidelity: high

## A-008 — CAS-весы
- confidence: `CONFIRMED brand family / exact model unresolved`
- likely function: взвешивание; возможно комплектование/фасовка/счёт деталей
- exact workflow: `UNRESOLVED`
- fidelity: medium-high
- note: не придумывать точный номер модели без читаемой шильды

---

# Переносной электроинструмент

## E-001 — Сетевые электродрели
- confidence: `CONFIRMED`
- fidelity: medium-high

## E-002 — Аккумуляторная дрель/шуруповёрт
- confidence: `CONFIRMED`
- fidelity: medium-high

## E-003 — Удлинители, кабели, кабельные бухты
- confidence: `CONFIRMED`
- preserve function: yes
- preserve chaotic execution: no
- transform: новая безопасная электрика и cable management

---

# Ручной инструмент

- `HND-001` — ножовки и ручные пилы — `CONFIRMED`, wall authenticity anchor.
- `HND-002` — рожковые/накидные ключи — `CONFIRMED`.
- `HND-003` — плоскогубцы/пассатижи — `CONFIRMED`.
- `HND-004` — молотки — `CONFIRMED`.
- `HND-005` — отвёртки, включая прецизионные/индикаторные семейства — `CONFIRMED family`.
- `HND-006` — напильники — `CONFIRMED`.
- `HND-007` — струбцины — `CONFIRMED`.
- `HND-008` — штангенциркуль / точный измерительный инструмент — `CONFIRMED family`.
- `HND-009` — угольники, длинные металлические линейки/уровни — `CONFIRMED`.
- `HND-010` — шилья/тонкий разметочный инструмент — `CONFIRMED family`.
- `HND-011` — шестигранные ключи — `CONFIRMED family`.

---

# Фурнитура и крепёж

- `F-001` — гайки M8 — `CONFIRMED family`.
- `F-002` — мебельные/машинные болты — `CONFIRMED family`.
- `F-003` — болты с шестигранной головкой — `CONFIRMED family`.
- `F-004` — крепёж с широкой округлой головкой — `CONFIRMED family`.
- `F-005` — шайбы — `CONFIRMED family`.
- `F-006` — саморезы — `CONFIRMED family`, крупные партии.
- `F-007` — резьбовые шпильки и стержни — `CONFIRMED family`.
- `F-008` — двухрезьбовые hanger bolts — `LIKELY / strong identification`; exact use in this workshop: `VERIFY`.
- `F-009` — four-pronged T-nuts / забивные T-гайки — `LIKELY`; не заявлять exact SKU.
- `F-010` — квадратные монтажные пластины с 4 отверстиями и центральным резьбовым элементом — `CONFIRMED geometry`; likely узлы крепления/опор мебели; exact product `UNRESOLVED`.
- `F-011` — небольшие карточные/стыковые петли — `CONFIRMED`.
- `F-012` — более крупные петли — `CONFIRMED family`.
- `F-013` — шарнирные механизмы — `CONFIRMED geometry / function varies`.
- `F-014` — металлические уголки — `CONFIRMED`.
- `F-015` — кронштейны — `CONFIRMED`.
- `F-016` — соединительные пластины — `CONFIRMED`.
- `F-017` — перфорированные элементы/профили — `CONFIRMED`.
- `F-018` — мебельные/тележечные колёса на кронштейнах — `CONFIRMED`.
- `F-019` — проволока/трос — `CONFIRMED family`.
- `F-020` — партии мелкого крепежа разных типоразмеров — `CONFIRMED`; часть запасов должна оставаться визуально видимой.

---

# Материалы

- `M-001` — фанера — `CONFIRMED family`.
- `M-002` — MDF / другие плитные мебельные материалы — `LIKELY/CONFIRMED family`.
- `M-003` — одинаково нарезанные листовые заготовки — `CONFIRMED`.
- `M-004` — длинномерные деревянные элементы — `CONFIRMED`.
- `M-005` — мебельные/декоративные панели — `CONFIRMED family`.
- `M-006` — панели с древесным/каменным рисунком — `CONFIRMED family`.
- `M-007` — тёмные профили и рамные элементы — `CONFIRMED family`.

**New workshop rule:** отдельный вертикальный material rack; не складывать материалы «для красивой композиции».

---

# Хранение

## S-001 — Реальные коробки/ведра/лотки с партиями
- preserve function: yes
- preserve damaged container: no
- transformation: маркированные деревянные/металлические shallow drawers, прозрачные фронтальные bins, модульные секции

## S-002 — Рукописная маркировка партий
- confidence: `CONFIRMED`
- preserve logic: yes
- transformation: аккуратные этикетки/карточки; часть рукописного характера можно сохранить

## S-003 — Полки/стеллажи
- preserve zoning: yes
- transformation: прочные светлые профессиональные systems

---

# Сделано мастером

## MM-001 — Серое кресло с болтовыми соединениями и сиденьем из чёрных лент
- confidence: `USER-CONFIRMED MADE BY MASTER`
- priority: high
- instruction: отдельный asset; не превращать в luxury designer chair

## MM-002 — Стол
- confidence: `USER-CONFIRMED MADE BY MASTER`

## MM-003 — Чёрная уличная скамейка
- confidence: `USER-CONFIRMED MADE BY MASTER`
- note: пользователь отдельно упомянула, что она хорошо стоит под дождём

---

# Пространство

## SP-001 — ROOM 1 / большая входная комната
- confidence: `USER-CONFIRMED`
- character: большой объём, сравнительно мало станков/работы
- opportunity: светлая входная/приёмная/демонстрационная зона без превращения в шоурум

## SP-002 — ROOM 2 / основная рабочая
- confidence: `USER-CONFIRMED`
- character: ядро станков, верстака, фурнитуры, ручной обработки

## SP-003 — ROOM 3 / небольшая складско-бытовая
- confidence: `USER-CONFIRMED`
- character: склад + розовый диван / личный бытовой слой
- transformation: организованное хранение + спокойный угол отдыха/книг

## SP-004 — Наружный сад/участок
- confidence: `CONFIRMED`
- transformation: большие окна могут делать сад частью интерьера

---

# Infrastructure — разрешено добавить, но маркировать как NEW

- `N-001` — пылеудаление / dust extraction — `WEB RECOMMENDATION / NEW INFRASTRUCTURE`.
- `N-002` — безопасная электрика и cable management — `NEW INFRASTRUCTURE`.
- `N-003` — качественный task lighting + общий мягкий свет — `NEW INFRASTRUCTURE`.
- `N-004` — модульное маркированное хранение — `NEW INFRASTRUCTURE`.
- `N-005` — вертикальный rack для листовых/длинномерных материалов — `NEW INFRASTRUCTURE`.

---

# Final rule for every asset

> **Моделировать точно. Называть осторожно.**

Нельзя:
- заменять реальные станки типовыми красивыми аналогами;
- добавлять CNC, большой table saw, jointer, planer и т.п. без evidence;
- приписывать функции по отраслевому контексту, если они не подтверждены;
- прятать весь запас фурнитуры за дизайнерскими фасадами.

Можно:
- очистить;
- убрать грязь/ржавчину;
- восстановить окраску;
- улучшить читаемость;
- сделать хранение профессиональнее;
- добавить безопасную инфраструктуру.
