# English

For `Django >= 2.0` compatible with `Python >= 3.5`

## Structure

Recommend installation virtualenv in `env` folder in project folder.

```
/.git
/env         - virtualenv
/applications - folder for django applications
---/main      - start app point that I offer for you
/requirements - requirements for current project
/settings     - django settings
```

## Install

```
git clone https://github.com/o5b/telegram-freelance.git
cd telegram-freelance/
python3.12 -m venv env
source .env/bin/activate
pip install -r requirements/base.txt
```

## Usage

### Server

```
python manage.py runserver
```

### Database

PostgreSQL is used as a database. Site search is based on PostgreSQL functionality.

#### Database migrations and superuser creation

```
python manage.py migrate
python manage.py createsuperuser
```

### Django-modeltranslation

#### Synchronizing Model Fields

```
python manage.py sync_translation_fields
```

#### If you need to transfer the data that was originally in the model to the fields created by django-modeltranslation

```
python manage.py update_translation_fields
```

### Add test data to the database

```
python manage.py loaddata fixtures/db.json
```

#### If you need to save data from the database to fixtures

```
python manage.py dumpdata capture main services --indent 2 > fixtures/db.json
```

![demo](docs/video/demo_2024-05-08.gif)

# Russian

Этот проект: https://github.com/o5b/telegram-freelance

Для `Django >= 2.0` совместно с `Python >= 3.5`

## Структура

Рекомендуется устанавливать virtualenv в папку `env` в папку проекта.

```
/.git
/env          - папка для установки виртуального окружения
/applications - папка django applications
---/main      - основное приложение
/requirements - зависимости для текущего проекта
/settings     - настройки django
```

## Установка

```
git clone https://github.com/o5b/telegram-freelance.git
cd telegram-freelance/
python3.12 -m venv env
source .env/bin/activate
pip install -r requirements/base.txt
```

## Использование

### Сервер (в консоли терминала)

```
python manage.py runserver
```

### База данных
В качестве базы данных используется PostgreSQL. Поиск по сайту основан на функционале PostgreSQL.

#### Миграции для базы данных и создание суперпользователя

```
python manage.py migrate
python manage.py createsuperuser
```

### Локализация на другие языки

#### Если Django, то собрать для перевода в файл django.po

```
django-admin makemessages -a
```

#### Делаем переводи и затем компилируем в файл django.mo

```
django-admin compilemessages
```

#### Если использовать Rosetta то строки для перевода можно найти по адресу

```
http://127.0.0.1:8000/admin/rosetta/
```

### Django-modeltranslation

#### Синхронизируем поля модели

```
python manage.py sync_translation_fields
```

#### Если нужно перенести данные, которые были в модели изначально, в поля созданные django-modeltranslation

```
python manage.py update_translation_fields
```

### Наполнить бд тестывыми данными

```
python manage.py loaddata fixtures/db.json
```

#### Если нужно сохранить данные из бд в fixtures

```
python manage.py dumpdata capture main services --indent 2 > fixtures/db.json
```
