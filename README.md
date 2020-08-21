**I build API for people (with some ocassional bugs 🙈)**

#### Want to try my stack?

##### Get GraphQL backend  

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
Powered by https://graphback.dev

##### Build client apps without being data engineer (with offline support)

> Generate client side database (with automatic replication to server)
```bash
npx @offix/cli generate model.graphql ./generated
```
> Use simplied API to work with the database or hooks if you react(ing)

```ts
import { GithubRepositoryModel } from './generated';
import { DataStore } from 'offix-datastore';

export const datastore = new DataStore({
  dbName: "offix-datasync",
  replicationConfig: {
    client: {
      url: "http://localhost:5400/graphql",
      wsUrl: "ws://localhost:5400/graphql",
    }
  }
});

GithubRepositoryModel.save({name: "offix"}).then(async (result) => {
    result.name = "offix datastore";
    await UserModel.updateById(result);
    await UserModel.removeById(result.id);
}).catch(console.log)
``` 

Powered by https://offix.dev
