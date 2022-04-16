# tmdb_api
Упражнение на чтение кода. Фильмы с TMDB

Код представляет собой набор скриптов, предназначенных для взаимодействия с API сайта [https://www.themoviedb.org/](https://www.themoviedb.org/) - одной из крупнейших информационных баз фильмов.

Для первоначального скачивания базы данных с TMDB при помощи скриптов необходимо зарегистрироваться на сайте и получить API-токен [здесь](https://www.themoviedb.org/settings/api).

Для проверки работоспособности API-токена можно запустить

`hello_api_TMDB.py`

Программа запросит токен, после его ввода в случае успеха скрипт выдаст сумму бюджета фильма **"Пила 2"** - 4000000
    
    >>>hello_api_TMDB.py
    Enter your api key
    4000000
    
Обратите внимание, что вводимый токен не отображается в консоли в целях безопасности.

Далее для полноценной работы скрипта следует создать локальную базу данных фильмов, запустив скрипт  `make_own_db.py`

Скрипт также запросит токен, после чего скачает и сохранит в файл `MyFilmDB.json` данные о фильмах с номерами в базе TMDB от 0 до 1000. Скачивание займет некоторое время - примерно 15-20 минут. Прогресс будет отбражаться в консоли.

        >>>make_own_db.py
        Enter your api key
        please, wait, this operation may take smth like 15-20 minutes
        0.0 percent complete
        10.0 percent complete
        20.0 percent complete
        30.0 percent complete
        40.0 percent complete
        50.0 percent complete
        60.0 percent complete
        70.0 percent complete
        80.0 percent complete
        90.0 percent complete

Далее скрипты работают с локальной базой данных.

## search_in_db.py

Этот скрипт ищет заданные символы или слова в оригинальных названиях фильмов, имеющихся в базе. При запуске необходимо указать путь к базе данных (по умолчанию просто `MyFilmDB.json`. После этого ввести поисковый запрос. Скрипт выведет соответствующий список фильмов.

        >>>search_in_db.py
        Enter path to DataBase:MyFilmDB.json
        Enter film to search for:a
        Ariel
        Life in Loops (A Megacities RMX)
        Sonntag im August
        Varjoja paratiisissa

## find_similar.py

Скрипт принимает название фильма и ищет в базе наиболее похожие на него картины, учитывая следующие параметры: принадлежность к одинаковым коллекциям, одинаковый оригинальный язык фильма, одинаковый бюджет, одинаковый жанр. При запуске необходимо указать путь к базе данных (по умолчанию просто `MyFilmDB.json`. После этого ввести поисковый запрос.

Выдает названия 8 наиболее "похожих" картин из базы.

        >>>find_similar.py
        Enter path to DataBase:MyFilmDB.json
        Enter film to search for:Judgment Night
        Ariel
        Four Rooms
        Life in Loops (A Megacities RMX)
        Sonntag im August
        Varjoja paratiisissa

