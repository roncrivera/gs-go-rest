# gs-go-rest
Getting Started with REST using Go.

# Prerequisites
* Install and run MongoDB.
  * ```tar -zxvf mongodb-osx-ssl-x86_64-4.0.3.tgz && ln -s mongodb*/ mongodb```
  * ```mkdir -p /data/db```
  * ```mongodb/bin/mongod```
* Go packages:
  * toml : Parse the configuration file (MongoDB server & credentials)
    * ```go get github.com/BurntSushi/toml```
  * mux : Request router and dispatcher for matching incoming requests to their respective handler
    * ```go get github.com/gorilla/mux```
  * mgo : MongoDB driver
    * ```go get gopkg.in/mgo.v2```

# Getting Started
## Run application
```go run app.go```

## Create a movie
```curl -sSX POST -d '{"name":"dunkirk", "description":"war movie"}' http://localhost:3000/movies```

## List movies
```curl -sSX GET http://localhost:3000/movies | jq '.'```

## Update movie
```curl -sSX PUT -d '{"name":"dunkirk","cover_image":"https://image.tmdb.org/t/p/w640/cUqEgoP6kj8ykfNjJx3Tl5zHCcN.jpg", "description":"world war 2 movie"}' http://localhost:3000/movies | jq '.'```

## Delete movie
```curl -sSX DELETE -d '{"name":"dunkirk","cover_image":"https://image.tmdb.org/t/p/w640/cUqEgoP6kj8ykfNjJx3Tl5zHCcN.jpg", "description":"world war 2 movie"}' http://localhost:3000/movies | jq '.'```

