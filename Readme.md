# Часть 0

[Database](https://supabase.com/dashboard/project/yqoalglytywaxdfociwd)

# Часть 1

[BuildShip](https://buildship.app/remix/8c7234ca-f8dd-489c-9d46-3ab210e8f8a6)
[EndPoint](https://6om791.buildship.run/mission31)

# Часть 2

[BuildShip](https://buildship.app/remix/ff587de0-0a7d-40d6-9725-227146aa851f)
[EndPoint](https://6om791.buildship.run/mission32)

# Часть 4

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
