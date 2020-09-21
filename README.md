I build API solutions for people and machines. Not interested in code? Look https://wtrocki.com

##### Build GraphQL backend in less than 1 minute.

1. Define your data using GraphQL by creating model file.

`touch model.graphql && open model.graphql`

2. Build your model 

```graphql
""" @model @datasync """
type GithubRepository {
 _id: MongoObjectID!
 name: String
}

scalar MongoObjectID
``` 

3. Get your API server based on that model is backed by MongoDB database

```bash
npx graphql-serve serve --port=5400 --datasync model.graphql
```
Powered by https://graphback.dev and https://graphqlcrud.org
