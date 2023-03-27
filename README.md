# FilmorateDbArchitecture

![alt text](https://github.com/Tulpanchik2906/FilmorateDbArchitecture/blob/main/QuickDBD-export-filmorate.png)

## Основные запросы к БД
- Получить список всех фильмов
``` sql
SELECT * FROM FILMS;
```

- Получить фильм по id
``` sql
SELECT * FROM FILMS
WHERE ID = <film_id>;
```

- Получить список всех пользователей
``` sql
SELECT * FROM USERS;
```

- Получить пользователя по Id
``` sql
SELECT * FROM USERS
WHERE ID = <user_id>;
```

- 10 Самых популярных фильмов
``` sql
SELECT FILMS.NAME, COUNT(LIKES.USER_ID)
FROM FILMS
LEFT JOIN LIKES ON
FILMS.ID = LIKES.FILM_ID
GROUP BY FILMS.ID
ORDER BY COUNT(LIKES.USER_ID) DESC
LIMIT 10;
```

- Получить список id пользователей, которые лайкнули фильм
``` sql
SELECT LIKES.USER_ID
FROM LIKES
JOIN FILMS
ON FILMS.ID = LIKES.FILM_ID
WHERE FILMS.ID = <film_id>
```
