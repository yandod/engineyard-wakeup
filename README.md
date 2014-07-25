# Engineyard::Wakeup

Boot and stop existing environment on Engine Yard Cloud.

## Installation

    $ gem install engineyard

## Usage

### Boot stopped environment

```
$ ey environments -a=todo
your-account/todo
    testenv                       [ production ]  (stopped)
$ ./bin/ey-wakeup boot \
-e=testenv \
-ip=54.83.57.226 \
-apps=2 \
-apps-size=m3_medium　\
-app-snapshot=latest \
-db-size=m3_medium \
-db-snapshot=latest \
-db-volume=5 \
-db-iopos=500 \
-slave0=slavedbname \
-slave0-size=m3_medium \
-slave0-volume=5 \
-utility0=utilname \
-utility0-size=m3_medium \
-utility0-volume=5 \
-utility0-iops=500
$ ey environments -a=todo
your-account/todo
    testenv                       [ production ]  3 instances
```

### Stop running environment

```
$ ./bin/ey-wakeup stop -e=testenv
$ ey environments -a=todo
your-account/todo
    testenv                       [ production ]  (stopped)
```
