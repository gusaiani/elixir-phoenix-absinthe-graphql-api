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

## Create a booking

This request requires an authentication token

```
mutation {
  createBooking(
    placeId:1,
    startDate: "2020-10-13",
    endDate:"2020-10-16"
  ) {
    id
    endDate
    startDate
    totalPrice
    state
  }
}
```

## Cancel a booking

This request requires an authentication token

```
mutation {
  cancelBooking(
    bookingId:13
  ) {
    id
    state
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

## Subscribe to a booking change (create/cancel)

To trigger it, open another window at http://localhost:4000/graphiql and create a booking or cancel an existing one

```
subscription {
  bookingChange(placeId: 1) {
    startDate
    endDate
    state
  }
}
```

## Passing an authentication token

* In localhost:4000/graphiql
* Click on Headers › + Add
* Add Name: authorization
* Add Value: Bearer ${your_token}
* Click on OK
