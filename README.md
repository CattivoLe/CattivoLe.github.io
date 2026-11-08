# Общий сайт приложений на GitHub Pages

Один публичный репозиторий **`CattivoLe.github.io`** на все приложения. GitHub
публикует репозиторий с таким именем по корневому адресу
`https://cattivole.github.io/`, а каждое приложение — отдельная папка в нём:

```
CattivoLe.github.io/
├── index.html          список приложений
├── style.css           общий стиль
├── .nojekyll           отдавать файлы как есть
└── probelab/
    ├── index.html      поддержка (Support URL)
    ├── privacy.html    политика конфиденциальности (Privacy Policy URL)
    └── icon.png
```

Адреса Probe Lab (уже вписаны в `ProbeLab/Model/AppLinks.swift` и
`fastlane/metadata/*/`):

- https://cattivole.github.io/probelab/
- https://cattivole.github.io/probelab/privacy.html
- обращения: https://github.com/CattivoLe/CattivoLe.github.io/issues — с
  «[Probe Lab]» в заголовке, кнопка «Сообщить о проблеме» подставляет его сама.

Код приложений публиковать не нужно: основные репозитории остаются приватными,
в общий попадают только страницы.

## Первая публикация (5 минут)

1. Войдите на github.com под аккаунтом **CattivoLe**.
2. Создайте **публичный** репозиторий с именем ровно **`CattivoLe.github.io`**
   (https://github.com/new, без README). Имя должно совпадать с логином, иначе
   сайт окажется не в корне, а по адресу `cattivole.github.io/<имя>/`.
3. Загрузите содержимое папки `site/` (кроме этого README по желанию):

   ```bash
   cd "/Users/alex/Develop/Probe Lab/site"
   git init -b main
   git add .
   git commit -m "Сайт приложений: Probe Lab"
   git remote add origin https://github.com/CattivoLe/CattivoLe.github.io.git
   git push -u origin main
   ```

   Или в браузере: Add file → Upload files, перетащить всё содержимое `site/`
   вместе с папкой `probelab`.
4. **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   ветка **main**, папка **/(root)**, Save. У репозитория `*.github.io` это
   обычно включено сразу.
5. Через 1–2 минуты откройте https://cattivole.github.io/probelab/privacy.html
   в браузере без входа в GitHub.
6. Проверьте, что **Issues** включены: Settings → General → Features.
7. В App Store Connect впишите адреса из `fastlane/metadata/*/` (подробно —
   `docs/app-store-review/submission-checklist.md`).

## Как добавить другое приложение

1. Скопируйте папку `probelab/` под коротким именем нового приложения,
   например `myapp/`, и замените тексты, иконку и название в заголовке.
   Стиль подключается как `../style.css`, его копировать не нужно.
2. Добавьте строку в таблицу в корневом `index.html`.
3. В приложении ссылайтесь на `https://cattivole.github.io/myapp/` и
   `.../myapp/privacy.html`, а обращения — на
   `https://github.com/CattivoLe/CattivoLe.github.io/issues/new?title=%5BMyApp%5D%20`.
4. `git add . && git commit && git push` — страница появится через минуту.

Одно ограничение: не создавайте отдельный репозиторий с Pages под тем же именем,
что и папка (например, публичный репозиторий `probelab` с включёнными Pages) —
он займёт адрес `cattivole.github.io/probelab/` вместо папки.

## Где хранить исходники

Удобно держать живую копию прямо в клоне `CattivoLe.github.io`, а папку `site/`
этого проекта считать исходником Probe Lab: после правок скопировать
`site/probelab/` в клон и запушить.

## Контактный email

Apple ждёт на странице поддержки способ связаться с разработчиком. Issues для
этого подходят, но многим пользователям проще написать письмо. Если хотите,
добавьте адрес в раздел «Поддержка» в `probelab/index.html`.
