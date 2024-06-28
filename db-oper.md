# CREATE #
---
>[!Note] Sample
```sqlite
CREATE TABLE IF NOT EXISTS <table-name> (
id INTEGER PRIMARY KEY,
username TEXT NOT NULL,
email TEXT NOT NULL,
age INTEGER
)
```

# INSERT #
---
>[!Note] Sample
```sqlite
INSERT INTO <table-name> (col1, col2, ..., colN)>
VALUES (val1, val2, ..., valN);
```
- Добавление данных в бд
>[!Info] При добавлении данных необязательно указывать значения для всех столбцов!
> - Можно опускать при добавлении такие столбцы, которые поддерживают **NULL** / **default**
> - Можно явным образом для них указывать **NULL** 

## Множественное добавление ##
---
>[!Example]
```
INSERT INTO users(name, age) VALUES
('Tom', 16),
('Bob', 24),
('Sam', 35)
```


# SELECT #
---

```sqlite
select * from [table-name];
```
- Получить все данные

https://metanit.com/sql/sqlite/3.2.php
