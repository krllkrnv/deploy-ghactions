# Быстрый старт

1. Установите зависимости:
   - Python: `pip install mkdocs`
   - Node: `npm ci`
2. Соберите стили PostCSS: `npm run styles:docs`.
3. Запустите локальный сервер: `mkdocs serve`.
4. Сборка продакшена: `mkdocs build` (результат — в папке `site/`).

Структура проекта:
- `docs/` — Markdown‑контент и ассеты.
- `custom_theme/` — шаблоны Jinja2 для темы.
- `src/styles/` — исходники CSS, сборка в `docs/assets/styles/index.css`.
