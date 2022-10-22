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
### Примеры запросов:
http://127.0.0.1:8000/redoc/
