# Создание и управление таблицами #
---
```python
import sqlite3
```

```python
connection = sqlite3.connect('my_databse.db')
```
- Устанавливаем соединение с бд
    * В контексте работы с *db* в *Python*, когда устанавливается соединение с *db* - создается объект соединения.

```python
cursor = connection.cursor()
```
- Создает объект **cursor** для выполнения *SQL*-запросов и операций с *db*.
- *Cursor* - Это механизм, который позволяет отправлять *SQL*-запросы *db* и получать результаты запросов.
> [!TIP] *Представляет соединение в качестве объекта.*

```python
cursor.execute('''
CREATE TABLE IF NOT EXISTS Users (
id INTEGER PRIMARY KEY,
username TEXT NOT NULL,
email TEXT NOT NULL,
age INTEGER
)
''')
```
- Создаем таблиу Users

```python
connection.commit()
connectiom.close()
```
- Сохраняем изменения и закрываем таблицу
