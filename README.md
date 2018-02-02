# Richkware-Manager-Server
[![Build Status](https://travis-ci.org/richkmeli/Richkware-Manager-Server.svg?branch=master)](https://travis-ci.org/richkmeli/Richkware-Manager-Server)

Service for management of hosts where is present a malware developed using **Richkware** framework.

 <img src="http://richk.altervista.org/rms.png">

## Implementation

RMS has been developed following the REST principles; the following table shows which HTTP methods have been used for each servlet.

|  HTTP methods  | GET | POST | PUT | DELETE |
|--------------|:----:|:---:|:---:|:------:|
| device | x | | x | x |
| user | x | | | x |
| deviceList | x | | | x |
| userList | x | | | |
| encryptionKey | x | | | |


## Related Projects

[Richkware](https://github.com/richkmeli/Richkware): Framework for building Windows malware.

[Richkware-Manager-Client](https://github.com/richkmeli/Richkware-Manager-Client): Client of **Richkware-Manager-Server**, that obtains list of all hosts and is able to send commands to do at each of them.

![](http://richk.altervista.org/RichkwareDiagram.svg)

## Requirements
These are the base requirements to build and use Richkware:

-   Java 1.5 or higher
-   MySQL

## Get Started

Open the configuration file (/src/main/resources/configuration.properties) and set the parameters inside it. In particular:

- __database.url__: address of the database, RMS supports MySQL, if you want to use another one, it may not work. (default: jdbc:mysql://db:3306/)
- __database.username__: username used to access to the database (default: root)
- __database.password__: password used to access to the database (default: richk)
- __encryptionkey__: encryption key used to exchange message to Richkware and RMC. if you change this parameter, remember to change also the configurations in Richkware and RMC (default: richktest)

After that, you can deploy RMS using __docker-compose__.

    docker-compose up