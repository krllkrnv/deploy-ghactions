# Быстрый старт

## Требования
- Python 3.x
- Node.js 18+ (CI использует Node 20)

## Установка
1. Python-зависимости: `pip install -r requirements.txt`
2. Node-зависимости: `npm ci`

## Локальная разработка
1. Сборка стилей: `npm run styles:docs` → `docs/assets/styles/index.css`
2. Запуск превью: `mkdocs serve`
3. Открыть `http://127.0.0.1:8000`

## Продакшен-сборка
- `mkdocs build` → `site/`
- Минификация HTML: `npm run site:minify`

## Структура проекта
- `docs/` — Markdown и ассеты
- `custom_theme/` — Jinja2 шаблон (`main.html`)
- `src/styles/` — исходники CSS, сборка PostCSS
- `mkdocs.yml` — конфигурация
- `.github/workflows/` — CI/CD

## CI/CD
- Test: сборка CSS → MkDocs → минификация → HTML-валидация → артефакт `site/`
- Deploy: публикация `site/` в `gh-pages`
