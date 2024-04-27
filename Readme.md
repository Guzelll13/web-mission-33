# Mission 2

## Part 0

[Link to video](https://disk.yandex.ru/i/dXoCIutitcr3jw)

## Part1

- Вопрос 1	 
> SSH (Secure Shell) используется для безопасного удаленного доступа и управления серверами. Он обеспечивает шифрование данных и аутентификацию, что делает передачу информации через сеть безопасной.

- Вопрос 2	 
> Публичный ключ Васи нужно добавить в файл ~/.ssh/authorized_keys на сервере, чтобы он мог подключиться к терминалу.

- Вопрос 3	 
> Long polling - это техника, при которой клиент отправляет запрос на сервер, который остается открытым до появления новой информации. Webhooks - это механизм, при котором сервер отправляет HTTP POST запросы на указанный URL при наступлении определенных событий.

- Вопрос 4	 
> Issues на GitHub используются для отслеживания задач, багов, улучшений и других вопросов в проекте. Примеры issues: 
   - https://github.com/facebook/react/issues
   - https://github.com/tensorflow/tensorflow/issues

- Вопрос 5	 
> Чтобы добавить пустую папку в Git, можно создать в ней временный файл .gitkeep, который не будет использоваться, но позволит Git отслеживать пустую директорию.
> 


# Mission 3

## Part 0-2

[Link to video](https://disk.yandex.ru/i/T809ea3z76_H8g)

## Part 3
- Получить список юзернеймов пользователей:
> SELECT username FROM users;

- Получить кол-во отправленных сообщений каждым пользователем:
> SELECT u.username, COUNT(m.id) AS number_of_sent_messages
FROM users u
LEFT JOIN messages m ON u.id = m.from
GROUP BY u.username;

- Получить пользователя с самым большим кол-вом полученных сообщений и само количество:
> SELECT u.username, COUNT(m.id) AS number_of_received_messages
FROM users u
LEFT JOIN messages m ON u.id = m.to
GROUP BY u.username
ORDER BY number_of_received_messages DESC
LIMIT 1;

- Получить среднее кол-во сообщений, отправленное каждым пользователем:
> SELECT AVG(messages_per_user) AS average_messages_sent_per_user
FROM (
    SELECT COUNT(id) AS messages_per_user
    FROM messages
    GROUP BY "from"
) AS subquery;

