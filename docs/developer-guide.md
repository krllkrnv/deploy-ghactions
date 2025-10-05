# Руководство разработчика

## Тема MkDocs
- Каталог: `custom_theme/`, основной шаблон: `main.html` (Jinja2).
- Контент вставляется через `{{ page.content }}`.
- Поддержка ассетов: цикл по `config.extra_css` и `config.extra_javascript`.

## Стили (PostCSS)
- Исходники: `src/styles/`
- Сборка: `npm run styles:docs` → `docs/assets/styles/index.css`
- Плагины: `postcss-import`, `postcss-csso` (минификация)

## Сборка и деплой
- Локально: `mkdocs serve` / `mkdocs build`
- CI: `.github/workflows/test.yml` — сборка, минификация, строгая HTML‑валидация (Nu HTML Checker), артефакт `site/`.
- Deploy: `.github/workflows/deploy.yml` — сборка и публикация `site/` в `gh-pages`.
