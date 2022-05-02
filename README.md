# Maven Lab

This **goal of this lab** is for you to set up Maven completely for your project. 

You should commit to this repository the current source code of your project, including the Maven setup, and show that you can:
1. Compile your application:
   ```bash
   mvn compile
   ```
2. Run your unit tests:
   ```bash
   mvn test
   ```
3. Package your project:
   ```bash
   mvn package
   ```
4. Run your application:
   ```bash
   mvn exec:exec
   ```
   or
   ```
   java -jar app.jar
   ```
5. Generate documentation for your project:
   ```bash
   mvn javadoc:javadoc
   ```    

Remember to work together. Do not delegate everything to one member of the group!

## 1. Mandatory setup

Follow the list below to set up ba 

1. Adopt Maven's standard directory layout
2. Create your `pom.xml` file
3. Add your project's coordinates: `groupId`, `artifactId`, `version`
4. Configure the Java version you are using
5. Configure the standard file encoding
6. Add JUnit 5 as a test dependency
7. Configure the Apache Maven Surefire Plugin (at least version 2.22.0)
8. Add other dependencies required for your project
9. Configure how your project is packaged
10. Decide how to run your project (you should run your packaged jar)
11. Configure the Apache Maven Javadoc Plugin in your project
12. Edit your `.gitignore` file to ignore files generated in your build
13. Edit your `README.md` file to include all instructions one needs to build, test, and run your project.

## 2. Packaging your project

You can package your project as:
- Thin jar: contains only your app's code
- Fat jar: your app's code and its dependencies
- A runnable jar (also known as an *uber jar*)

Common plugins used to configure how your project is packaged are:
- [Apache Maven Jar Plugin](https://maven.apache.org/plugins/maven-jar-plugin/)
- [Apache Maven Shade Plugin](https://maven.apache.org/plugins/maven-shade-plugin/index.html)
- [Apache Maven Assembly Plugin](http://maven.apache.org/plugins/maven-assembly-plugin/)

You can read the articles below to decide which plugin to use:
- https://medium.com/@randilfernando/when-to-use-maven-jar-maven-assembly-or-maven-shade-ffc3f76ba7a6
- https://www.baeldung.com/executable-jar-with-maven

## 3. Running your project

If you built an uber jar, running your project should be as simple as:

```bash
java -jar myapp.jar
```

Alternatively, you can configure the [Exec Maven Plugin](https://www.mojohaus.org/exec-maven-plugin/):

## 4. Testing your setup

1. **`mvn clean`**: should clean your project
2. **`mvn test`**: should run your unit tests
3. **`mvn package`**: should generate an executable jar for your project
4. **`mvn javadoc:javadoc`**: should generate the documentation for your project

## 5. Recommended additional setup

1. Configure the [Apache Maven Clean Plugin](https://maven.apache.org/plugins/maven-clean-plugin/) to remove additional files you created during build, test, and execution.

2. Configure the JaCoCo Maven Plugin to generate a test coverage report whenever you run your unit tests.
    - [JaCoCo](https://www.eclemma.org/jacoco/)
    - [Plugin](https://www.eclemma.org/jacoco/trunk/doc/maven.html)
    - Tutorials
        - https://mkyong.com/maven/maven-jacoco-code-coverage-example/
        - https://www.baeldung.com/jacoco

3. Configure Maven Wrapper so others can build your project without installing maven on their machines:
    - https://github.com/takari/maven-wrapper

## Optional setup: OS-specific artifact generation

For Windows:
- [launch4j](http://launch4j.sourceforge.net/)
- [launch4j Maven Plugin](https://github.com/lukaszlenart/launch4j-maven-plugin)

For macOS:
- [AppBundle Maven Plugin](https://github.com/federkasten/appbundle-maven-plugin)

For Debian and Ubuntu:
- [Debian Maven Plugin:](http://debian-maven.sourceforge.net/)

Multi-platform:
- [Mojo Codehaus Appassembler Plugin](https://www.mojohaus.org/appassembler/)

## Optional setup: Code formatters

Google Java Style:
- https://google.github.io/styleguide/javaguide.html
- https://github.com/google/google-java-format#third-party-integrations

Plugins to automatically format your code:
- [Formatter Maven Plugin](https://code.revelc.net/formatter-maven-plugin/)
- [Spotless Maven Plugin](https://github.com/diffplug/spotless)
- [FMT Maven Plugin](https://github.com/coveooss/fmt-maven-plugin)

## Optional setup: Static code analyzers

You can use a plugins to automatically analyze your code.

- Apache Maven Checkstyle Plugin:
  - Checkstyle: https://checkstyle.org/
  - Plugin: https://maven.apache.org/plugins/maven-checkstyle-plugin/

- Apache Maven PMD Plugin:
  - PMD: https://pmd.github.io/
  - Plugin: https://maven.apache.org/plugins/maven-pmd-plugin/

- FindBugs Maven Plugin: 
  - FindBugs: http://findbugs.sourceforge.net/
  - Plugin: https://www.mojohaus.org/findbugs-maven-plugin/