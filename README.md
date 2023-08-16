## Цель проекта

Собрать статистику по репозиториям заданного пользователя на GitHub и сохранить ее в базу данных Postgres.

## Описание проекта

Проект состоит из трех основных компонентов:
<b>main.py</b>, <b>functions.py</b> и <b>postgres_db.py</b> 

<b>functions.py</b> содержит функцию get_repos_stats(), которая собирает статистику по репозиториям заданного пользователя на GitHub. 
Эта функция использует библиотеку requests, чтобы обращаться к API GitHub и получать информации о репозиториях пользователя. Затем функция обрабатывает полученные данные и возвращает список словарей, содержащих статистику по каждому репозиторию.

<b>postgres_db.py</b> содержит класс PostgresDB, который обеспечивает взаимодействие с базой данных Postgres. Класс реализует методы, чтобы создать таблицу, добавить данные в таблицу, экспортировать данные в формат JSON и получить данные из таблицы.

<b>main.py</b> является точкой входа в проект. Его основная функция main() вызывает функцию get_repos_stats(), чтобы собрать статистику по репозиториям пользователя, и затем использует класс PostgresDB для сохранения данных в базу данных. В конце функция вызывает другой метод класса PostgresDB, чтобы экспортировать данные в формате JSON.

### Для корректной работы потребуется: 

- Установить зависимости через ```pip install -r requirements.txt```

- Создать файл конфигурации в корне проекта database.ini

### Шаблон файла с конфигурацией:
```
[postgresql]
host=localhost
user=ваше_имя_пользователя
password=ваш_пароль
port=5432
```
