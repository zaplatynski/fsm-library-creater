# FSM Library Creater [![Build Status](https://travis-ci.org/zaplatynski/fsm-library-creater.svg?branch=master)](https://travis-ci.org/zaplatynski/fsm-library-creater)

The FSM Library Creator is a small but useful apllication of the [FSM Maven Packagetype](https://github.com/zaplatynski/fsm-packagetype). It can be used to provide Library-FSMs such as JDBC drivers to the FirstSpirit CMS.

There are predefined working Maven profiles for
- PostgreSQL
- MySQL
- HyperSQL
- SQLite

OracleDB and Microsoft SQL server are special cases. For OracleDB please read their [blog about how to get a JDBC driver](https://blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc).

But this is not limited to JDBC drivers. Any library which should be public avaialable for FirstSpirit CMS can add anew profile. Please send me a pull request if you think others might benefit too.

## Bugs and feature requests

Please file any **bug** or **feature request** here at [github.com/zaplatynski/fsm-library-creater/issues](https://github.com/zaplatynski/fsm-library-creater/issues). Thanks!
 
## Build

[Maven](http://maven.apache.org/) is used to assemble the FirstSpirit module (FSM):
```
mvn clean package -p postgres
```
The example above will create the FSM for the PostgreSQL JDBC Driver.

##  Disclaimer

By using it you agree to the license stated in the file [LICENSE](LICENSE). The JDBC drivers are respective property of the DBMS vendors. FirstSpirit is a trade mark by the [e-Spirit AG](http://www.e-spirit.com/).
Use this project and provided binaries at your own risk.

