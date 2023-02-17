# Скрипты для скачивания книг с электронной библиотеки
Скрипты для скачивания книг с [сайта](https://tululu.org/) и создания собственной электронной библиотеки.
Пример можно посмотреть [тут](https://0viktory0.github.io/biblio/pages/index1.html).

## Как установить
Python3 должен быть уже установлен.
Затем используйте `pip` (или `pip3`, если есть конфликт с Python2) для установки зависимостей:
```
pip install -r requirements.txt
```

## Как запустить
Для запуска скрипта необходимо запустить файл из консоли.
```
$ python имя_скрипта.py
```

### parse_tululu.py
Скрипт скачает первые 10 книг с id 1 по 10.
Можно задать свой промежуток, указав его при запуске.
```
$ python parse_tululu.py --start_id=3 --end_id=10
```

### parse_tululu_category.py
Скрипт скачивает книги заданной категории. По умолчанию скачает книги из категории "Научная фантастика" с 1 по 5 страницу. 
Так же, можно задать следующие настройки:

- `start_page` - Номер первой страницы для скачивания
- `end_page` - Номер последней страницы для скачивания 
- `books_category` - Категория книг
- `skip_img` - Отменяет скачивание обложек, по умолчанию False
- `skip_txt` - Отменяет скачивание книг, по умолчанию False
- `dest_folder` - Папа для скачивания файлов, по умолчанию базовая.
- `json_path` - Папка для скачивания файла `.json`, в котором находится информация о скаченных книгах, по умолчанию `books.json`

### render_website.py
Скрипт для создания собственной электронной библиотеки.
Для начала, с помощью скрипта `parse_tululu_category.py` необходимо скачать книги, обложки для 
книг и файл карточек `books_description.json`.<br>
Скрипт создаст готовые web-страницы с книгами, по 20 книг на странице с возможностью чтения.<br>
Сайт можно запустить локально по адресу `http://127.0.0.1:5500/pages/index1.html`.

Пример запуска скрипта:
```
$ python render_website.py
[I 230213 20:39:18 server:335] Serving on http://127.0.0.1:5500
[I 230213 20:39:18 handlers:62] Start watching changes
[I 230213 20:39:18 handlers:64] Start detecting changes
[I 230213 20:39:30 handlers:135] Browser Connected: http://127.0.0.1:5500/
```

## Цель проекта
Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).
