## GraphQL-Subscriptions-Apollo-Server-RedisPubSub

</br>

### Server
</br>
Start a node package: 

```javascript
npm init -y
```

Install Dependencies:

```javascript
npm install
```

</br>

### Redis Server

</br>

Use this [link](https://redis.io/) to install and configure the Redis server.

Start the Redis Server:
(in the terminal)
```
redis-server
```

</br>

### Testing GraphQL Subscriptions

</br>
Open a GraphQL IDE and set the url as http://localhost:4000/graphql

</br>

Run a Subscription

```
subscription receive {
  receiveMessage{
    id
    name
    content
  }
}
```


Run a Mutation
</br>

```graphql
mutation send($params: DataInput) {
  sendMessage(params: $params) {
    id
    name
    content
  }
}
```
Add the following to the query variables

```
{
  "params": {"name": "User", "content": "Hello"}
}
```

After running a mutation you should see the data has been received by the subscription request 