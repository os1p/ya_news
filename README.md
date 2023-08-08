Для загрузки заготовленных новостей после применения миграций выполните команду:
```bash
python manage.py loaddata news.json
```
Добро пожаловать в проект! Знакомьтесь:
На главной странице проекта отображаются 10 последних новостей. Главная страница доступна любому пользователю. Новости отображаются в сокращённом виде (видно только первые 15 слов).
У каждой новости есть своя страница, с полным текстом новости; там же отображаются и комментарии пользователей.
Любой пользователь может самостоятельно зарегистрироваться на сайте.
Залогиненный (авторизованный) пользователь может оставлять комментарии, редактировать и удалять свои комментарии.
Если к новости есть комментарии — их количество отображается на главной странице под новостью.
В коде проекта есть список запрещённых слов, которые нельзя использовать в комментариях, например, «редиска» и «негодяй».


Разверните на своём компьютере проект YaNews:
На своём компьютере в директории с проектами создайте папку для проекта YaNews.
Склонируйте проект YaNews из репозитория: 
```bash
git clone …
```
Создайте виртуальное окружение  
```bash 
python -m venv venv
```
Запустите виртуальное окружение и установите зависимости из файла
```bash 
requirements.txt: pip install -r requirements.txt
```
Миграции уже созданы, выполните их: 
```bash 
python manage.py migrate.
```
Cоздайте суперпользователя: 
```bash 
python manage.py createsuperuser.
```
Для заполнения базы данных новостями, выполните команду 
```bash 
python manage.py loaddata news.json.
```
Запустите проект.
