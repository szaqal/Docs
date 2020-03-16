# GRPC

### RPC types 

* Unary RPCs request / response model ```rpc SayHello(HelloRequest) returns (HelloResponse)```

* Server Streaming RPC request  / multiple messages back ```pc LotsOfReplies(HelloRequest) returns (stream HelloResponse)```

* Client streaming RPCs ```rpc LotsOfGreetings(stream HelloRequest) returns (HelloResponse)```

* Bidirectional Steaming ```rpc BidiHello(stream HelloRequest) returns (stream HelloResponse)```


#### Error Codes

* [Status codes](https://github.com/googleapis/googleapis/blob/master/google/rpc/code.proto)
