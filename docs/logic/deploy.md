# 3.4. Публикация сайта на GitHub Pages и настройка сборки и деплоя

1) Выполните в терминале VS Code команду `mkdocs gh-deploy`.  
GitHub автоматически опубликует собранный сайт на GitHub Pages. В логах терминала отобразится URL сайта.  
2) Создайте папку `.github` в корне проекта.
3) Создайте папку `workflows` в папке `.github`.
4) Создайте файл `ci.yml` в папке `workflows`.
5) Вставьте в файл `ci.yml` следующий код:
```
name: ci
on:
  push:
    branches:
      - main
permissions:
  contents: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: 3.x
      - uses: actions/cache@v2
        with:
          key: ${{ github.ref }}
          path: .cache
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```
6) Перенесите изменения из локальной копии в репозиторий.  
GitHub Actions позволяет автоматизировать процессы сборки и деплоя проекта. Теперь деплой будет запускаться автоматически при обновлении главной ветки.  