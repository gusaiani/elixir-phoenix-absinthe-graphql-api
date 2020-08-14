# Examples of GraphQL requests

## Sign up

```
mutation {
  signup (
    username: "Gustavo Saiani",
    email: "gustavo@poe.ma",
    password: "arstarst"
  ) {
    user {
      username
      email
    }
    token
  }
}
```

## Sign in

```
mutation {
  signin (
    username: "Gustavo Saiani",
    password: "arstarst"
  ) {
    token
  }
}
```

## List places

```
query {
  places(limit: 10) {
    id
    name
    location
  }
}
```

## Get a place by its slug

```
{
  place(slug: "dock-house") {
    id
    name
    bookings {
      state
      totalPrice
    }
  }
}
```

## Create a review

This request requires an authentication token

```
mutation {
	createReview (
    placeId:"3",
    comment: "Wonderful!",
    rating: 5
  ) {
    id
    comment
    rating
  }
}

```

## Passing an authentication token

* In localhost:4000/graphiql
* Click on Headers › + Add
* Add Name: authorization
* Add Value: Bearer ${your_token}
* Click on OK
