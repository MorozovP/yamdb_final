### Общее описание

Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles).
Произведения делятся на категории: «Книги», «Фильмы», «Музыка». 

Произведению может быть присвоен жанр (Genre) из списка предустановленных (
например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только
администратор.

Пользователи оставляют к произведениям текстовые отзывы (Review) и ставят 
произведению оценку в диапазоне от одного до десяти (целое число); из 
пользовательских оценок формируется усреднённая оценка произведения — рейтинг
(целое число). 

### Технологии

Проект Yamdb реализован на Django и Django REST API Framework. Используемая
база данных - Postgres, сервер - Nginx. Настроено развертывание проекта в трех
Docker - контейнерах: yamdb, db, nginx.

### Установка
Клонируйте репозиторий
```
git clone git@github.com:MorozovP/infra_sp2.git
```
Заполните файл с переменными окружения по шаблону: infra/.env.example 

Для запуска приложения в контейнерах перейдите в папку infra и выполните 
следующие команды:

```
docker-compose up -d --build
```
Выполните миграции:

```
docker-compose exec yamdb python manage.py migrate
```
Создайте администратора:

```
docker-compose exec yamdb python manage.py createsuperuser
```
Для корректного отображения страниц выполните:

```
docker-compose exec yamdb python manage.py collectstatic --no-input
```

![workflow bagde](https://github.com/MorozovP/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

### Об авторе
Выполнил Морозов Павел 
https://github.com/MorozovP
