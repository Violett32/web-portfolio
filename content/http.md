---
title: "Тема 4 - HTTP"
date: 2025-10-16
---

# Тема 4 - HTTP

1. Устанавливаю Telnet
![Устанавливаю Telnet](/web-portfolio/2_1.png)

GET-запрос: подключаюсь к учебному серверу и ввожу
```
GET /get?name=boreevav HTTP/1.1
Host: httpbin.org
Connection: close
```
И получила JSON ответ от сервера
![JSON-ответ](/web-portfolio/2_2.png)

POST-запрос: снова подключаюсь к серверу и отправляю запрос
```
POST /post HTTP/1.1
Host: httpbin.org
Content-Type: application/json
Content-Length: 56
Connection: close

{"student":"Boreeva Violetta","project":"Web Portfolio","grade":5}
```
![Запрос](/web-portfolio/2_3.png)

Сервер получил мой запрос, успешно его обработал и вернул в ответе то, что я ему отправила (значит данные дошли правильно).
![Запрос](/web-portfolio/2_4.png)

2. cURL
Get-запрос: ввожу в терминале
```
curl "https://httpbin.org/get?name=boreevav"
```

Сервер вернул JSON с параметром name
![JSON](/web-portfolio/2_5.png)

POST-запрос: ввожу в терминале 
```
curl -X POST "https://httpbin.org/post" \
  -H "Content-Type: application/json" \
  -d '{"student":"Boreeva Violetta","project":"Web Portfolio","grade":5}'
```
И получаю в ответе JSON с параметрами и телом запроса, что подтверждает успешную передачу данных
![JSON](/web-portfolio/2_6.png)

3. Выбрала Postman, тк он до этого был установлен
4. GET запрос в Банк России
Создаю новый запрос
![Запрос](/web-portfolio/2_7.png)

Для обращения к API Центробанка ввожу https://www.cbr.ru/scripts/XML_dynamic.asp и выбираю метод GET
![Запрос](/web-portfolio/2_8.png)

Далее хочу получить курс евро с 10 по 17 октября этого года. Для этого ввожу в key и value следующие данные
![Данные](/web-portfolio/2_9.png)

При нажатии на Send получила в ответе страницу 404
![404](/web-portfolio/2_10.png)

Пробую ввести все данные в строке запроса
https://www.cbr.ru/scripts/XML_dynamic.asp?date_req1=10/10/2024&date_req2=17/10/2024&VAL_NM_RQ=R01239
![Запрос](/web-portfolio/2_11.png)

и в ответе получаю xml документ с курсами евро за эти даты
![XML](/web-portfolio/2_12.png)