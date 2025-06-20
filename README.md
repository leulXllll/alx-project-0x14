# alx-project-0x14
## API overview
- The API Documentation includes path end points , the query parameters avialible for those specific end points , it also gives us the return descriptions (meaning what we should expect from the each api calls).
## Version
- Api version 1
## Available Endpoints
/titles : returns titles of the movies
/x/titles-by-ids : retus titles by their ids
/titles/{id}: returns title according to filters by id
/titles/{id}/ratings: returns title ratings
/titles/series/{id} : returns array of episodes
/titles/seasons/{id} : returns number of seasons
/titles/series/{id}/{season} : reurns array of episodes
/titles/episode/{id} : return episodes according to filters
/titles/x/upcoming: returns array of upcoming titles

/titles/search/keyword/{keyword}: returns array of titles according to filters
/titles/search/title/{title}: returns array of titles according to filters
/titles/search/akas/{aka}: returns array of titles according to filters

/actors: returns array of actors
/actors/{id} : return details about actor

/title/utils/titleType:return array of title types
/title/utils/genreType: return array of genre types
/title/utils/lists: returns array of lists

 ## Request and Response Format 
 Request
#### A GET request is made to the /x/titles-by-ids endpoint, with query parameters including:
    idsList (required): an array of title ID strings.
    list (optional): a predefined category from Utils - Titles Lists.
    info (optional): boolean flag to indicate if detailed info should be returned.
Example Request:
GET /x/titles-by-ids?idsList=123&idsList=456&list=featured&info=true
Response

The response is a JSON array of title objects. Each object follows the title model structure.
Example Response:

[
  {
    "id": "123",
    "name": "Inception",
    "genre": "Sci-Fi",
    "release_year": 2010,
    "rating": 8.8
  },
  {
    "id": "456",
    "name": "Interstellar",
    "genre": "Sci-Fi",
    "release_year": 2014,
    "rating": 8.6
  }
]
Each object in the array includes fields defined in the title model. These typically include:
    id (string): unique identifier of the title
    name (string): name of the title
    genre (string): genre category
    release_year (number): release year of the title
    rating (number): average user rating
## Authentication
- Lets first sign up for rapid api account after obtaining api keys, then in the enviroment variable we store our api keys we set them on our headers for authentication purpose
## Error Handling
- By responding to proper api call status we prevent our app to behave unexpectedly if error occurs 
## Usage Limits and Best Practices
-Clients are limited to 100 request per minute exceeding this limit could result in temporarly blocking or throttling
-Use Filtering: When using /titles, always apply query parameters like list or sorting options to narrow down the dataset and reduce unnecessary load