.. _v_ProcedureCPV2:

v_ProcedureCPV2
===============

Змінна містить собі CPV2 код процедури.

**Формат:**  Рядок.

**Рівень розрахунку:** Процедура закупівлі

**Частота розрахунку:** Змінна розраховується один раз 

Дані, що використовуються для розрахунку
----------------------------------------

Для розрахунку використовуються:

* - :ref:`v_ProcedureCPV`
* - таблиця cpv_catalogue

Формула розрахунку
------------------

1. З таблиці cpv_catalogue CPV2 для :ref:`v_ProcedureCPV` процедури.
