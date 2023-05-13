# README

## Setup

### Initialize the replica set

```bash
docker compose up -d

docker compose exec mongo1 mongosh --eval "rs.initiate({
 _id: \"myReplicaSet\",
 members: [
   {_id: 0, host: \"mongo1\"},
   {_id: 1, host: \"mongo2\"},
   {_id: 2, host: \"mongo3\"}
 ]
})"
```

Details about the replica set with Docker can be found [here](https://www.mongodb.com/compatibility/deploying-a-mongodb-cluster-with-docker/).

### Makes sure the replica set is working

```bash
docker compose exec mongo1 mongosh --eval "rs.status()"
```
