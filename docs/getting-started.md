# Быстрый старт

## Требования
-   Python 3.x
-   Node.js 18+ (в CI — Node 20)

## Установка
1.  Установите Python‑зависимости:
    -   `pip install -r requirements.txt`
2.  Установите Node‑зависимости:
    -   `npm ci`

## Локальная разработка
1.  Соберите стили PostCSS:
    -   `npm run styles:docs` → `docs/assets/styles/index.css`
2.  Запустите превью MkDocs:
    -   `mkdocs serve`
3.  Откройте URL из консоли (обычно `http://127.0.0.1:8000`).

## Продакшен‑сборка локально
-   `mkdocs build` → результат в каталоге `site/`.
-   При необходимости минифицируйте HTML: `npm run site:minify`.

## Структура проекта
-   `docs/` — Markdown‑страницы и ассеты сайта.
-   `custom_theme/` — Jinja2‑шаблон темы (`main.html`, header/footer/nav/meta).
-   `src/styles/` — исходники CSS; сборка PostCSS → `docs/assets/styles/index.css`.
-   `mkdocs.yml` — конфиг сайта: тема, навигация, extra_css, метаданные.
-   `.github/workflows/` — CI для сборки/валидации и деплоя.

## CI/CD (кратко)
-   Test: сборка CSS → MkDocs → минификация → строгая HTML‑валидация → артефакт `site/`.
-   Deploy: сборка и публикация `site/` в `gh-pages` (GitHub Pages).
