**I build API solutions for people and machines. Not interested in code? Look https://wtrocki.com **

## Try stack I use

### Build GraphQL backend  

> Define your data using GraphQL 

```graphql
""" @model @datasync """
type GithubRepository {
 _id: MongoObjectID!
 name: String
}
``` 
\> model.graphql

> Run API server that is backed by mongo database

```bash
npx graphql-serve serve --port=5400 --datasync model.graphql
```
Powered by https://graphback.dev and https://offix.dev
