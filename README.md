# grokconstructor

AVAILABLE ON {{}http://grokconstructor.appspot.com/

Grok is a collection of named regular expressions that can be used - for instance with logstash http://logstash.net/ -
to parse logfiles. GrokDiscovery http://grokdebug.herokuapp.com/ can somewhat help you by suggesting regular
expressions. GrokConstructor goes beyond that by finding many possible regular expressions
that match a whole set of logfile lines by using groks patterns and fixed strings. This can be done automatically
(which is of limited use only for small stuff), or in a incremental process.

## How to run it

### http://grokconstructor.appspot.com/

The best way is probably to use it on http://grokconstructor.appspot.com/ - 
there is also a good description, and you can use it on
some examples or for your own log lines you want to match.

### Appengine Devserver, started from maven

To run locally, build with
mvn clean install
and start with
mvn appengine:devserver
. It runs on http://localhost:9090/ .

### Deploy as a WAR

If you want to run it on a system without internet connection or that has an application server, anyway,
you can also deploy the created target/GrokConstructor-*-SNAPSHOT.war e.g. on a Tomcat.

### Standalone Executable

java -jar GrokConstructor-0.1.0-SNAPSHOT-standalone.jar

runs an embedded Tomcat that makes it available at http://localhost:8080/ .
Please be aware that this creates a directory .extract in the current directory that contains the 
unpacked webapp. You can print additional arguments (such as ports, unpack location) with

java -jar GrokConstructor-0.1.0-SNAPSHOT-standalone.jar -h

### Run & Debug Executable With Eclipse

mvn tomcat6:run
