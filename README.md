### Дипломный проект по профессии «Тестировщик ПО»
[![Build status](https://ci.appveyor.com/api/projects/status/rj3emib4auafmh4k?svg=true)](https://ci.appveyor.com/project/North-tx/aqa-diplom)

1. [Задание для работы](https://github.com/North-tx/AQA_Diplom/blob/main/doc/Task.md)
2. [План автоматизации тестирования](https://github.com/North-tx/AQA_Diplom/blob/main/doc/Plan.md)
3. [Отчёт по итогам тестирования](https://github.com/North-tx/AQA_Diplom/blob/main/doc/Report.md)
4. [Отчёт по автоматизации тестирования](https://github.com/North-tx/AQA_Diplom/blob/main/doc/Summary.md)
## Предустановленное окружение
 - IntelliJ IDEA
 - Docker Desktop
### Запуск проекта по тестированию сервиса для покупки туров
1. Запустить Docker Desktop.
2. Склонированный проект окрыть в IDEA.
3. Открыть терминал в IDEA.
4. Запустить контейнеры командой `docker-compose up -d --build`.
5. Запустить приложение командой:
   - Для работы с MySQL `java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar aqa-shop.jar`.
   - Для работы с Postgres `java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar aqa-shop.jar`.
6. Проверить доступность приложения в браузере по ссылке http://localhost:8080/.
7. Запустить тесты командой:
   - Для работы с MySQL `gradlew clean test -Durl="jdbc:mysql://localhost:5432/app" -Duser="app" -Dpassword="pass" --info`.
   - Для работы с Postgres `gradlew clean test -Durl="jdbc:postgresql://localhost:5432/app" -Duser="app" -Dpassword="pass" --info`.
8. Запустить Allure для создания отчёта командой `./gradlew allureServe`.
9. Остановить Allure комбинацией клавиш **Ctrl+C**, а после ввести **Y** для подтверждения.
10. Остановить приложение комбинацией клавиш **Ctrl+C**.
11. Остановить работу контейнеров командой `docker-compose down`.
