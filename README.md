# Проект «API для Yatube»
Проект Yatube — это платформа для публикаций, блог. У пользователей есть возможность публиковать, редактировать, удалять записи, оставлять комментарии, подписываться на авторов. «API для Yatube» расширяет функционал проекта.

## Описание функционала:

* Возможность получать, создавать, обновлять, удалять публикации, а также комментарии к ним.
* Возможность просмотратривать сообщества и информацию о сообществах.
* Возможность подписываться на авторов.
* Возможность получать, проверять, обновлять JWT-токен.

### Как запустить проект на локальной машине:
###### Клонировать репозиторий и перейти в него в командной строке:
`git clone https://github.com/Igor-L12/api_final_yatube.git`
`cd api_final_yatube`
###### Создать и активировать виртуальное окружение:
`python -m venv venv`
`source venv/Scripts/activate`
###### Установить зависимости из файла requirements.txt:
`pip install -r requirements.txt`
###### Выполнить миграции:
`python manage.py migrate`
###### Запустить проект:
`python manage.py runserver`
###### Когда вы запустите проект, по адресу `http://127.0.0.1:8000/redoc/` будет доступна документация для API Yatube.

### Примеры запросов:
Пример POST-запроса с токеном: добавление поста

*POST .../api/v1/posts/*
```
{
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "group": 1
}
```
Пример GET-ответа:
```
{
    "id": 14,
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "author": "anton",
    "image": null,
    "group": 1,
    "pub_date": "2021-06-01T08:47:11.084589Z"
}
```

Пример POST-запроса с токеном: отправляем комментарий с `id=3`

*POST .../api/v1/posts/3/comments/*
```
{
    "text": "тест тест"
}
```
Пример GET-ответа:
```
{
    "id": 4,
    "author": "anton",
    "post": 3,
    "text": "тест тест",
    "created": "2021-06-01T10:14:51.388932Z"
} 
```
Автор: [Игорь Любаев](https://github.com/Igor-L12)
