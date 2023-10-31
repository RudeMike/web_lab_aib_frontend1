## Get запрос

```Git
$ curl -v www.youtube.com
```

Получили код:
```
 % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:--  0:00:05 --:--:--     0*   Trying 64.233.164.198
  0     0    0     0    0     0      0      0 --:--:--  0:00:08 --:--:--     0* Connected to www.youtub
  0     0    0     0    0     0      0      0 --:--:--  0:00:09 --:--:--     0> GET / HTTP/1.1
> Host: www.youtube.com
> User-Agent: curl/7.79.1
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 301 Moved Permanently
< Content-Type: application/binary
< X-Content-Type-Options: nosniff
< Cache-Control: no-cache, no-store, max-age=0, must-revalidate
< Pragma: no-cache
< Expires: Mon, 01 Jan 1990 00:00:00 GMT
< Date: Tue, 24 Oct 2023 07:28:23 GMT
< Location: https://www.youtube.com/
< Server: ESF
< Content-Length: 0
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
<
  0     0    0     0    0     0      0      0 --:--:--  0:00:09 --:--:--     0
* Connection #0 to host www.youtube.com left intact
```

Описание к коду
```
$ curl -v www.youtube.com - Получение заголовков HTTP (ключ -v) с сайта www.youtube.com
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:--  0:00:05 --:--:--     0*   Trying 64.233.164.198
  0     0    0     0    0     0      0      0 --:--:--  0:00:08 --:--:--     0* Connected to www.youtub
  0     0    0     0    0     0      0      0 --:--:--  0:00:09 --:--:--     0> GET / HTTP/1.1 - запрашиваемый ресурс на постоянной основе переехал на новый адрес. Тогда новый путь к ресурсу указывается сервером в заголовке Location ответа.

```
# Заголовки запроса <br>
1. GET / HTTP/1.1 говорит об отправке GET-запроса на главную страницу сайта;
2. User-Agent: содержит информацию о типе и версии браузера или приложения, с помощью которого был отправлен запрос (в данном случае это Curl и соответсвенно его версия);
3. Accept: определяет форматы контента, которые клиент может принять в ответ на запрос (в данном случае */* означает, что принимается любой тип данных и формат);
# Заголовки ответа <br>
1. HTTP/1.1 301 Moved Permanently: эта строка говорит о получении ответа от сервера с кодом 301 (перенаправление), что означает, что данный URL был перемещен и нужно использовать новый, который находится в строке Location;
2. Server: ESF: сервер, который обрабатывает наш запрос;
3. Connection: keep-alive: информация о том, что нужно делать с соединением после выполнения запроса (в данном случае оставить открытым);
4. Последующие строки являются телом ответа в виде HTML-кода;
5. Connection  #0 to host www.youtube.com left intact: завершение соединения с сервером.