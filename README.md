# bodgeit-maven

This is a sample project to get started with the zap-maven-plugin 1.2 and ZAproxy 2.4.2.

## Usage
You first have to build it without tests:

  mvn clean install -DskipTests -DskipITs

You can deploy it to your server, but under the /thebodgeitstore/ context. Or you can run it using:

  mvn jetty:run
  
Then you adapt the pom.xml for the tests. If a new Firefox is used, you probably have to update the selenium dependency to the latest version.
You need also adapt the location where the plugin has to find the ZAProxy batch file or shell file under the <zapProgram>-tag

Then you can run the maven verify to perform the tests:

  mvn verify
