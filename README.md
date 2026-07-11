# Домашнее задание к занятию «Работа с данными (DDL/DML)»
### Задание 1

## 1.3
<img width="1456" height="773" alt="image" src="https://github.com/user-attachments/assets/6f345414-e654-46af-bc2c-3d994ab77613" />

## 1.5
<img width="1460" height="786" alt="image" src="https://github.com/user-attachments/assets/7ec64d40-d1cd-4314-9c09-f4493722ae9a" />

## 1.8
<img width="1344" height="1086" alt="image" src="https://github.com/user-attachments/assets/4555bfb8-cce3-4a0d-aa7a-af55068bb4b3" />
<img width="1247" height="737" alt="image" src="https://github.com/user-attachments/assets/13a82b2a-a6c7-47a5-b0a7-07c85e778ec7" />


### Задание 2
<img width="953" height="839" alt="image" src="https://github.com/user-attachments/assets/0887b5ff-e10e-4e41-9795-2e9e68aca492" />
<img width="627" height="793" alt="image" src="https://github.com/user-attachments/assets/3c822d79-e4c5-4646-8d51-f12cd836bfbc" />

### все запросы
-- ===========================================
-- Задание 1.2. Создание пользователя sys_temp
-- ===========================================
CREATE USER 'sys_temp'@'%' IDENTIFIED WITH mysql_native_password BY 'TempPass123!';

-- ===========================================
-- Задание 1.3. Список пользователей (скриншот)
-- ===========================================
SELECT User, Host FROM mysql.user;

-- ===========================================
-- Задание 1.4. Выдача всех прав
-- ===========================================
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;

-- ===========================================
-- Задание 1.5. Список прав для sys_temp (скриншот)
-- ===========================================
SHOW GRANTS FOR 'sys_temp'@'%';

-- ===========================================
-- Задание 1.6. Смена типа аутентификации
-- ===========================================
ALTER USER 'sys_temp'@'%' IDENTIFIED WITH mysql_native_password BY 'TempPass123!';
FLUSH PRIVILEGES;

-- ===========================================
-- Задание 1.8. Список таблиц Sakila (скриншот)
-- ===========================================
USE sakila;
SHOW TABLES;

-- ===========================================
-- Задание 2. Первичные ключи таблиц Sakila (скриншот)
-- ===========================================
USE sakila;
SELECT 
    TABLE_NAME,
    COLUMN_NAME
FROM
    information_schema.key_column_usage
WHERE
    CONSTRAINT_SCHEMA = 'sakila'
    AND CONSTRAINT_NAME = 'PRIMARY'
ORDER BY TABLE_NAME;
