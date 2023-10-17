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

- Now to use database run command **npx prisma init**

    - This command will create a folder `prisma` that have schem.prisma file where we can specify the database which we like to use and the its credentials.

- Define the database name (used mysql) and url ( used localhost) 
- `DATABASE_URL = mysql://root:root@127.0.0.1:3306/inventory`
- Cross-check the localhost url and port.
- Define models for Category and Tag
- Then run the command **$ npx prisma migrate dev --name create-categories-and-tags-table**

- Updated the schema.prisma ( db models);
- run **$ npx prisma migrate dev --name create-products-table**

##### Working with the Prisma client
- to access data and store data in db install prisma-client
- run `npm i @prisma/client`

```
**Migrations not required for MongoDB as it an oriented document database.**
```

##### Seeding the database
- create a seed.ts in prisma folder and write code to add some default categories/tags 

- Update package.json
    ```
    "prisma":{
        "seed":"ts-node prisma/seed.ts"
    }
    ```
- Install: `npm i ts-node`
- RUN: `npx prisma db seed`
- CHECK: check db to see the added data.

