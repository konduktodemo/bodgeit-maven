# bodgeit-maven

This is a sample project to get started with the zap-maven-plugin 1.2 and ZAproxy 2.4.2. It is a sample web application which has selenium tests, which are executed during the test-phase of maven. It reuses the same selenium tests to feed the zap-proxy application with all links. The zap-maven-plugin will start the ZAProxy application and stop it after the tests. The zap-maven-plugin will create a site (in the src/site/resources/zaproxy directory) so it can be shown using mvn site:run.

## Usage
You first have to build it without tests:

  mvn clean install -DskipTests -DskipITs

You can deploy it to your server, but under the /thebodgeitstore/ context. Or you can run it using:

  mvn jetty:run
  
You open a second terminal and adapt the pom.xml for the tests. If a very new Firefox is used, you probably have to update the selenium dependency to the latest version.
You need also adapt the location where the plugin has to find the ZAProxy batch file or shell file under the &lt;zapProgram&gt;-tag

Then you can run the maven verify to perform the tests:

  mvn verify

Good Luck and Develop Secure Web applications.

## Releasing bodgeit project
Releasing uses jgitflow plugin and a prayer-book

mvn jgitflow:release-start

mvn jgitflow:release-finish -DskipTests -DskipITs -DneDeploy=true
