# oapi codegen

OpenApi의 definition으로 부터 go 소스 코드를 자동생성할때
<br>openapi-generator cli를 이용하면 변경을 적용하기가 매우 번거롭기 때문에

oapi-codegen을 이용하여 자동생성을 실시

## 분할된 definition yaml을 하나의 json 파일로 변환

분할된 파일을 하나의 파일로 변경하는 것이 편리하다.

``` sh
swagger-cli bundle -o output/openapi.output.json openapi/openapi.yaml

```

> [swagger-cli](https://github.com/APIDevTools/swagger-cli?tab=readme-ov-file#combine-multiple-files) 참조


## install 

[oapi codegen github](https://github.com/deepmap/oapi-codegen)

``` sh
go install github.com/deepmap/oapi-codegen/v2/cmd/oapi-codegen@latest
```
 커맨드 사용 안될 시 PATH를 확인

## model 생성

``` sh
oapi-codegen -generate "types" -package openapi ../md-convertor-definition/output/openapi.output.json > ./src/type.gen.go
```

## server 생성

```
oapi-codegen -generate "server" -package openapi ../md-convertor-definition/output/openapi.output.json > ./src/server.gen.go
```