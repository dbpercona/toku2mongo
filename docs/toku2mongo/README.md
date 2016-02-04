# toku2mongo - pull and replay TokuMX 2.x oplog to PSMDB 3.x
----

This tool will pull and replay a TokuMX 2.x oplog to a Percona Server
for MongoDB 3.x target.

It can be used for zero-downtime migration of TokuMX 2.x to Percona Server for
MongoDB 3.x.  See [the Percona website](https://www.percona.com/downloads/toku2mongo)
for more information.

**Usage: bin/toku2mongo {options}**

    --help                                produce help message
    -v [ --verbose ]                      be more verbose (include multiple times
                                          for more verbosity e.g. -vvvvv)
    --version                             print the program's version and exit
    -h [ --host ] arg                     mongo host to connect to ( <set 
                                          name>/s1,s2 for sets)
    --port arg                            server port. Can also use --host 
                                          hostname:port
    --ipv6                                enable IPv6 support (disabled by 
                                          default)
    -u [ --username ] arg                 username
    -p [ --password ] arg                 password
    --authenticationDatabase arg          user source (defaults to dbname)
    --authenticationMechanism arg (=MONGODB-CR)
                                          authentication mechanism
    --dbpath arg                          directly access mongod database files 
                                          in the given path, instead of 
                                          connecting to a mongod  server - needs 
                                          to lock the data directory, so cannot 
                                          be used if a mongod is currently 
                                          accessing the same path
    --directoryperdb                      each db is in a separate directly 
                                          (relevant only if dbpath specified)
    -d [ --db ] arg                       database to use
    -c [ --collection ] arg               collection to use (some commands)
    --gtid arg                            max applied GTID
    --w arg (=1)                          w parameter for getLastError calls
    --from arg                            host to pull from
    --ruser arg                           username on source host if auth 
                                          required
    --rpass arg                           password on source host
    --rauthenticationDatabase arg (=admin)
                                          user source on source host (defaults to
                                          "admin")
    --rauthenticationMechanism arg (=MONGODB-CR)
                                          authentication mechanism on source host
    --oplogns arg (=local.oplog.rs)       ns to pull from
    --reportingPeriod arg (=10)           seconds between progress reports
