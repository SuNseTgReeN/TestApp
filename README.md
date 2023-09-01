# Test App
## Test App предназначено для тестирования пользователей. Для тестируемых существуют специальные секретные ключи, которые позволяют пройти 2 теста: тест на IQ и тест на EQ. После прохождения тестов пользователь может увидеть свои результаты. Приложение, написанно на Python 3.10 и разработано с использованием Django 3.2 и Django DRF.

### Основные функции приложения:

- Создание теста через админ панель;
- Сохранение результатов теста IQ и времени прохождения;
- Сохранение результатов теста EQ и времени прохождения;
- Получение текущего результата прохождения теста по заданному логину.
### API предоставляет следующие эндпойнты:

- GET Poll/search/<str:secret_key>/ - поиск теста по уникальному ключу, перенаправление на страницу Poll/poll_detail/<int:pk>/
- GET Poll/poll_detail/<int:pk>/ - вывод общей информации о тесте.
- GET Poll/poll_detail/<int:pk>/go - Начало прохождения теста. Получение вопросов и ответов.
- PUT Poll/poll_detail/<int:pk>/go - Окончание прохождения теста. Вывод результатов, в зависимости от типа теста.(тип теста, количество баллов, словарь с ответами вопрос: ответ, время прохождения каждого теста, id пользователя).
