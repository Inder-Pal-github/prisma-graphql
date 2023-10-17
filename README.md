# This project will be the foundation for the GraphQL API that will be build and deploy

### Step 1 - Creating  the node.js project.
```
    npm init -y
    npm i apollo-server graphql --save
```

```
- apollo-server is the HTTP library that you use to define how GraphQL requests are resolved and how to fetch data.
- graphql is the library you’ll use to build the GraphQL schema.
```

### Step 2 - Defining the GraphQL Schema and Resolvers

- will define the GraphQL schema and corresponding resolvers. The schema will define the operations that the API can handle. The resolvers will define the logic for handling those requests using in-memory data structures, which you will replace with database queries

```
mkdir src
nano src/schema.js
```

