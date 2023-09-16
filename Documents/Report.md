# Отчет по тестированию
Проведено тестирование формы оплаты "Путешествие дня - Марракэш"

Приложение предлагает оплатить тур с определёнными параметрами двумя способами:
- оплата по дебетовой карте
- выдача кредита с указанием банковской карты

**Краткое описание**

В ходе тестирования были проверены процессы:

- работа формы для обоих способов оплаты (по дебетовой карте и в кредит) через веб-браузер Google Chrome;
- взаимодействие приложения с банковскими сервисами;
- сохранение информации в СУБД (MySQL и PostgreSQL)

**Результаты**

Количество тест-кейсов: 38 тест-кейсов, повторяющихся для обеих СУБД:

- 4 позитивных (по 2 для каждого способа оплаты)
- 34 негативных (по 2 для каждого способа оплаты). 

Соотношение успешных/неуспешных тестов: 32/6

![AllureReport]

**Общие рекомендации**

- Составить техзадание на продукт
- Устранить найденные дефекты
- Провести повторное тестирование