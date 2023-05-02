# Horror Film Text Analysis

## Data

These tables can be accessed at the following link: https://virginia.box.com/s/4zfi385yvykwvuui179slxfubf22t5cq

This project consists of 21 CSV tables

### Data Description

#### CORPUS & CORPUS_1980 & CORPUS_1990 & CORPUS_2000:

| Column    | Type  | Description                                                                            |
|-----------|-------|----------------------------------------------------------------------------------------|
| movie_id  | int   | The ID of the associated film in the corpus                                            |
| scene_id  | int   | The scene number in the film                                                           |
| sent_num  | int   | The sentence number in the scene                                                       |
| token_num | int   | The token number in the sentence                                                       |
| pos_tuple | tuple | The token and its NLTK tagged part of speech                                           |
| pos       | str   | The part of speech associated with the token                                           |
| token_str | str   | A token in the corpus                                                                  |
| term_str  | str   | A normalized version of a token in the corpus in lowercase with any characters removed |

CORPUS contains all the films in the corpus
CORPUS_1980 & CORPUS_1990 & CORPUS_2000 contain only films for that decade

#### VOCAB & VOCAB_1980 & VOCAB_1990 & VOCAB_2000:

| Column         | Type  | Description                                                                  |
|----------------|-------|------------------------------------------------------------------------------|
| term_str       | str   | A term in the corpus                                                         |
| n              | int   | The number of times that term appears in the corpus                          |
| n_chars        | int   | The number of characters of the term                                         |
| p              | float | The probability of that term appearing in the corpus                         |
| i              | float | The inverse log of the probabily                                             |
| max_pos        | str   | The most frequently associated part-of-space category for each token         |
| n_pos          | str   | The number of parts of speech associated with that token                     |
| cat_pos        | list  | A concatenated list of all the parts of speech associated with that token    |
| stop           | int   | 1 indicates the token is a stopword, 0 indicates the token is not a stopword |
| stem_porter    | str   | Porter stemming algorithm applied to the term                                |
| stem_snowball  | str   | Snowball stemming algorithm applied to the term                              |
| stem_lancaster | str   | Lancaster stemming algorithm applied to the term                             |
| tfidf          | float | Term frequency-inverse document frequency                                    |

VOCAB contains all the films in the corpus
VOCAB_1980 & VOCAB_1990 & VOCAB_2000 contain only vocab tables for films for that decade


#### LIB:

| Column           | Type | Description                       |
|------------------|------|-----------------------------------|
| movie_id         | int  | The ID associated with that movie |
| movie_title      | str  | The title of the movie            |
| source_file_path | str  | The path to the source file       |
| year             | str  | The year of the film's release    |
| decade           | str  | The decade of the film's release  |
| movie_len        | int  | The number of tokens in the movie |
| n_scenes         | int  | The number of scenes in the movie |

#### DOC:

| Column           | Type | Description                                |
|------------------|------|--------------------------------------------|
| movie_id         | int  | The ID associated with that movie          |
| scene_id         | int  | The scene number in the movie              |
| movie_title      | str  | The title of the movie                     |
| source_file_path | str  | The path to the source file                |
| year             | str  | The year of the film's release             |
| decade           | str  | The decade of the film's release           |
| movie_len        | int  | The number of tokens in the movie          |
| n_scenes         | int  | The number of scenes in the movie          |
| title            | str  | The movie title concatenated with the year |


#### TFIDF (Term Frequency-Inverse Document Rrequency):

| Column   | Type | Description                                               |
|----------|------|-----------------------------------------------------------|
| movie_id | int  | The movie ID associated with a particular film            |
| scene_id | int  | The scene number in that film                             |
| term     | str  | Each token in the corpus represented as a separate column |

#### DFIDF:

| Column   | Type  | Description          |
|----------|-------|----------------------|
| term_str | str   | A term in the corpus |
| DFIDF    | float | DFIDF of term        |

#### Content:

| Column          | Type      | Description                                                                   |
|-----------------|-----------|-------------------------------------------------------------------------------|
| CLIENT          | VARCHAR   | ID for the client                                                             |
| ID              | VARCHAR   | Unique ID for the row. Connects with Event set_profile                        |
| CONTENT_ID      | VARCHAR   | Unique ID for each content                                                    |
| KEYWORDS        | ARRAY     | Keywords associated with a content                                            |
| DOWNLOAD_SLIDE  | DOUBLE    | Number of times the content had a download slide event                        |
| PDF_CLICK       | DOUBLE    | Number of times the content had a PDF click event                             |
| PAGEVIEW        | DOUBLE    | Number of times the content had a page view event                             |
| POST_READ       | DOUBLE    | Number of times the content had a post read event                             |
| POST_READ_MID   | DOUBLE    | Number of times the content had a post read mid event                         |
| POST_READ_START | DOUBLE    | Number of times the content had a post read start event                       |
| POST_READ_END   | DOUBLE    | Number of times the content had a post read end event                         |
| SCROLL          | DOUBLE    | Number of times the content had a scroll event                                |
| EXCERPT         | VARCHAR   | Text excerpt from the content                                                 |
| CONTENT         | VARCHAR   | Description of the content                                                    |
| SCORE           | DOUBLE    | Sum of all the event columns                                                  |
| SOURCE          | VARCHAR   | Source of the content                                                         |
| TITLE           | VARCHAR   | Title of the content                                                          |
| TYPE            | VARCHAR   | Type of the content                                                           |
| URL             | VARCHAR   | URL of the content                                                            |
| CREATED         | TIMESTAMP | Timestamp of when a content was created                                       |
| UPDATED         | TIMESTAMP | Timestamp of when a content was updated                                       |
