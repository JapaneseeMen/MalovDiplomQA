# MalovDiplomQA

## Дипломный проект профессии «Тестировщик»

Данный проект представляет собой тестирование веб-сервиса покупки тура "Путешествие дня - Марракэш" 
(предоставленного в виде приложения). Приложение предлагает купить тур по определённой цене с помощью 
двух способов: обычная оплата по дебетовой карте и выдача кредита по данным банковской карты. 
Приложение в собственной СУБД сохраняет информацию о том, каким способом был совершён платёж и успешно 
ли он был совершён. 

В рамках проекта составляется план тестирования. На основании плана создаются автотесты. Они проверяют
позитивные и негативные сценарии покупки. Результаты тестов обрабатываются и визуализируются во внешней
системе отчетов. На основании полученного отчета даются рекомендации по улучшению сервиса.

[План тестирования](https://github.com/JapaneseeMen/MalovDiplomQA/blob/main/Documents/Plan.md)

[Отчет по тестированию](https://github.com/JapaneseeMen/MalovDiplomQA/blob/main/Documents/Report.md)

[Отчет о выполнении плана тестирования](https://github.com/JapaneseeMen/MalovDiplomQA/blob/main/Documents/Summary.md)

## Подготовка и настройка окружения

* Java 11
* IntelliJ IDEA 2022.3.1 с подключенными библиотеками файл [build.gradle](https://github.com/JapaneseeMen/MalovDiplomQA/blob/main/build.gradle) :
  * JUnit Jupiter
  * Selenide 
  * Selenium Java
  * Lombok
  * JavaFaker
  * WebDriverManager 
  * Apache Commons DbUtils
  * MySQL Connector
  * PostgreSQL JDBC Driver
  * Allure

* в качестве SUT используется 
  [aqa-shop.jar](https://github.com/netology-code/qa-diploma/blob/master/aqa-shop.jar)

## Установка и запуск приложения, автотестов и отчетов

Учётные данные и url для подключения задаются в файле [application.properties](https://github.com/JapaneseeMen/MalovDiplomQA/blob/main/application.properties)

## **перед запуском закомментировать строку с ненужной БД**

* запустить IntelliJ IDEA с проектом с депозитария
  * git clone ```https://github.com/JapaneseeMen/MalovDiplomQA/tree/main```

  * перейти в папку с проектом 
    * cd ```MalovDiplomQA```
  * запустить docker container (настройки в файле docker-compose.yml)
    * ```docker-compose up```   
  * дождаться запуска контейнеров
* в терминале IntelliJ IDEA запустить SUT:
    - с использованием БД MySQL командой 
      ```java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar artifacts/aqa-shop.jar```
    - с использованием БД PostgreSQL командой
      ```java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar artifacts/aqa-shop.jar```
* в терминале IntelliJ IDEA запустить автотесты командой:
    - для конфигурации БД MySql:  
      ```./gradlew clean test "-Ddb.url=jdbc:mysql://localhost:3306/app"```
    - для конфигурации БД PostgreSQL:  
      ```./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/app"```
* в терминале IntelliJ IDEA запустить отчеты командой:
    - ```./gradlew allureReport ```
    - ```./gradlew allureServe ```
* в терминале IntelliJ IDEA остановить SUT
  * ```CTRL+C```
* на виртуальной машине остановить работу контейнеров
  * ```docker stop $(docker ps –a –q)``` 

* ### Для повторного тестирования в папке проекта удалить папки "data" , "data2"

