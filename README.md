![Workflow status badge](https://github.com/berg96/kittygram_final/actions/workflows/main.yml/badge.svg)
# Проект Kittygram 

## Описание проекта 

Проект Kittygram позволяет зарегистрированным пользователям выкладывать своих котов, кошек и котенков.
[Kittygram](https://zelek-kittygram.ddns.net)

Доступ к контенту сайта ограничен: смотреть информацию о котиках и управлять карточками собственных котиков могут только авторизованные пользователи. Поэтому главная страница сайта сразу же предлагает посетителям ввести логин и пароль.
Аутентифицированным пользователям проект позволяет добавлять новых питомцев на сайт. Для каждого нового котика нужно обязательно указать его имя, год рождения и выбрать цвет. Опционально можно загрузить фотографию своего питомца, для котиков без фотографии будет выводиться изображение по умолчанию. Кроме этого, для каждого котика можно указать его достижения — одно или сразу несколько. Их можно выбрать из уже доступных или добавить новые.
На главной странице сайта будут выведены все загруженные котики в БД. Кроме того, SPA должно владеть информацией об id текущего пользователя, от этого зависит к какому котику нужно будет добавить интерфейс обновления/удаления информации, а к какому нет — только хозяева могут обновлять или удалять информацию о своих питомцах.

### Автор проекта Артём Куликов

tg: [@Berg1005](https://t.me/berg1005)

[GitHub](https://github.com/berg96)

## Используемые технологии 

Проек реализован на языке python c использованием следующих библиотек:

* Django (v 3.2.16) 
* djangorestframework(v 3.12.4) 
* djoser (v 2.1.0) 
* gunicorn (v 20.1.0)

и др. 

## Как запустить проект

Клонировать репозиторий:
```
git clone git@github.com:berg96/kittygram_final.git
```
Запустить Docker compose:
```
docker compose -f docker-compose.production.yml up -d
```
Собрать миграции и собрать статику:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```
