# Нотатки розробника

## Формування mailto-посилань

Посилання `mailto:` дозволяє відкрити поштовий клієнт із заповненими полями.

Приклад використання у вебі:

```html
<a href="mailto:kirillvelicka0@gmail.com?subject=Привіт&body=Повідомлення%20з%20сайту">Написати лист</a>
```

**Важливі моменти:**
- Усі спеціальні символи потрібно кодувати через `encodeURIComponent()` (пробіл → `%20`, перенос рядка → `%0A`).
- Параметри `subject` та `body` не обов’язкові, але покращують досвід користувача.
- Не варто жорстко прописувати тему і тіло в HTML — динамічно формуйте рядок у JavaScript.

```js
const mailto = `mailto:user@example.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
window.location.href = mailto;
```
---

*Оновлено: 2026*