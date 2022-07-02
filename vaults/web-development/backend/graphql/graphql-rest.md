graphql: a specification
rest: architectural concept

** An iterative approach to GraphQL needs.

```
GET /user/123/name
> techbos
```

One day we decide to also return user's `age`. So we come up with 4 options:

-   Option A: create a new endpoint for `age`
```
GET /user/123/age
> 23
```

-   Option B: merge `age` with `name`
```
GET /user/123/nameAndAge
> { "name": "techbos", "age": 23 }
```

-   Option C: return the entire `user` object and let client pick whichever fields they want
```
GET /user/123
> { "name": "techbos", "age": 23, "id": 123, "location": "Seattle", ... }
```

-   Option D: use query params
```
GET /user/123?fields=name,age
> { "name": "techbos", "age": 23 }
```

Option D is reasonable but there can be nested fields.

To solve this, we replace the url query param `?fields=` with a _JSON-like request body_. We also use `POST` instead of `GET`.  
```
// Replace ?fields=name,age with request body
POST /user/123
// JSON-like request body for selecting fields
{
  name {
    first
  }
  age
}
```


** One more iteration ** 
```
// Get user 123's first name and age
POST /user/123 { name { first }, age }
// Get user 123's post title and content
POST /posts/user/123 { title, content }
```

We can take this with only one HTTP request
```
POST /smartql
// One request body to query for two things
{
  // Replaces /user/123
  user(id: 123) {
    name {
      first
    }
    age
  }
  // Replaces /posts/user/123
  posts(userId: 123) {
    title
    content
  }
}
```




