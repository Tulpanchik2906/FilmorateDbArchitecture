# FilmorateDbArchitecture
```mermaid
erDiagram
    FILM {
				integer id PK "id фильма"
        varchar name "название фильма"
        varchar description "описание фильма"
        date releaseDate "дата выхода фильма"
				integer duration "длительность фильма в минутах"
				integer rating_mpa_id FK "id рейтинга mpa"
    }
		
		GENRE{
				integer id PK "id фильма"
        varchar name "название фильма"
		}

		FILM_GENRE{
				integer film_id FK "id фильма"
        integer genre_id FK "id жанра"
		}

		LIKE{
			integer film_id FK "id фильма"
			integer user_id FK "id пользователя"
		}	

		RATING_MPA{
			integer id PK "id рейтинга mpa"
			varchar rating
		}
	
		USER {
				integer id PK "id Пользователя"
				varchar email "email пользователя"
				varchar login "логин пользователя"
				varchar name "имя пользователя"
				date birthday "день рождение"
		}
		
		FRIENDSHIP {
			integer initiator_id "id инициатора дружбы"
			integer acceptor_id "id принимающего дружбу"
			boolean status "статус дружбы"
		}

		FILM ||--o{ LIKE : pl
		FILM ||--o{ FILM_GENRE : pl
		GENRE ||--o{ FILM_GENRE : pl
		FILM ||--o{ RATING_MPA : pl
		
		USER ||--o{ LIKE : pl
		USER ||--o{ FRIENDSHIP : pl
		
  ```
