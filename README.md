# FSM Library Creator [![Build Status](https://travis-ci.org/zaplatynski/fsm-library-creator.svg?branch=master)](https://travis-ci.org/zaplatynski/fsm-library-creator)

The FistSpirit Module Library Creator is a small but useful application of the [FSM Maven Packagetype](https://github.com/zaplatynski/fsm-packagetype). It can be used to provide Library-FSMs such as JDBC drivers or web libaries like JSTL to the FirstSpirit CMS. See the [FirstSpirit Module Developer Manual (German only)](http://www.e-spirit.com/odfs52/dokumentation/fuer-entwickler/MDEV_DE_FirstSpirit_ModuleDeveloper.pdf), section 3.15 and 3.16 for detailed information.

There are predefined working [Maven profiles](pom.xml) for
- PostgreSQL JDBC driver,
- MySQL JDBC driver,
- HyperSQL JDBC driver,
- SQLite JDBC driver,
- DerbyDB JDBC driver and for the
- JSTL (for Apache Tomcat).

*Microsoft SQL* server and *Oracle DB* are special cases. For Oracle DB please read their [blog about how to get a JDBC driver](https://blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc).

But this is not limited to the examples above. Any library which should be public avaialable for FirstSpirit CMS can add a new profile in the pom's profile section like this:
```
<profile>
    <id>name</id>
    <properties>
        <lib.groupId>maven.groupId</lib.groupId>
        <lib.artifactId>maven.artifactId</lib.artifactId>
        <lib.use.version>maven.version</lib.use.version>
        <lib.displayName>Short name</lib.displayName>
        <lib.description>Long name</lib.description>
        <lib.vendor>vendor name</lib.vendor>
        <lib.module>MODULE_XML</lib.module>
    </properties>
</profile>
```
For `MODULE_XML` you can choose bewteen two predefined `module.xml` files:
- [`module_all.xml`](src/main/resources/module_all.xml) specifies the library both for web and server wiede usage and
- [`module_web.xml`](src/main/resources/module_web.xml) only specifies the library for web usage.

Please send me a pull request if you think others might benefit from your profile too.

## FirstSpirit and Java compatibility

The created library FSMs should be compatibel with FirstSpirit 5.1 and later (this is not tested in detail). Since the incorporate library JARs are third party it depends with which Java target version they are created. Please check the respective vendor for details about the Java compatibility. In general it is recommended to use the latest stable Java version as runtime.

## Bugs and feature requests

Please file any **bug** or **feature request** here at [github.com/zaplatynski/fsm-library-creator/issues](https://github.com/zaplatynski/fsm-library-creator/issues). Thanks!
 
## Build

[Maven](http://maven.apache.org/) is used to assemble the FirstSpirit module (FSM):
```
mvn clean package -p postgres
```
The example above will create the FSM for the PostgreSQL JDBC Driver. Please specify only one Maven profile at a time since every profile contains enough information needed to assemble the requested FSM.
You can bypass the version. So, for instance, to get the Postgres diver not in version 9.4.1209 (the predefined version in the `postgres` profile) but in version 9.2-1002-jdbc4 just call Maven with an additional command line parameter:
```
mvn clean package -p postgres -Dlib.version=9.2-1002-jdbc4
```
The version string must match the versions available in Maven central or the user configured repository.

##  Disclaimer

By using it you agree to the license stated in the file [LICENSE](LICENSE). The JDBC drivers are respective property of the DBMS vendors. FirstSpirit is a trade mark by the [e-Spirit AG](http://www.e-spirit.com/).
Use this project and provided binaries at your own risk.
