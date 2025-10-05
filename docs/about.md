# О проекте

Цель: продемонстрировать разработку собственной темы для MkDocs и полный конвейер сборки/валидации/деплоя на GitHub Pages.

Стек:
-   MkDocs (кастомная тема: header/nav/logo, контейнеры, footer)
-   PostCSS (`postcss-import`, `postcss-csso`)
-   GitHub Actions: сборка, минификация, строгая HTML‑валидация (html5validator action)
-   GitHub Pages (ветка `gh-pages`)

Ссылки:
-   Сайт: страница GitHub Pages репозитория
-   Репозиторий: текущий проект

Как внести изменения:
-   Ветки → PR → проверки в `test.yml` → деплой `deploy.yml`.
