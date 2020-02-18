# Grakn Simulation World

## Build and run Simulation
```shell script
bazel run //:simulation -- -d -k world
```

## Running with Logsplit
Logsplit is a simple Python 3 script designed to split the logs of simulation based on a tracker for ease of testing.

Ensure the `logs/` directory exists.
```shell script
mkdir logs
```
Pipe the output of simulation to logsplit:
```shell script
bazel run //:simulation -- -d -k world | python3 logsplit.py
```
The separated logs can then be found in the `logs/` directory.

## CLI options

### Standard Options
```
-k,--keyspace <keyspace>
    Grakn keyspace
    REQUIRED

-g,--grakn-uri <uri>
    Grakn server URI
    default: localhost:48555

-s,--seed <seed>
    Simulation randomization seed
    default: A random seed generated by Java.

-i,--iterations <iterations>
    Number of simulation iterations
    default: 10
```

### Grabl Tracing Options
```
-d,--disable-tracing
    Disable Grabl Tracing

REQUIRED OPTIONS (if tracing is enabled):

-o,--organisation <name>
    Grabl/GitHub organisation for Grabl Tracing

-r,--respository <name>
    Grabl/GitHub repository for Grabl Tracing

-c,--commit <sha>
    Grabl/GitHub commit for Grabl Tracing

-u,--username <username>
    Grabl/GitHub username for Grabl Tracing

-a,--api-token <token>
    Grabl API token for Grabl Tracing
```