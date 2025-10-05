# Руководство разработчика

## Тема MkDocs
-   Каталог: `custom_theme/`
-   Основной шаблон: `main.html`
-   Вставка контента: `{{ page.content }}`
-   Навигация: итерация по `nav` (подсветка активного пункта `nav_item.active`)
-   Метаданные: `meta description` из `config.site_description`, `meta author` из `config.site_author`
-   Ассеты: циклы по `config.extra_css` и `config.extra_javascript`

Рекомендуется расширять структуру через дополнительные блоки (например, отдельные partials), но для минимального ТЗ достаточно текущего `main.html` с `header/main/footer`.

## Стили (PostCSS)
-   Исходники: `src/styles/`
-   Сборка: `npm run styles:docs` → `docs/assets/styles/index.css`
-   Плагины: `postcss-import` (модули), `postcss-csso` (минификация)
-   Блоки темы: базовые стили для `header/nav/footer` и `.home-hero` размещены в `src/styles/blocks/page.css`

## Добавление JS (при необходимости)
-   Добавьте файл в `docs/assets/js/` и подключите путь в `extra_javascript` (`mkdocs.yml`).
-   Тема выведет теги через фильтр `script_tag`.

## CI/CD
-   Сборка и проверка (test.yml):
    1) `npm ci`
    2) `pip install -r requirements.txt`
    3) `npm run styles:docs`
    4) `mkdocs build --strict`
    5) `npm run site:minify`
    6) Nu HTML Checker (фатальный)
    7) Артефакт `site/`
-   Деплой (deploy.yml): сборка и публикация `site/` в `gh-pages`.
