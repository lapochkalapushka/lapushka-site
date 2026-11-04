# Lapushka

Минимальный статический сайт независимого проекта иллюстрированных книг.
Целевой репозиторий: `lapochkalapushka/lapushka-site` (подключение Books).

## Структура

```text
public/
  index.html          Главная страница
  harms/index.html    Страница Даниила Хармса: /harms/
  404.html            Страница для неизвестных адресов
  assets/style.css    Общие стили
```

Сайт работает без JavaScript, сборки, зависимостей и внешних шрифтов.
Тексты разделов Хармса явно обозначают будущие материалы.

## Репозиторий

https://github.com/lapochkalapushka/lapushka-site

Основная ветка — `main`. Публикуемые файлы находятся в `public/`.

## Cloudflare Pages

Первая публикация выполнена 4 ноября 2026 года. Проект Cloudflare: `lapushka-lapochka`.

- Главная: https://lapushka-lapochka.pages.dev/
- Страница Хармса: https://lapushka-lapochka.pages.dev/harms/

Основной адрес проекта: `lapushka-lapochka.pages.dev`. QR-код книги ведёт на `https://lapushka-lapochka.pages.dev/harms/`.

Проект подключён к `lapochkalapushka/lapushka-site`. Изменения в `main` автоматически публикуются. Предварительные публикации других веток и комментарии в pull request включены.

| Поле | Значение |
| --- | --- |
| Project name | `lapushka-lapochka` |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | `exit 0` |
| Build output directory | `public` |
| Root directory | корень репозитория |

После изменения сайта проверить `/`, `/harms/` и страницу для неизвестного адреса. Путь `/harms/` сохранять при дальнейшем наполнении сайта.

Официальная инструкция: https://developers.cloudflare.com/pages/framework-guides/deploy-anything/

## Локальный просмотр

Если установлен Python, из корня проекта выполнить:

```sh
python -m http.server 8000 --bind 127.0.0.1 --directory public
```

Открыть http://127.0.0.1:8000/ и http://127.0.0.1:8000/harms/.
Остановить сервер сочетанием Ctrl+C. Локальный сервер Python показывает собственную страницу 404; Cloudflare Pages использует `public/404.html`.

Для новой книги создать `public/<название>/index.html` и добавить ссылку на главной странице.
