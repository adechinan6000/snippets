# Mongo setup

## create: C:\Program Files\MongoDB\Server\3.4mongod.cfg


## Add this inside it:

```bash
systemLog:
    destination: file
    path: C:\Program Files\MongoDB\Server\3.4\data\log\mongod.log
storage:
    dbPath: C:\Program Files\MongoDB\Server\3.4\data\db
```