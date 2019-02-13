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
