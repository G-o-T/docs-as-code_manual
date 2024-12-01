# 3.5. Настройка конфигурационного файла

1. Скопируйте и вставьте в первую строку файла `mkdocs.yml` код:

```
site_name:  # Название сайта
site_description:  # Описание сайта, надо для meta-тегов
nav:
  - index.md
theme: # Тема сайта и ее параметры
    name: material # Название темы
    logo: logo.png # Ссылка на логотип сайта
    language: ru # Язык
    font:
      text: Inter # Шрифт текста
      code: Roboto Mono # Шрифт для текста кода
    palette: # Настройки светлой и тёмной тем
    - media: "(prefers-color-scheme: light)"
      scheme: default
      toggle:
        icon: material/brightness-4
        name: Темное оформление
      primary: amber
      accent: cyan
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      toggle:
        icon: material/brightness-7
        name: Светлое оформление
      primary: amber
      accent: cyan 
    features:
      - navigation.indexes # Необходимо для создания корневых страниц разделов меню
      - navigation.top # Кнопка для быстрой обратной прокрутки страницы
      - search.suggest # Подсказки при вводе поискового запроса
      - search.highlight # Подсветка результатов поиска на странице
      - content.code.copy # Кнопка копирования в блоке кода
markdown_extensions: # Расширения markdown
  - def_list # Поддержка списков определений
  - pymdownx.tabbed # Поддержка табов
  - pymdownx.details # Поддержка спойлеров (катов)
  - pymdownx.snippets # Поддержка сниппетов
  - pymdownx.superfences # Поддержка вложенных блоков кода
  - footnotes # Поддержка встроенных сносок на страницах
  - tables # Поддержка таблиц
  - admonition # Поддержка информационных панелей
  - attr_list # Использование html-атрибутов и CSS в элементах markdown
  - md_in_html # Поддержка markdown внутри html
  - smarty # конвертирует дефисы в тире
  - pymdownx.emoji: # Иконки и эмодзи
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg
  - pymdownx.highlight: # Подсветка синтаксиса в блоках кода
      anchor_linenums: true
```

2. Скорректируйте значения ключей `site_name` и `site_description` в соответствии с разрабатываемой технической документацией.   
3. Перенесите изменения из локальной копии в репозиторий.
