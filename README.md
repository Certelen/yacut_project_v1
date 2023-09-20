# ЯП - Спринт 21 - Cервис YaCut.

## Описание
Сервис YaCut обрезает ссылки и выдаёт короткую ссылку, либо пользовательский вариант короткой ссылки не более 16 символов, с помощью которой можно перейти на изначальную ссылку.

## Технологии
- Python 3.9
- Flask 2.0.2

## Документация
# Установка
После клонирования репозитория требуется развернуть и активировать виртуальное окружение:
```
~ py -3.9 -m venv venv
~ . venv/Scripts/activate
```
Установить требуемые зависимости:
```
~ pip install -r requirements.txt
```
При необходимости можно создать файл .env и изменить стандартный настройки.

# Запуск
Запуск сервиса производится командой:
```
~ flask run
```
Доступ к сервису становится доступен по адресу http://127.0.0.1:5000/

## Примеры запросов
- ```api/id``` - POST-запрос возвращающий исходную длинную ссылку и её укороченный вариант:
```
{
    "url": "<Длинная ссылка>",
    "custom_id": "<Пользовательский вариант короткой ссылке, необязательно>"
} 
```
- ```api/id/<custom_id>/``` - GET-запрос возвращающий длинную ссылку, если данный короткий вариант существует.
- ```http://127.0.0.1:5000/``` - Основной сайт сервиса, содержащий форму с полями для заполнения.
- ```http://127.0.0.1:5000/<custom_id>``` - Если данный короткий вариант существует, будет произведена переадресация на соответствующую длинную ссылку.

## Автор

- :white_check_mark: [Коломейцев Дмитрий(Certelen)](https://github.com/Certelen)

Проект сделан в рамках учебного процесса по специализации Python-разработчик (back-end) Яндекс.Практикум.