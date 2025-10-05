# Руководство разработчика

## Тема MkDocs
-   Каталог: `custom_theme/`
-   Основной шаблон: `main.html`
-   Вставка контента: `{{ page.content }}`
-   Навигация: итерация по `nav` (подсветка активного пункта `nav_item.active`)
-   Домашняя ссылка: `href="{{ (nav.homepage and nav.homepage.url) | default('.') | url }}"` — всегда ведёт на главную независимо от глубины URL
-   Ассеты: циклы по `config.extra_css` и `config.extra_javascript`

## Стили (PostCSS)
-   Исходники: `src/styles/`
-   Сборка: `npm run styles:docs` → `docs/assets/styles/index.css`
-   Базовые стили: `src/styles/blocks/page.css` (тёмный фон, меню, футер, `.home-hero`)

## Добавление JS (при необходимости)
-   Добавьте файл в `docs/assets/js/` и подключите путь в `extra_javascript` (`mkdocs.yml`).

## CI/CD
-   Сборка и проверка (test.yml):
    1) `npm ci`
    2) `pip install -r requirements.txt`
    3) `npm run styles:docs`
    4) `mkdocs build --strict`
    5) `npm run site:minify`
    6) Строгая HTML‑валидация (GitHub Action html5validator) каталога `site/`
    7) Артефакт `site/`
-   Деплой (deploy.yml): сборка и публикация `site/` в `gh-pages`.
