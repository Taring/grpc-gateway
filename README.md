# grpc-gateway
The GRPC HTTP Proxy

## Features
* not need modify .proto
* not need generate code before compiler 

## Dependent
* VS 2017 or gcc 7.0
* nghttp2
* protobuf

## Build
1. `git submodule init`
2. `git submodule update`
3. `mkdir build` & cd `build`
4. `cmake -G "Visual Studio 15 Win64" ..`

## Test
1. run your grpc server, listen port:`8888`
2. run your proxy of cmd: `grpc_proxy.exe 0.0.0.0 8080 127.0.0.1 8888 echo_service.proto`
3. use `curl -v -XPOST http://localhost:8080/sofa.pbrpc.test.EchoServer.Echo -d {"message":"hello"}`

## TODO
* Dont't create new connection to grpc server when every client enter.
* Use some internal HTTP API for control proxy server, eg compiler .proto from client runtime.
even for reload .proto.