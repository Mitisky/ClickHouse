<a name="table_engines-mysql"></a>

# MySQL

Движок MySQL позволяет выполнять `SELECT` запросы над данными, хранящимися на удалённом MySQL сервере.

Формат вызова:

```
MySQL('host:port', 'database', 'table', 'user', 'password');
```

На данный момент простые условия `WHERE`, такие как `=, !=, >, >=, <, <=` будут выполняться на стороне сервера MySQL.

Остальные условия и ограничение выборки `LIMIT` будут выполнены в ClickHouse только после выполнения запроса к MySQL.

Движок `MySQL` не поддерживает тип данных [Nullable](../../data_types/nullable.md#data_type-nullable), поэтому при чтении данных из таблиц MySQL `NULL` преобразуются в значения по умолчанию для заданного типа столбца, обычно это `0` или пустая строка.
