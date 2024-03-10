## database in kubernetes
benefits:
- one instance of postgres/influx that has a bunch of databases
- less worry about backing up/restoring databases in a cluster
- less breakage if one of those chart deps get upgraded
drawbacks:
- external dependency
- need to handle backups differently
- need some other computer to run these on


## psql generic command

```
k exec -it pod/postgres-1 -n database -- sh

psql

\l
```
