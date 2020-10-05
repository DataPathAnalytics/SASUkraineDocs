################################################
Загальна кількість замовників за останній місяць
################################################

**Тип елемента:**
    Кількість(ключовий показник ефективності)
    
Частота розрахунку:
-------------------
Показник розраховується кожного разу при перерахунку усіх показників

Дані для розрахунку:
--------------------
- API тендерінгу системи публічних закупівель
- змінна :ref:`v_DateCreated`
- змінна :ref:`v_LastMonth`

Поля розрахунку:
----------------
- ``data.date``
- ``data.status``
- ``data.procuringEntity.identifier.scheme``
- ``data.procuringEntity.identifier.id``

Формула розрахунку:
-------------------
1. Вибираємо ідентифікатори замовників (конкатенація ``data.procuringEntity.identifier.scheme`` та ``data.procuringEntity.identifier.id``) усіх процедур, що мають у ``data.status`` слово ``active`` та :ref:`v_DateCreated` у яких менше або дорівнює ``v_LastMonthRightMargin``.
2. Вибираємо ідентифікатори замовників (конкатенація ``data.procuringEntity.identifier.scheme`` та ``data.procuringEntity.identifier.id``) усіх процедур, що мають:
2.1. ``data.status`` дорівнює ``complete``, ``cancelled``, ``unsuccessful``.
2.2. :ref:`v_DateCreated` у яких менше або дорівнює ``v_LastMonthRightMargin`` та ``data.date`` яких більше або дорівнює ``v_LastMonthLeftMargin``.
3. Рахуємо кількість унікальних ідентифікатори замовників, знайдених у п.1 та п.2.
