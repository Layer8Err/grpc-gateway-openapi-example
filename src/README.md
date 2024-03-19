# grpc-gateway-openapi-example

Just an example of creating a gRPC service and generating an OpenAPI spec then
exposing it over HTTP too.

## Tools

- [buf](https://buf.build)
- [protoc](https://grpc.io/docs/protoc-installation/)
- [protoc-gen-go and protoc-gen-grpc](https://grpc.io/docs/languages/go/quickstart/)
- [protoc-gen-grpc-gateway](https://grpc-ecosystem.github.io/grpc-gateway/)
- [protoc-gen-openapiv2](https://pkg.go.dev/github.com/grpc-ecosystem/grpc-gateway/v2@v2.11.0/protoc-gen-openapiv2)

## Running

```
> go run cmd/example.go
2022/07/20 16:15:13 gRPC server ready on localhost:5566...
2022/07/20 16:15:13 HTTP server ready on localhost:8080...
```

Open http://localhost:8080/swagger-ui/ to view the generated docs. The UI is
literally copied from https://github.com/swagger-api/swagger-ui/tree/master/dist
as that is the intended use of it.

## Modifying `protos/service.proto`

If you modify this file you need to rebuild and regenerate files. We use the
`buf` CLI to do this.

```
> buf build

> buf generate
```