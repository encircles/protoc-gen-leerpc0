# protoc-gen-leerpc0
protocol file generation tool for leerpc0

## Install

1. First of all, you need to install the protoc tool, [protoc](https://github.com/protocolbuffers/protobuf/releases/tag/v3.0.2)

2. Then you need to install the protoc-gen-go tool
                                                  
    ```sh
    go get -u github.com/golang/protobuf/protoc-gen-go
    ```
3. Run the following command in the terminal to install protoc-gen-gorpc

    ```sh
    go get -u -v github.com/encircles/protoc-gen-leerpc0
    ```

### Quick Start

1. Writing a protocol file, for example :
  
```proto
    syntax = "proto3";
    
    service Greeter {
        rpc Hello(Request) returns (Response) {}
    }
    
    message Request {
        string name = 1;
    }
    
    message Response {
        string msg = 1;
    }

```

2. Run the following command to generate the pb.go file

    ```sh
    protoc --leerpc0_out=plugin:. greeter.proto
    ```

   A file greeter.pb.go is generated.
    
