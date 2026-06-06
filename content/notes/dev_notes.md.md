
# Заметки разработчика

Разные мысли, сниппеты и напоминалки, собранные за время работы.

## Полезные сниппеты

### Быстрый debounce на TypeScript

```ts
const debounce = <T extends (...args: any[]) => void>(fn: T, ms = 300) => {
    let timer: ReturnType<typeof setTimeout>;
    return (...args: Parameters<T>) => {
        clearTimeout(timer);
        timer = setTimeout(() => fn(...args), ms);
    };
};
```

### Удобные Git-алиасы

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --oneline --graph --all"
```

### Форматирование JSON в командной строке

```bash
cat data.json | python -m json.tool
# или с помощью jq
jq . data.json
```

## Горячие клавиши VS Code (мои must‑have)

| Действие | Сочетание |
|----------|-----------|
| Палитра команд | `Ctrl+Shift+P` |
| Быстрое открытие файла | `Ctrl+P` |
| Форматирование документа | `Shift+Alt+F` |
| Мультикурсор | `Ctrl+D` (по одному) / `Ctrl+Shift+L` (все) |
| Переход к определению | `F12` |

## Ресурсы, к которым я постоянно возвращаюсь

- [Roadmap.sh](https://roadmap.sh) — дорожные карты по всем направлениям
- [DevDocs](https://devdocs.io) — офлайн-документация в одном месте
- [The Pragmatic Programmer](https://pragprog.com/titles/tpp20/) — книга, обязательная к прочтению
- [Refactoring.Guru](https://refactoring.guru) — паттерны проектирования с наглядными примерами

## Правило «пяти минут»

> Если ошибка не находится за 5 минут — сделай перерыв или попроси второго человека посмотреть. Свежий взгляд решает 90% проблем.

## Чек-лист перед коммитом

- [ ] Код собирается без ошибок
- [ ] Линтер не выдаёт новых предупреждений
- [ ] Основные тесты проходят
- [ ] Комментарии на английском и понятны
- [ ] Сообщение коммита осмысленное (почему, а не что)

---

Последнее обновление: 20.02.2026
