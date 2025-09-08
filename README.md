# Микросервисный калькулятор

[![Java](https://img.shields.io/badge/Java-17-blue?logo=openjdk)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-green?logo=springboot)](https://spring.io/projects/spring-boot)
[![H2 Database](https://img.shields.io/badge/H2-Database-orange?logo=h2)](https://www.h2database.com)
[![Swagger](https://img.shields.io/badge/Swagger-3.0-85ea2d?logo=swagger)](https://swagger.io/)
[![JUnit](https://img.shields.io/badge/JUnit-5.10-brightgreen?logo=junit5)](https://junit.org/junit5/)


Микросервисное клиент-серверное приложение на Java Spring Boot, выполняющее арифметические операции (сложение и вычитание) с сохранением результатов в in-memory базе данных H2. Проект включает веб-интерфейс Swagger для тестирования API и полный набор модульных тестов.

## Возможности

-   **REST API**: Эндпоинты для сложения (`/add/{a}/{b}`) и вычитания (`/subtract/{a}/{b}`)
-   **Сохранение результатов**: Все вычисления автоматически сохраняются в базе данных H2
-   **Просмотр истории**: GET-запрос на `/calcList` возвращает список всех предыдущих результатов
-   **Интерактивная документация**: Интегрированный Swagger UI для визуального тестирования API
-   **Полное тестирование**: Набор модульных тестов, проверяющих корректность работы калькулятора
-   **In-Memory База данных**: Используется H2 Database для хранения данных без внешних зависимостей

## Технологический стек

-   **Backend**: Java 17, Spring Boot 3.2.1
-   **База данных**: H2 Database (in-memory)
-   **Документация API**: Swagger 3.0 / OpenAPI
-   **Тестирование**: JUnit 5, Spring Boot Test
-   **Сборка**: Maven
-   **Вспомогательные библиотеки**: Lombok

## Запуск приложения

### Предварительные требования

-   Установленный JDK 17 или выше
-   Maven 3.6+ (опционально, можно использовать встроенный в IDE)
-   Любая IDE (IntelliJ IDEA, Eclipse, VS Code) или командная строка

### Сборка и запуск

1.  **Клонируйте репозиторий**:
    ```bash
    git clone https://github.com/your-username/practice-java.git
    cd practice-java
    ```

2.  **Соберите проект с помощью Maven**:
    ```bash
    mvn clean package
    ```

3.  **Запустите приложение**:
    ```bash
    java -jar target/practice-0.0.1-SNAPSHOT.jar
    ```

    *Или запустите прямо из IDE, найдя класс `PracticeApplication`.*

4.  **Приложение запущено!** Доступно по адресу: `http://localhost:8080`

## Использование API

### 1. Базовые операции

-   **Сложение**: `GET http://localhost:8080/add/{a}/{b}`
    ```http
    GET /add/10/7
    Ответ: 17
    ```

-   **Вычитание**: `GET http://localhost:8080/subtract/{a}/{b}`
    ```http
    GET /subtract/10/7
    Ответ: 3
    ```

### 2. Просмотр истории вычислений

-   **Получить все результаты**: `GET http://localhost:8080/calcList`
    ```http
    GET /calcList
    Ответ: [17, 3, 25, ...]
    ```

### 3. Интерактивная документация (Swagger UI)

После запуска приложения откройте в браузере:  
**`http://localhost:8080/swagger-ui/index.html`**

Здесь вы можете:
-   Просмотреть все доступные эндпоинты
-   Тестировать API прямо в браузере
-   Изучить модели данных и форматы запросов/ответов

### 4. Консоль базы данных H2

Для просмотра и управления базой данных перейдите по адресу:  
**`http://localhost:8080/h2-console`**

**Данные для подключения:**
-   JDBC URL: `jdbc:h2:mem:testdb`
-   User Name: `sa`
-   Password: *(оставить пустым)*

## Документация

В папке [`/docs/`](/docs/) находится полная документация по проекту.
