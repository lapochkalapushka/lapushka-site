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

После загрузки файлов в GitHub:

1. В Cloudflare открыть Workers & Pages → Create application → Pages → Import an existing Git repository.
2. Подключить GitHub-аккаунт `lapochkalapushka` и выбрать `lapushka-site`.
3. Использовать настройки:

| Поле | Значение |
| --- | --- |
| Project name | `lapushka`, если свободно |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | `exit 0` |
| Build output directory | `public` |
| Root directory | корень репозитория (поле оставить пустым) |

4. Выполнить Save and Deploy. Проверить `/`, `/harms/` и неизвестный адрес (ответ 404).

Доступность `lapushka.pages.dev` пока не подтверждена. Использовать адрес в QR-коде только после успешной публикации и проверки. Путь `/harms/` сохранять при дальнейшем наполнении сайта.

Официальная инструкция: https://developers.cloudflare.com/pages/framework-guides/deploy-anything/

## Локальный просмотр

Если установлен Python, из корня проекта выполнить:

```sh
python -m http.server 8000 --bind 127.0.0.1 --directory public
```

Открыть http://127.0.0.1:8000/ и http://127.0.0.1:8000/harms/.
Остановить сервер сочетанием Ctrl+C. Локальный сервер Python показывает собственную страницу 404; Cloudflare Pages использует `public/404.html`.

Для новой книги создать `public/<название>/index.html` и добавить ссылку на главной странице.
