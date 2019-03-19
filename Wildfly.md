# Wildfly

* Access cli 
```
./bin/jboss-cli.sh
[disconnected /] connect localhost:9990
[standalone@localhost:9990 /]
```

* Remove subsystem

```
[standalone@localhost:9990 /] /subsystem=batch-jberet:remove
{
    "outcome" => "success",
    "response-headers" => {
        "operation-requires-reload" => true,
        "process-state" => "reload-required"
    }
}
[standalone@localhost:9990 /] reload
```

```
[standalone@localhost:9990 /] /subsystem=ejb3/strict-max-bean-instance-pool=slsb-strict-max-pool/:read-resource
{
    "outcome" => "success",
    "result" => {
        "derive-size" => "from-worker-pools",
        "max-pool-size" => 20,
        "timeout" => 5L,
        "timeout-unit" => "MINUTES"
    }
}
```


```
[standalone@localhost:9990 /] /subsystem=ejb3/thread-pool=default:read-resource
{
    "outcome" => "success",
    "result" => {
        "keepalive-time" => {
            "time" => 100L,
            "unit" => "MILLISECONDS"
        },
        "max-threads" => 10,
        "name" => "default",
        "thread-factory" => undefined
    }
}
```

```
[standalone@localhost:9990 /] /subsystem=ejb3/thread-pool=default:write-attribute(name=max-threads,value=512)
```

List JNDI 

```
/subsystem=naming:jndi-view()
```

Running scripts

```
./jboss-cli.sh -c --file=./disable-modules.cli
```

