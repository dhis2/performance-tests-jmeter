# DHIS2 Performance Tests (JMeter)

These JMeter scripts mock calls done by Android SDK for data synchronization (download/upload).

The API calls are based on Sierra Leone demo data set.

## Requirements

- DHIS2 (2.29-2.32) with Sierra Leone demo DB
- JMeter >= 5.0.0
- JMeter plugins
    * jpgc - Standard Set
    * 3 Basic Graphs
    * 5 Additional Graphs
    * Command-Line Graph Plotting Tool
    * Graphs Generator Listener
    * PerfMon (Servers Performance Monitoring)

**Note:** To monitor server performance using PerfMon you need the [ServerAgent](https://github.com/undera/perfmon-agent) utility.


## Usage

You can run the tests by JMeter GUI tool (not recommended) or by JMeter CLI.

To run a test using JMeter CLI, you can use the helper script **run-test.sh** which needs some parameter:

```
TEST_FILE PROTOCOL HOST PORT RAMP_UP_SECONDS MIN_USER_COUNT MAX_USER_COUNT STEP_USER_COUNT [LOOP_COUNT]
```

Example:

```bash
./run-test.sh tests/data-download-no-events.jmx https play.dhis2.org/android-current 443 0 1 1 1 1
```

**Note:** Default location for JMeter is *apache-jmeter* directory on current directory, you can edit *run-test.sh* if you need to change it.