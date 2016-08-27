# FSM Library Creater

The FSM Library Creator is a small but useful apllication of the [FSM Maven Packagetype](https://github.com/zaplatynski/fsm-packagetype). It can be used to provide Library-FSMs such as JDBC drivers to the FirstSpirit CMS. 

## Bugs and feature requests

Please file any **bug** or **feature request** here at [github.com/zaplatynski/fsm-library-creater/issues](https://github.com/zaplatynski/fsm-library-creater/issues). Thanks!
 
## Build

[Maven](http://maven.apache.org/) is used to assemble the FirstSpirit module (FSM):
```
mvn clean package -p postgres
```
The example above will create the FSM for the PostgreSQL JDBC Driver.

##  Disclaimer

By using it you agree to the license stated in the file [LICENSE](LICENSE). FirstSpirit is a trade mark by the [e-Spirit AG](http://www.e-spirit.com/).
Use this project and provided binaries at your own risk.

