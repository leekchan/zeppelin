#Zeppelin 

**Documentation:** [User Guide](http://zeppelin-project.org/docs/index.html)<br/>
**Mailing List:** [User and Dev mailing list](http://zeppelin.incubator.apache.org/community.html)<br/>
**Continuous Integration:** [![Build Status](https://secure.travis-ci.org/NFLabs/zeppelin.png?branch=master)](https://travis-ci.org/NFLabs/zeppelin) <br/>
**Contributing:** [Contribution Guide](https://github.com/NFLabs/zeppelin/blob/master/CONTRIBUTING.md)<br/>
**License:** [Apache 2.0](https://github.com/NFLabs/zeppelin/blob/master/LICENSE)


**Zeppelin**, a web-based notebook that enables interactive data analytics. You can make beautiful data-driven, interactive and collaborative documents with SQL, Scala and more.

Core feature:
   * Web based notebook style editor.
   * Built-in Apache Spark support


To know more about Zeppelin, visit our web site [http://zeppelin-project.org](http://zeppelin-project.org) 

## Requirements
 * Java 1.7
 * Tested on Mac OSX, Ubuntu 14.X, CentOS 6.X
 * Maven (if you want to build from the source code)
 * Node.js Package Manager

## Getting Started

### Before Build
If you don't have requirements prepared, install it. 
(The installation method may vary according to your environment, example is for Ubuntu.)
```
sudo apt-get update
sudo apt-get install openjdk-7-jdk
sudo apt-get install git
sudo apt-get install maven
sudo apt-get install npm
```

### Build
If you want to build Zeppelin from the source, please first clone this repository. And then:
```
mvn clean package
```
Build with specific version

Spark 1.1.x (more stable with Zeppelin for this moment.)
```
mvn clean package -Pspark-1.1 -Dhadoop.version=2.2.0 -Phadoop-2.2 -DskipTests 
```
Spark 1.2.x
```
mvn clean package -Pspark-1.2 -Dhadoop.version=2.2.0 -Phadoop-2.2 -DskipTests 
```

### Configure
If you wish to configure Zeppelin option (like port number), configure the following files:
```
./conf/zeppelin-env.sh
./conf/zeppelin-site.xml
```
(You can copy ```./conf/zeppelin-env.sh.template``` into ```./conf/zeppelin-env.sh```. 
Same for ```zeppein-site.xml```.)

### Run
    ./bin/zeppelin-daemon.sh start

    browse localhost:8080 in your browser. 8081 port should be accessible for websocket connection.


For configuration details check __./conf__ subdirectory.

### Package
To package final distribution do:

      mvn clean package -P build-distr

The archive is generated under _zeppelin-distribution/target_ directory

###Run end-to-end tests
Zeppelin comes with a set of end-to-end acceptnce tests driving headless selenium browser

      #assumes zeppelin-server running on localhost:8080 (use -Durl=.. to override)
      mvn verify

      #or take care of starting\stoping zeppelin-server from packaged _zeppelin-distribuion/target_
      mvn verify -P using-packaged-distr


[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/10ba60fb64e53bb1ccd0bab47abbcc4a "githalytics.com")](http://githalytics.com/NFLabs/zeppelin)



