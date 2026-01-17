# Руководство разработчика

## Тема MkDocs
- Каталог: `custom_theme/`
- Шаблон: `main.html`
- Контент: `{{ page.content }}`
- Навигация: итерация по `nav`, активный пункт `nav_item.active`
- Домашняя ссылка: `href="{{ (nav.homepage and nav.homepage.url) | default('.') | url }}"`
- Ассеты: циклы по `config.extra_css` и `config.extra_javascript`

## Стили (PostCSS)
- Исходники: `src/styles/`
- Сборка: `npm run styles:docs` → `docs/assets/styles/index.css`
- Базовые стили: `src/styles/blocks/page.css`

## JavaScript
Файлы в `docs/assets/js/`, подключение через `extra_javascript` в `mkdocs.yml`.

## CI/CD
**Test (test.yml):**
1. `npm ci`
2. `pip install -r requirements.txt`
3. `npm run styles:docs`
4. `mkdocs build --strict`
5. `npm run site:minify`
6. HTML-валидация `site/`
7. Артефакт `site/`

**Deploy (deploy.yml):** публикация `site/` в `gh-pages`
