# Статический сайт на MkDocs (кастомная тема + CI/CD)

## Что это
-   Кастомная тема MkDocs: `custom_theme/main.html` (header/nav/logo, контейнеры, footer).
-   Тёмная стилизация: градиент фона, аккуратные контейнеры, меню с hover.
-   Контент: `docs/` (Markdown), стили: PostCSS → `docs/assets/styles/index.css`.
-   CI: сборка CSS, MkDocs, минификация HTML, строгая HTML‑валидация (GitHub Action html5validator).
-   Деплой: GitHub Pages (ветка `gh-pages`).

## Локальный запуск
1.  Установить зависимости:
    -   Python: `pip install -r requirements.txt`
    -   Node: `npm ci`
2.  Сборка CSS: `npm run styles:docs`
3.  Превью: `mkdocs serve`
4.  Продакшен‑сборка: `mkdocs build`

## CI/CD
-   `.github/workflows/test.yml`
    -   `npm ci` → `pip install -r requirements.txt`
    -   `npm run styles:docs` → `mkdocs build --strict`
    -   `npm run site:minify` → html5validator (строгая валидация) по каталогу `site/`
    -   Артефакт `site/`
-   `.github/workflows/deploy.yml`
    -   Сборка (как выше) → публикация `site/` в `gh-pages`

## Конфиг MkDocs
-   `mkdocs.yml`: `theme.name: null`, `custom_dir: custom_theme`, `extra_css`, `nav`, `site_name/description/author`.

## Адрес сайта
-   GitHub Pages: Settings → Pages (ветка `gh-pages`).
