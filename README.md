# cattivole.github.io

Страницы поддержки и политики конфиденциальности моих приложений.
Support pages and privacy policies for my apps.

**https://cattivole.github.io/**

| Приложение / App | Страницы / Pages |
| --- | --- |
| **CoverCast** — Now Playing для винила / for vinyl. iPhone, iPad, Apple TV, Android TV | [О приложении / About](https://cattivole.github.io/covercast/) · [Поддержка / Support](https://cattivole.github.io/covercast/support.html) · [Политика / Privacy](https://cattivole.github.io/covercast/privacy.html) · [Политика Apple TV / Apple TV privacy](https://cattivole.github.io/covercast/privacy-tv.html) |
| **Learn Notes** («Учить Ноты») — ноты на стане, пианино, слух и гитара / reading music: staff, piano, ear and guitar. iPhone, iPad | [О приложении / About](https://cattivole.github.io/learnnotes/) · [Поддержка / Support](https://cattivole.github.io/learnnotes/support.html) · [Политика / Privacy](https://cattivole.github.io/learnnotes/privacy.html) |
| **Probe Lab** — карманная лаборатория цифровой безопасности / a pocket digital-security lab. iPhone | [Поддержка / Support](https://cattivole.github.io/probelab/) · [Политика / Privacy](https://cattivole.github.io/probelab/privacy.html) |
| **Veilix** — секреты внутри обычных фотографий / secrets inside ordinary photos. iPhone, iPad, Android ([исходный код / source](https://github.com/CattivoLe/Veilix)) | [О приложении / About](https://cattivole.github.io/veilix/) · [Поддержка / Support](https://cattivole.github.io/veilix/support.html) · [Политика / Privacy](https://cattivole.github.io/veilix/privacy.html) |
| **VideoHub Control** — пульт для Blackmagic Videohub и AJA KUMO / a remote for Blackmagic Videohub and AJA KUMO routers. iPhone, iPad | [О приложении / About](https://cattivole.github.io/videohubcontrol/) · [Поддержка / Support](https://cattivole.github.io/videohubcontrol/support.html) · [Политика / Privacy](https://cattivole.github.io/videohubcontrol/privacy.html) |

## Вопросы и ошибки / Questions and bugs

Создайте обращение в [Issues](https://github.com/CattivoLe/CattivoLe.github.io/issues/new)
и укажите приложение в заголовке: `[CoverCast] …`, `[Learn Notes] …`, `[Probe Lab] …`
или `[VideoHub Control] …`.
Вопросы по Veilix — в [его репозитории](https://github.com/CattivoLe/Veilix/issues).
Напишите модель устройства, версию системы и что происходило.

Open an [issue](https://github.com/CattivoLe/CattivoLe.github.io/issues/new) with
the app's name in the title — `[CoverCast] …`, `[Learn Notes] …`, `[Probe Lab] …` or
`[VideoHub Control] …` — and include
your device model, system version and what happened.
Veilix questions go to [its own repository](https://github.com/CattivoLe/Veilix/issues).

---

## Для себя: как устроен сайт

Обычные статические страницы, без сборки. GitHub Pages публикует ветку `main`
из корня; `.nojekyll` отключает Jekyll, файлы отдаются как есть.

**Одно место для всех страниц.** Локальная копия этого репозитория одна —
`~/Develop/PrivacyPolicies`, рядом с проектами приложений. Внутрь проектов сайт
не клонируется: они ссылаются на него как на `../PrivacyPolicies`
(`Tools/site_images.py` CoverCast пишет картинки в `../PrivacyPolicies/covercast/img/`).
Все правки страниц, коммиты и `git push` — отсюда. Коммиты — с личного адреса:
`git config user.email 42239507+CattivoLe@users.noreply.github.com`.

```
├── index.html            список приложений
├── style.css             общий стиль (светлая и тёмная тема)
├── 404.html
├── covercast/
│   ├── index.html        о приложении      → Marketing URL
│   ├── support.html      поддержка         → Support URL
│   ├── privacy.html      политика          → Privacy Policy URL (и Google Play)
│   ├── privacy-tv.html   политика Apple TV → Apple TV Privacy Policy, тот же текст
│   ├── page.css          свой акцент и стили картинок поверх ../style.css
│   ├── icon.png
│   └── img/              скриншоты; делает Tools/site_images.py в репозитории CoverCast (пишет сюда)
├── learnnotes/
│   ├── index.html        о приложении      → Marketing URL
│   ├── support.html      поддержка         → Support URL
│   ├── privacy.html      политика          → Privacy Policy URL (и ссылка в Настройках приложения)
│   ├── page.css          индиго поверх ../style.css
│   ├── icon.png
│   └── img/              скриншоты из StoreAssets/Release-2.2/_raw/iphone репозитория NotesTrainer
├── probelab/
│   ├── index.html        поддержка         → Support URL
│   ├── privacy.html      политика          → Privacy Policy URL
│   └── icon.png
├── veilix/
│   ├── index.html        о приложении      → Marketing URL
│   ├── support.html      поддержка         → Support URL
│   ├── privacy.html      политика          → Privacy Policy URL
│   ├── page.css          фиолетовый акцент поверх ../style.css
│   ├── icon.png
│   └── img/              скриншоты: iPhone из store/ репозитория iOS, Android из docs/images Veilix
└── videohubcontrol/
    ├── index.html        о приложении      → Marketing URL
    ├── support.html      поддержка         → Support URL
    ├── privacy.html      политика          → Privacy Policy URL
    ├── page.css          оранжевый акцент и стили картинок поверх ../style.css
    ├── icon.png
    └── img/              скриншоты из AppStore/screenshots репозитория VideoHubControl
```

Каждая страница двуязычная: секции `#ru` и `#en` на одной странице, ссылки на
английскую версию ведут на `…#en`.

Адреса вписаны в самих приложениях и в `fastlane/metadata/*/` их репозиториев
(у Probe Lab ещё в `ProbeLab/Model/AppLinks.swift`). **Не переименовывайте файлы
и папки** — сломаются ссылки в App Store и Google Play.

Политика Apple TV повторяет текст из поля Apple TV Privacy Policy в App Store
Connect: меняете одно — меняйте и другое, вместе с датой «Действует с…».

### Новое приложение

1. Скопируйте `probelab/` в папку с коротким именем, например `myapp/`;
   замените тексты, иконку и `<title>`. Общий стиль подключается как
   `../style.css`, свой акцент — отдельным `page.css`, как у CoverCast.
2. Добавьте строку в таблицу в корневом `index.html` и в этот README.
3. В приложении ссылайтесь на `https://cattivole.github.io/myapp/`,
   `…/myapp/privacy.html`, а обращения —
   `https://github.com/CattivoLe/CattivoLe.github.io/issues/new?title=%5BMyApp%5D%20`.
4. Закоммитьте и запушьте в `main` — страница появится через минуту-две.

Не создавайте отдельный репозиторий с включёнными Pages под тем же именем, что
и папка: он займёт адрес `cattivole.github.io/<имя>/` вместо неё.

### Проверить локально

```bash
python3 -m http.server 8000
```

и открыть http://localhost:8000/.
