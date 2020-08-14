# GraphQL API with Elixir, Phoenix and Absinthe

## Installation

1. Install Elixir dependencies:

    ```sh
    mix deps.get
    ```

2. Create the database, run all the migrations, and load the sample data:

    ```sh
    mix ecto.setup
    ```

3. Make sure all the tests pass:

    ```sh
    mix test
    ```

4. Fire up the Phoenix endpoint:

    ```sh
    mix phx.server
    ```

5. Visit [`localhost:4000/graphiql`](http://localhost:4000/graphiql) to explore the GraphQL API using the GraphiQL user interface.

## Example Queries, Mutations, and Subscriptions

https://github.com/gusaiani/elixir-phoenix-absinthe-graphql-api/blob/main/docs/requests.md
