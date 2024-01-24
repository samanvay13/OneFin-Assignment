# OneFin-Assignment
## API 1. Login API

POST https://demo.onefin.in/api/v1/usermodule/login/

Sample request:
{
  'username': 'testuser',
 'password': 'v^4!C%CQ94f0'
}

Sample success response:
{
   'is_success': true,
   'data': {
       'token': <Token to be sent for authentication of future requests>
   }
}
API 2. Movie API

The movie API is described below. Note that this is a paginated API, for the next set of movies, a link to the next page is provided.

You have to attach an authorization header for the API to work, specified below. Use the token stored in local storage in the login api response for this.

Add header: ‘Authorization’: ‘Token <token obtained in login API>’

GET https://demo.onefin.in/api/v1/maya/movies/

The response is a paginated list of movies, returning 10 movies at a time:

{
    “count”: <total number of movies>,
    “next”: <link for next page, if present>,
    “previous”: <link for previous page>,
    “data”: [
        {
            “title”: <title of the movie>,
            “description”: <a description of the movie>,
            “genres”: <a comma separated list of genres, if present>,
		 “uuid”: <a unique uuid for the movie>
        },
        ...
    ]
}
