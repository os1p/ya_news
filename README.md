**Для загрузки заготовленных новостей после применения миграций выполните команду:**
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


**Разверните на своём компьютере проект YaNews:**
На своём компьютере в директории с проектами создайте папку для проекта YaNews.
Склонируйте проект YaNews из репозитория: 
```bash
git clone …
```
**Создайте виртуальное окружение**
```bash 
python -m venv venv
```
**Запустите виртуальное окружение и установите зависимости из файла**
```bash 
requirements.txt: pip install -r requirements.txt
```
**Миграции уже созданы, выполните их:**
```bash 
python manage.py migrate.
```
**Cоздайте суперпользователя:** 
```bash 
python manage.py createsuperuser.
```
**Для заполнения базы данных новостями, выполните команду**
```bash 
python manage.py loaddata news.json.
```
Запустите проект.


**Будем тестировать:**

**В файле test_routes.py:**
```bash 
- [ ]Главная страница доступна анонимному пользователю.
- [ ]Страница отдельной новости доступна анонимному пользователю.
- [ ]Страницы удаления и редактирования комментария доступны автору комментария.
- [ ]При попытке перейти на страницу редактирования или удаления комментария анонимный пользователь перенаправляется на страницу авторизации.
- [ ]Авторизованный пользователь не может зайти на страницы редактирования или удаления чужих комментариев (возвращается ошибка 404).
- [ ]Страницы регистрации пользователей, входа в учётную запись и выхода из неё доступны анонимным пользователям.
```
**В файле test_content.py:**
```bash 
+ Количество новостей на главной странице — не более 10.
+ Новости отсортированы от самой свежей к самой старой. Свежие новости в начале списка.
+ Комментарии на странице отдельной новости отсортированы от старых к новым: старые в начале списка, новые — в конце.
+ Анонимному пользователю недоступна форма для отправки комментария на странице отдельной новости, а авторизованному доступна.
```
**В файле test_logic.py:**
```bash 
+ Анонимный пользователь не может отправить комментарий.
+ Авторизованный пользователь может отправить комментарий.
+ Если комментарий содержит запрещённые слова, он не будет опубликован, а форма вернёт ошибку.
+ Авторизованный пользователь может редактировать или удалять свои комментарии.
+ Авторизованный пользователь не может редактировать или удалять чужие комментарии.
```
**Не будем тестировать:**
```bash 
+ Непосредственно регистрацию пользователей, процесс входа в учетную запись и выхода из неё.
+ Всё, что связано с админ-зоной проекта.
+ Абсолютные url-адреса; обращаться к адресам будем при помощи функции reverse('name').
+ Какие шаблоны используются, и насколько корректно шаблон обрабатывает полученную от Django информацию. Например, если в шаблон передается список объектов, мы будем считать, что они выводятся все, а их сортировка не меняется.
+ Всё то, что не попало в список «будем тестировать».
```
