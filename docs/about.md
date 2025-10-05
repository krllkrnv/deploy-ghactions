# О проекте

Цель: продемонстрировать разработку собственной темы для MkDocs и полный конвейер сборки/валидации/деплоя на GitHub Pages.

Стек:
-   MkDocs (собственная тема через `custom_theme/`)
-   PostCSS (`postcss-import`, `postcss-csso`)
-   GitHub Actions: сборка, минификация, строгая HTML‑валидация (Nu HTML Checker)
-   GitHub Pages (ветка `gh-pages`)

Ссылки:
-   Сайт: страница GitHub Pages репозитория
-   Репозиторий: текущий проект

Как внести изменения:
-   Ветки → PR → проверки в `test.yml` → деплой `deploy.yml`.
