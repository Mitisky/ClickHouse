# numbers

`numbers(N)` - возвращает таблицу с единственным столбцом number (тип UInt64), содержащим натуральные числа от 0 до N-1.

Так же как и таблица `system.numbers` может использоваться для тестов и генерации последовательных значений.

Следующие 2 запроса эквивалентны:
```sql
SELECT * FROM numbers(10);
SELECT * FROM system.numbers LIMIT 10;
```
Примеры:
```sql
-- генерация последовательности всех дат от 2010-01-01 до 2010-12-31
select toDate('2010-01-01') + number as d FROM numbers(365);
```
