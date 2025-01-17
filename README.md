# Приложение для перевода текста

## Описание

Это простое веб-приложение на Spring Boot, которое переводит текст с одного языка на другой, используя API Яндекс.Переводчика. 

## Функциональность

- Перевод текста с разбивкой на слова для ускорения обработки.
- Многопоточность для параллельного перевода слов.
- Обработка ошибок API Яндекс.Переводчика.
- Сохранение истории запросов в базу данных H2 (in-memory).

##ограничения
-api яндекс обрабатывает только 20 запросов в секунду


## Как запустить

1. **Получите API-ключ Яндекс.Переводчика:**
   - Перейдите на [https://cloud.yandex.ru/](https://cloud.yandex.ru/) и создайте новый API-ключ для сервиса "Яндекс.Переводчик".
2. **Настройте приложение:**
   - Откройте файл `src/main/resources/application.properties`.
   - Укажите ваш API-ключ:
     ```properties
     yandex.translate.api.key=YOUR_API_KEY
     ```
   - (Опционально) Измените ID каталога Яндекс.Облака:
     ```properties
     yandex.catalog.id=YOUR_CATALOG_ID
     ``` 
3. **Запустите приложение:**
   - Из командной строки выполните: `./mvnw spring-boot:run`
4. **Откройте в браузере:**
   - Перейдите по адресу: `http://localhost:8080/translate?text=Hello world&sourceLang=en&targetLang=ru`


## Тестирование

-   Запустите тесты: `./mvnw test`
