# Проект api_final_yatube


# Описание
В проекте реализован API который представляет собой проект включающий следующие возможности:
- публиковать записи
- комментировать записи
- подписываться 
- отписываться от авторов
# Технологии
- Django restful framework(DRF)
- Django, django ORM
- Djoser + JWT


### Как запустить проект api_final_yatube:

  

Клонировать репозиторий и перейти в него в командной строке:

  

```
git clone git@github.com:VadimTT-byte/api_final_yatube.git
```

  

```
cd api_final_yatube
```

  

Создать и активировать виртуальное окружение:

  

```
python -m venv venv
```

  

```
source venv/Scripts/activate
```

  

Установить зависимости из файла requirements.txt:

  

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```
Выполнить миграции:
```
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```

# Примеры запросов
### JWT+djoser sample requests
| Method| Endpoint| Description|
|-----| ------ | ------ |
|POST| /auth/users/| Базовый: зарегистрировать нового пользователя |
|POST| /auth/users/me| Базовый: получить/обновить зарег. пользователя |
|POST| /auth/jwt/create | Создать JWT-токен |
|POST| /auth/jwt/refresh| Получить новый JWT по истечении времени жизни токена |
Documentation [JWT+djoser](https://djoser.readthedocs.io/en/latest/index.html)
#### For anonymous users

  |Method| Endpoint| Description| 
| ------ | ------ | ------ |
| GET| /api/v1/posts/ | Получить список всех публикаций
|	GET |	 /api/v1/posts/{id}| Получение публикации по id
| GET| api/v1/groups/ | Получение списка доступных сообществ
| GET | api/v1/groups/{id}/ | Получение информации о сообществе по id
| GET | api/v1/{post_id}/comments/ | Получение всех комментариев к публикации
| GET | api/v1/{post_id}/comments/{id}/ | Получение комментария к публикации по id

Samples
````
GET /api/v1/posts/?limit=10&offset=0
````
_При указании параметров limit и offset выдача должна работать с пагинацией_
_limit_ - кол-во публикаций на страницу
_offset_ - номер страницы после которой начинать выдачу

#### For authorizes users
  |Method| Endpoint|  Description| 
| ------ | ------ | ------ |
| POST| /api/v1/posts/ | Создание публикации
|PUT|/api/v1/posts/{id}| Обновление публикации
| PATCH| /api/v1/posts/{id}/ | Частичное обновление публикации
| DEL| /api/v1/posts/{id}/ | Удаление публикации
| POST| /api/v1/posts/{post_id}/comments/ | Добавление комментариев к публикации
| PUT| api/v1/{post_id}/comments/{id}/ | Обновление комментария
| PATCH | /api/v1/posts/{post_id}/comments/ | Частичное обновление комментария
| DEL| api/v1/{post_id}/comments/{id}/ | Удаление комментариев
| POST| /api/v1/follow/ |Подписка на пользователя* |
_*Подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса. Анонимные запросы запрещены._
### Примеры запросов + Документация:
[Документация для API Yatube в формате Redoc](http://127.0.0.1:8000/redoc/)

_*запускать после старта сервера_
### Автор
[Vadim Trusov](https://github.com/VadimTT-byte)
