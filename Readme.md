**Запрос 1**
```sql
select *
from users
```
**Запрос 2**
```sql
 SELECT users.username AS usernames, COUNT(messages.id) AS number_of_sent_messages
 FROM users
 JOIN messages ON users.id = messages.from
 GROUP BY users.username
```
**Запрос 3**
```sql
 SELECT username, COUNT(*) AS "number of received messages"
 FROM messages
 JOIN users ON messages.to = users.id
 GROUP BY username
 ORDER BY COUNT(*) DESC
```
**Запрос 4**
```sql
 SELECT username, AVG(cnt) AS "average number of sent messages"
 FROM(
 SELECT messages.from, COUNT(*) AS cnt
 FROM messages
 GROUP BY messages.from
 ) AS message_count
 JOIN users ON message_count.from = users.id
 GROUP BY username
```
