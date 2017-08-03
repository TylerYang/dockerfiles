json-server
===========

Get a full fake REST API with zero coding in less than 30 seconds (seriously) with [json-server][1].

## docker-compose.yml

```yaml
json-server:
  image: tyler/json-server
  command: -w db.json
  ports:
    - "3000:3000"
  volumes:
    - ./db.json:/app/db.json
  restart: always
```

## db.json

```json
{
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" }
  ],
  "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ],
  "profile": { "name": "typicode" }
}
```

## up and running

```bash
docker-compose up -d

curl http://localhost:3000/posts
```

[1]: https://github.com/typicode/json-server
