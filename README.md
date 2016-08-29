# FSM Library Creator [![Build Status](https://travis-ci.org/zaplatynski/fsm-library-creator.svg?branch=master)](https://travis-ci.org/zaplatynski/fsm-library-creator)

The FSM Library Creator is a small but useful application of the [FSM Maven Packagetype](https://github.com/zaplatynski/fsm-packagetype). It can be used to provide Library-FSMs such as JDBC drivers or web liberies like JSTL to the FirstSpirit CMS. See the [FirstSpirit Module Developer Manual (German only)](http://www.e-spirit.com/odfs52/dokumentation/fuer-entwickler/MDEV_DE_FirstSpirit_ModuleDeveloper.pdf), section 3.15 and 3.16 for detailed information.

There are predefined working Maven profiles for
- PostgreSQL JDBC driver,
- MySQL JDBC driver,
- HyperSQL JDBC driver,
- SQLite JDBC driver,
- DerbyDB JDBC driver and for the
- JSTL (for Apache Tomcat).

*Microsoft SQL* server and *Oracle DB* are special cases. For Oracle DB please read their [blog about how to get a JDBC driver](https://blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc).

But this is not limited to the examples above. Any library which should be public avaialable for FirstSpirit CMS can add a new profile.
```
<profile>
    <id>name</id>
    <properties>
        <lib.groupId>maven.groupId</lib.groupId>
        <lib.artifactId>maven.artifactId</lib.artifactId>
        <lib.version>maven.version</lib.version>
        <lib.displayName>Short name</lib.displayName>
        <lib.description>Long name</lib.description>
        <lib.vendor>vendor name</lib.vendor>
        <lib.module>MODULE_XML</lib.module>
    </properties>
</profile>
```
For `MODULE_XML` you can choose bewteen two predefined `module.xml` files:
- `module_all.xml` specifies the library both for web and server wiede usage and
- `module_web.xml` only specifies the library for web usage.

Please send me a pull request if you think others might benefit too so.

## Bugs and feature requests

Please file any **bug** or **feature request** here at [github.com/zaplatynski/fsm-library-creator/issues](https://github.com/zaplatynski/fsm-library-creator/issues). Thanks!
 
## Build

[Maven](http://maven.apache.org/) is used to assemble the FirstSpirit module (FSM):
```
mvn clean package -p postgres
```
The example above will create the FSM for the PostgreSQL JDBC Driver. Please specify only one Maven profile at a time since every profile contains the information need to assemble the requested FSM.

##  Disclaimer

By using it you agree to the license stated in the file [LICENSE](LICENSE). The JDBC drivers are respective property of the DBMS vendors. FirstSpirit is a trade mark by the [e-Spirit AG](http://www.e-spirit.com/).
Use this project and provided binaries at your own risk.

