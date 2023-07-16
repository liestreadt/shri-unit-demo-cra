# Cтруктура CI/CD

-   ## Настройки репозитория

    -   Ветки `master` и `develop` защищены от merge. Merge в эти ветки можно произвести только после созданного Pull Request(PR).
    -   Разработка велась в ветке `develop`, прошу проводить все проверки на этой ветке

-   ## Commit Lint

    -   Запускается при PR, коммите в PR и при push в любую ветку
    -   Шаблон проверки - `conventional commits`

-   ## CI Tests

    -   Запускается при PR и Release
    -   Автоматически запускаются на каждый коммит в PR
    -   Добавляется запрет на merge, если тесты не прошли проверку
    -   Список тестов:
        -   Unit Tests
        -   E2E Tests

-   ## Release

    -   Запускается автоматически при появлении нового релизного тэга по шаблону `v<Число>`
    -   Запускаются CI Tests
    -   Формируется CHANGELOG от предыдущего релизного тэга
    -   Создается или обновляется `Issue` которое содержит
        -   GitHub автора
        -   Дата релиза
        -   Версия релиза
        -   Changelog, отображаются только коммиты типа feat, fix и refactor (ограничение от action из gh marketplace, заметил только под самый конец)
        -   Номер тестов и ссылку на `Artifacts` с результатами
    -   Добавляется label `Release`
    -   Создаётся релизная ветка по шаблону `release-v<Число>`
    -   Запускается `deploy` в ветку `gh-pages`
    -   Добавляется комментарий к Issue c номером `deploy` и [ссылкой](https://liestreadt.github.io/shri-unit-demo-cra/) на него
    -   При успешном деплое Issue автоматически закрыватеся (После этого ещё какое-то время отрабатывает внутренний скрипт деплоя на `gh-pages`, примерно 1-2 мин)

# В этом репозитории находится пример приложения с тестами

-   [e2e тесты](e2e/example.spec.ts)
-   [unit тесты](src/example.test.tsx)

Для запуска примеров необходимо установить [NodeJS](https://nodejs.org/en/download/) 16 или выше.

Как запустить:

```sh
# установить зависимости
npm ci

# запустить приложение
npm start
```

Как запустить e2e тесты:

```sh
# скачать браузеры
npx playwright install

# запустить тесты
npm run e2e
```

Как запустить модульные тесты:

```sh
npm test
```
