# Init #
---
## 1. Создание таблицы  ##
---
```sqlite
CREATE TABLE [TABLE-NAME]
```

>[!Note] Sample
```sqlite
CREATE TABLE [TABLE-NAME] (
   [col1] [DATE-TYPE] [ATTR]
   [col2] [DATE-TYPE] [ATTR]
   ...
   [colN] [DATE-TYPE] [ATTR]
);
```

>[!Example]
```sqlite
CREATE TABLE EXAMPLE (
	Id INTEGER,
	Name TEXT,
	Age INTEGER
);
```

### 1.1 Создание таблицы если она уже существует ###
---
```sqlite
CREATE TABLE IF NOT EXISTS [TABLE-NAME]
```
- IF NOT EXISTS - Проверяет существует такая таблица или нет

## 2. Удаление таблицы  ##
---
```sqlite
DROP TABLE IF EXISTS [TABLE-NAME]
```

## Прикрепление **DB** ##
---

```sqlite
ATTACH DATEBASE 'putch/to/file' AS [alias];
```

# Data types #
---

| type     | description                                      |
| -------- | ------------------------------------------------ |
| null     | указывает на отсутствие значения                 |
| integer  | целое значение (положительное или отрицательное) |
| real     | число с плавающей точкой                         |
| text     | строка                                           |
| blob     | бинарные данные                                  |
| NUMERIC  | все 5 типов (любой) ((анал. affinity))           |


# Ограничения #
---
#### PRIMARY KEY ####
---
```sqlite
id INTEGER PRIMARY KEY
```
- Данное поле будет выступать в качестве первичного ключа

>[!Warning] Установка первичного ключа на уровне таблицы
```sqlite
CREATE TABLE users (
    id INTEGER,
    name TEXT,
    age INTEGER,
    email TEXT,
    PRIMARY KEY(id)
);
```

>[!Warning] Установка составного первичного ключа
```sqlite
CREATE TABLE users (
    id INTEGER,
    name TEXT,
    age INTEGER,
    email TEXT,
    PRIMARY KEY(id, name)
);
```
- Составной первичный ключ

#### AUTOINCREMENT ####
---
```sqlite
id INTEGER PRIMARY KEY AUTOINCREMENT
```
- Автоматически увеличивает данное число на 1

#### UNIQUE ####
---
```sqlite
email TEXT UNIQUE
```
- Данные строки должны быть уникальными

>[!Warning] Определение ограничения на уровне таблицы
```sqlite
CREATE TABLE users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    age INTEGER,
    email TEXT,
    UNIQUE (name, email)
);
```
- В данном случае устанавливается ограничение сразу для двух столбцов

#### DEFAULT ####
---
```sqlite
age INTEGER DEFAULT 18
```
- Выставляет значение по умолчанию


#### NOT / NOT NULL ####
---
```sqlite
name TEXT NOT NULL,
```
- Столбец name не допускает значение NULL

>[!info] По умолчанию любой столбец, если он не представляет первичный ключ,может принимать значение NULL.

#### CHECK ####
---
- Создает ограничение для диапазона значений
```sqlite
name TEXT NOT NULL CHECK(name != '')
age INTEGER NOT NULL CHECK(age >0 AND age < 100)
```

>[!Warning] Использование CHECK на уровне таблицы
```sqlite
CREATE TABLE users
(
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER NOT NULL,
    CHECK ((age >0 AND age < 100) AND (name !=''))
);
```

#### CONSTRAINT ####
---
- С помощью данного оператора можно задавать имена ограничениям.
    - Для последующего управления ими.

>[!Example]
```sqlite
CREATE TABLE users
(
    id INTEGER,
    name TEXT NOT NULL,
    email TEXT NOT NULL,
    age INTEGER NOT NULL,
    CONSTRAINT users_pk PRIMARY KEY(id),
    CONSTRAINT user_email_uq UNIQUE(email),
    CONSTRAINT user_age_chk CHECK(age >0 AND age < 100)
);
```
