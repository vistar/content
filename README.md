<p align="center">
  <img src="https://i.imgur.com/GVA0m4I.png" alt="Druki" width="223">
</p>

# Druki Content

Данный репозиторий содержит исходные документы (содержимое) для [Drupal энциклопедии](https://druki.ru).

## Контрибуция

### Установка

Неважно как вы желаете принять участие, вам потребуется [GitHub аккаунт](https://github.com/join) если у вас его ещё нет. Если вы не знакомы с [git](https://git-scm.com/) и [GitHub](https://github.com/), вам может оказаться полезным материал на MDN - [Гит и ГитХаб](https://developer.mozilla.org/ru/docs/Learn/Tools_and_testing/GitHub).

Существует несколько путей как вы можете начать работать с репозиторием. Всё зависит от ваших предпочтений. Вот некоторые варианты:

* Зайдите на https://github.com/Druki-ru/content и [редактируйте](https://docs.github.com/en/github/managing-files-in-a-repository/editing-files-in-another-users-repository) документ прямо при помощи [GitHub UI](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-on-github). Это самый простой способ для внесения простых изменений в один файл или исправления опечаток.
* Зайдите на https://druki.ru/wiki и найдите материал, что вы хотите поправить. Внизу страницы в разделе «Помощь и обратная связь» нажмите на ссылку «Редактировать эту страницу». Данная ссылка откроет документ на редактирование в GitHub UI. Как и в предыдущем пункте, вы можете внести необходимые правки в документ или исправить опечатки.
* Зайдите на https://github.com/Druki-ru/content или любую другую страницу со структурой или файлами репозитория и нажмите точку `.` на клавиатуре.
* Установить и использовать [GitHub Desktop](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/github-desktop).
* Установить и использовать [GitHub CLI](https://docs.github.com/en/github/getting-started-with-github/github-cli).
* Установить `git` и использовать его любым удобным для вас способом.

Рекомендуется, по возможности, использовать [PHPStorm](https://www.jetbrains.com/ru-ru/phpstorm/) — он отлично поддерживает Markdown, понимает структуру проекта, проверяет пунктуацию и орфографию, а также позволяет делать простые рефакторинги, если вы захотите переместить документ. Более того, он будет подсвечивать примеры с кодом на PHP! Если у вас нет доступа к PHPStorm, можно рассмотреть использование [IntelliJ IDEA Community Edition](https://www.jetbrains.com/ru-ru/idea/) — она имеет все возможности PHPStorm, абсолютно бесплатна, но не будет понимать PHP.

Если вы ищете вариант полегче, [VSCode](https://code.visualstudio.com/) отличный выбор. Единственное, он не сможет произвести рефакторинг при перемещении документа.

### Простые изменения

Если вы хотите внести простые изменения в один файл, например, исправить опечатку или неточность, использование GitHub UI самый простой и быстрый способ сделать это.

Например, если вы нашли опечатку на странице [Drupal](https://druki.ru/wiki/drupal), вы можете зайти на GitHub, перейти в https://github.com/Druki-ru/content, найди документ отвечающий за эту страницу [docs/ru/drupal/drupal.md](https://github.com/Druki-ru/content/blob/master/docs/ru/drupal/drupal.md), а затем нажать на карандаш и внести исправления.

Если вы нашли опечатку прямо во время чтения, вы можете сделать это ещё быстрее — пролистайте материал до конца и нажмите на **«Редактировать эту страницу»**. Данная ссылка откроет нужный файл в данном репозитории на редактирование, как если бы вы проделали все действия из предыдущего абзаца.

Если вы не уверены нужно ли вносить изменения или в их корректности, вы можете [создать ишью](https://github.com/Druki-ru/content/issues/new) и вынести своё предложение на обсуждение. Вы также можете сделать это со страницы материала, для этого пролистайте материал до конца и нажмите **«Создать обращение»**. Данная ссылка откроет страницу создания ишьюса, попутно предоставив дополнительную информацию о материале за вас.

**Альтернативный вариант:** Нажмите `.` на клавиатуре, находясь в репозитории и вносите изменения.

### Базовые концепции

* **Документы это директории** — все документы представлены в виде директорий (например [docs/ru/drupal](docs/ru/drupal)). Данные директории могут иметь `index.md` файл, в котором и пишется содержимое (например [docs/ru/drupal/index.md](docs/ru/drupal/index.md)). Все остальные файлы, включая `*.md`, игнорируются парсером содержимого.
* **Документы пишутся с использованием Markdown** — все документы наполняются с использованием [Markdown](https://ru.wikipedia.org/wiki/Markdown) синтаксиса по спецификации [CommonMark](https://commonmark.org/). На проекте также добавлена поддержка собственных разметок. Для более детальной информации ознакомьтесь с разделом [Markdown](#markdown).
* **Все документы начинаются с Front Matter** — каждый документ должен иметь [Front Matter](#front-matter) разметку в начале документа.
* **Редиректы указываются в одном файле** — каждая языковая группа контента может содержать файл `redirects.csv` в котором можно указать редиректы для изменённого содержимого в формате `/откуда,/куда`. Он поддерживает query параметры (`?foo=bar`) и фрагменты (`#fragment`).

### Front Matter

**Front Matter** — YAML разметка в начале документа, описывающая дополнительную информацию о документе, не являющуюся частью содержимого. Данная разметка должна идти в самом начале документа и быть обёрнута в `---`.

Пример:

```markdown
---
title: Заголовок материала
slug: page-title
---

Содержимое материала.
```

Ниже перечислены все поддерживаемые свойства документа:

* `title` (обязательно): Заголовок документа. То что будет использовано в `<h1>` и `<title>`.
* `slug` (обязательно): Уникальный путь документа. Используется как суффикс URL. В контексте [Druki Website](https://github.com/Druki-ru/website), данное значение получает префикс `wiki/`. Например, документ со `slug: drupal/about` будет доступен по адресу `https://druki.ru/wiki/drupal/about`. Начальный и конечный слэш не указывается.
* `core`: Номер версии ядра, для которой написан данный документ. Используется в материалах которые написаны в контексте определённой версии Drupal. Значение должно быть `int`. Например `core: 9`.
* `category`: Позволяет категоризировать материал по названию категории в пределах `core` версии. Принимает следующие значения:
    * `area`: (обязательно) В этом параметре указывается заголовок категории. Материалы в категории будут искаться по схожему заголовку.
    * `order`: Указывает позицию данного материала в меню категории среди других материалов. Сортировка по возрастанию.
    * `title`: Переопределяет заголовок в меню категории на указанный здесь. Если не указано, будет использоваться значение `title`.
- `search-keywords`: Массив со строками, которые используются только в поиске, и имеют повышенный приоритет. В идеале, должны иметь ключевые фразы, по которым, скорее всего, люди попытаются найти материал. Например, для Libraries API это - "как подключать js css", "как добавить скрипт на страницу" и т.д. То есть то, что в заголовке никак не отражено, но имеет прямое отношение к нему.
- `metatags`: (массив) Данный параметр позволяет задать конкретные мета-теги для материала в принудительном порядке. На данный момент поддерживаются следующие переопределяемые значения:
    - `title`: (опционально) Позволяет переопределить заголовок страницы `<title></title>`, а также, все связанные метатеги `<meta name="title">`, `<meta name="twitter:title">`, `<meta property="og:title">`. Данное значение не влияет на `title` материала, он останется прежним и будет находиться в `<h1>`.
    - `description`: (опционально) Позволяет переопределить описание страницы. Влияет на следующие мета-теги: `<meta name="description">`, `<meta property="og:description">`

_Все прочие свойства, если они присутствуют, игнорируются._

### Markdown

**Markdown** — язык разметки используемый для написания материалов. Проект поддерживает Markdown синтаксис по спецификации [CommonMark](https://commonmark.org/).

На проекте также добавлена поддержка собственного синтаксиса.

#### Собственный синтаксис

#### Заметки

Позволяет добавлять различные выделяемые заметки на сайте. Всего существует 4 типа заметок:

1. `NOTE`: Обычная пометка, если вы хотите сконцентрировать внимание пользователя на чем-то важном ещё раз.
1. `WARNING`: Предупреждение о чем-то, например что можно что-то сломать или нужно сделать резервную копию перед проверкой.
1. `IMPORTANT`: Важная информацию, которую обязательно стоит изучить.
1. `TIP`: Совет, подсказка. Например можно описать какую-то неявную особенность, или дополнительную возможность, которая никак не повлияет на результат и смысл, но может оказаться приятным знанием кому-то.

Формат заметки имеют следующий:

```markdown
> [!NOTE]
> Заметка о чем либо. Поддерживает **маркдаун** внутри себя.
> Каждая новая строка должна содержать `>` до тех пор, пока это часть заметки.
>
> Все что находится внутри, воспринимается как маркдаун и не забываем, что параграфы отделяются пустой строкой. Две строки выше будут с `<br/>` переносом, а текущая, отдельным параграфом.
```

### Перелинковка

Содержимое ничего не знает о том, на каком домене, как и где оно используется и какие будут URL. Вся внутренняя перелинковка между документами должна производится при помощи относительных ссылок.

Например, имеем следующую структуру:

```
.
└── docs/
    └── ru/
        └── 8/
            ├── installation/
            │   └── index.md
            ├── drush/
            │   └── index.md
            └── changelog/
                └── index.md
```

Примеры ссылок и куда они приведут:

| Редактируемый файл                 | Ссылка                                       | Куда приведет |
|------------------------------------|----------------------------------------------|---------------|
| `docs/ru/8/installation/index.md`        | `[Drush](../drush/index.md)`                          | `docs/ru/8/drush/index.md` |
| `docs/ru/8/installation/index.md`        | `[Список изменений](../changelog/index.md)` | `docs/ru/8/changelog/index.md` |

### Добавления словаря в PHPStorm

- Откройте настройки (`CTRL + ALT + S`) и перейдите в **Editor | Proofreading | Spelling**.
- В разделе **Custom dictionaries** нажмите на + или `ALT + Insert`.
- Укажите путь до [dictionary.dic](dictionary.dic).

### Массовая проверка опечаток в PHPStorm

- `SHIFT + SHIFT` и найдите **Run Inspection by Name** или `CTRL + SHIFT + ALT + I`.
- Найдите **Typo** или **Grammar** и запустите.