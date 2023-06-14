# Node application for GraphQL

A nodejs (express) server for graphQL simple APIs.
A two collections are provided as static data: **books** and **authors**. 

Use API-a to list collections or to add a new item to each of them.

## Install npm packages
`npm install`

## Start node server
`npm run devStart`

An express server should be started and listening on the port 5000.

Open the URL: [http://localhost:5000/graphql](http://localhost:5000/graphql)

**Use the following APIs in your browser to fetch or insert a new item.**

### List authors with their books.
```
query {
  authors {
    id
    name
    books {
      id
      name
    }
  }
}
```

### List books with it's author. 
```
query {
  books {
    id
    name
    authorId
    author {
      name
      books {
        id
        name
      }
    }
  }
}
```

### Fetch book with id=1 and author's name.
```
query {
  book(id: 1) {
    name
    authorId
    author {      
      name
    }
  }
}
```

### Fetch author with id=1 and his books.
```
query {
  author(id: 1) {
    id
    name
    books {
      id
      name
    }
  }
}
```

### Add a new book to the collection.
```
mutation {
  addBook(name: "Gone with the wind", authorId: 1) {
    id
    name
  }
}
```

### Add a new author to the collection.
```
mutation {
  addAuthor(name: "Milos Petkovic") {
    id
    name
  }
}
```


