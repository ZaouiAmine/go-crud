# Go CRUD API

This is a simple CRUD (Create, Read, Update, Delete) API built with Go and the Gorilla Mux router. The API manages a collection of movies, each with an ID, ISBN, title, and director information.

## Features

- **Get All Movies**: Retrieve a list of all movies.
- **Get Movie by ID**: Retrieve details of a specific movie by its ID.
- **Create Movie**: Add a new movie to the collection.
- **Update Movie**: Update the details of an existing movie.
- **Delete Movie**: Remove a movie from the collection.

## Prerequisites

- Go 1.24.2 or later
- Gorilla Mux library (`github.com/gorilla/mux`)

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/go-crud.git
   cd go-crud
   ```

2. Initialize the Go module and install dependencies:
   ```sh
   go mod tidy
   ```

## Running the API

1. Start the server:
   ```sh
   go run main.go
   ```

2. The server will start on `http://localhost:8000`.

## API Endpoints

### Get All Movies
- **URL**: `/movies`
- **Method**: `GET`
- **Response**: JSON array of all movies.

### Get Movie by ID
- **URL**: `/movies/{id}`
- **Method**: `GET`
- **Response**: JSON object of the movie with the specified ID.

### Create Movie
- **URL**: `/movies`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "isbn": "438-1234567895",
    "title": "New Movie",
    "director": {
      "firstname": "New",
      "lastname": "Director"
    }
  }
  ```
- **Response**: JSON object of the created movie.

### Update Movie
- **URL**: `/movies/{id}`
- **Method**: `PUT`
- **Request Body**:
  ```json
  {
    "isbn": "438-1234567896",
    "title": "Updated Movie",
    "director": {
      "firstname": "Updated",
      "lastname": "Director"
    }
  }
  ```
- **Response**: JSON object of the updated movie.

### Delete Movie
- **URL**: `/movies/{id}`
- **Method**: `DELETE`
- **Response**: JSON array of remaining movies.

## Example Data

The API initializes with the following movies:
```json
[
  {
    "id": "1",
    "isbn": "438-1234567890",
    "title": "Movie One",
    "director": {
      "firstname": "John",
      "lastname": "Doe"
    }
  },
  {
    "id": "2",
    "isbn": "438-1234567891",
    "title": "Movie Two",
    "director": {
      "firstname": "Jane",
      "lastname": "Doe"
    }
  }
]
```

## License

This project is licensed under the MIT License.