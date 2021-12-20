# grpc-gateway-template

# Prerequisites
- Install [buf](https://buf.build/)

## Launch service
### Install tool dependencies
- We have tools.go to track tool dependencies for this module.
```shell
go mod tidy
```
### Generate protobuf
```shell
make generate
```
### Launch gRPC service
1. Run gRPC server
```shell
go run cmd/server/main.go
```
2. Run gRPC-gateway
```shell
go run cmd/gateway/main.go
```

## Test
Request
```shell
curl --location --request POST 'http://localhost:8081/v1/echo' \
--data-raw '{
    "message": "JJJ"
}'
```
Response
```
{"message":"Hello JJJ"}
```
## TODO
- Use docker build
- Integrate to kubernetes
- docker-compose (option)
