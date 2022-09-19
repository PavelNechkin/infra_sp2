# YAMDB
YAMDB

### Описание:

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий со временем может быть расширен.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения: книги, фильмы или музыка. Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Насекомые» и вторая сюита Баха.
Произведению может быть присвоен жанр из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры могут быть созданы по жеданию пользователей, но создавать их могут только администраторы.
Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти; из пользовательских оценок формируется усреднённая оценка произведения — рейтинг. На одно произведение пользователь может оставить только один отзыв

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone ...
```

В корневой директории клонированного репозитория создать файл .env. Файл должен нужно оформить в соответствии с примером:
DB_NAME=...
POSTGRES_USER=...
POSTGRES_PASSWORD=...
DB_HOST=...
DB_PORT=...
SECRET_KEY='секретный_ключь_50_символов'
DEBUG=False/True
ALLOWED_HOSTS='...'


Запустить docker-compose, выполнив команду из корневой директоии:

```
docker-compose up -d
```


Выполнить миграции:

```
docker-compose exec web python manage.py makemigrations --noinput
docker-compose exec web python manage.py migrate --noinput
```


Загрузить статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

### Авторы проекта:

```
Рафаэль Асланян - Auth/Users
Нечкин Павел - Categories/Genres/Titles
Алан Рысов - Review/Comments
Алексей Кашлинов - Ревью проекта
Андрей Горлов - Наставник группы
```

### Стек используемых технологий:

```
Django
DRF
Docker
```
