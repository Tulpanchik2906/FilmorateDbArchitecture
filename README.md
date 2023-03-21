# FilmorateDbArchitecture
```mermaid
erDiagram
    FILM {
				integer id PK "id фильма"
        string name "название фильма"
        string description "описание фильма"
        date releaseDate "дата выхода фильма"
				integer duration "длительность фильма в минутах"
				integer rating_mpa_id FK "id рейтинга mpa"
    }
		
		GENRE{
				integer id PK "id фильма"
        string name "название фильма"
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
		}
		
		FRIEND {
		
		}
  ```
