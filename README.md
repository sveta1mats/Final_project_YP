Финальный проект (вторая практическая часть)

ПЕРВАЯ ЧАСТЬ - SQL-запросы, работа с БД:

1 запрос:

SELECT c.login, COUNT(o."inDelivery")  

FROM "Couriers" AS c 

INNER JOIN "Orders" AS o ON o."courierId" = c.id 

WHERE o."inDelivery" = true

GROUP BY c.login;

2 запрос:

SELECT track, 

CASE 

WHEN o.finished = true THEN 2 

WHEN o.cancelled = true THEN -1 

WHEN o."inDelivery" = true THEN 1 

ELSE 0 END AS status 

FROM "Orders" AS o;


Для данных запросов приложен файл: SQL-запросы_Вывод Терминала.txt
___________________________________________________________________
ВТОРАЯ ЧАСТЬ - Автоматизация теста к API
- Созданные файлы: configuration.py, data.py, sender_stand_request.py, 
create_order_tests.py, README.md, .gitignore. 
- Для запуска тестов должны быть установлены пакеты pytest и requests
- Перед запуском нужно обновить URL_SERVICE в  configuration
- В файле sender_stand_request нажать кнопку Run
- Скриншот запуска автотеста в файле Scrinshot&autotest
