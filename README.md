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
4. Run your application via Maven (for instance):
   ```bash
   mvn exec:exec
   ```
5. Run your application via the jar you generate (for instance)
   ```
   java -jar app.jar
   ```
6. Generate documentation for your project:
   ```bash
   mvn javadoc:javadoc
   ```    

Remember to work together. Do not delegate everything to one member of the group!

## 1. Mandatory setup

Follow the list below to set up ba 

### 1.1. Maven's Standard Directory Layout

Reorganize your project such that it complies with [Maven's standard directory layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html).

```txt
/
|   pom.xml
|   README.md
|   LICENSE
|   .gitignore
+---src/
|   +---main/
|   |       +---java/
|   |       +---resources/
|   +---test/
|   |       +---java/
|   |       +---resources/
```

Remember to edit your:
- `.gitignore` file to ignore files generated in your build. 
- `README.md` file to include all instructions one needs to build, test, and run your project.

### 1.2. Configure your `pom.xml`

1. Create your `pom.xml` file
2. Add your project's coordinates: `groupId`, `artifactId`, `version`
3. Configure the Java version you are using
4. Configure the standard file encoding
5. Add dependencies required in your project

### 1.3. Testing environment

1. Add JUnit 5 as a test dependency
2. Configure the Apache Maven Surefire Plugin (at least version 2.22.0)

### 1.4. Packaging your project

Package your project as a fat runnable jar.

Common plugins used to configure how your project is packaged are:
- [Apache Maven Jar Plugin](https://maven.apache.org/plugins/maven-jar-plugin/)
- [Apache Maven Shade Plugin](https://maven.apache.org/plugins/maven-shade-plugin/index.html)
- [Apache Maven Assembly Plugin](http://maven.apache.org/plugins/maven-assembly-plugin/)

You can read the articles below to decide which plugin to use:
- https://medium.com/@randilfernando/when-to-use-maven-jar-maven-assembly-or-maven-shade-ffc3f76ba7a6
- https://www.baeldung.com/executable-jar-with-maven

### 1.5. Running your project

Running your `.jar` should be as simple as:

```bash
java -jar myapp.jar
```

To run your app via Maven, you should configure the [Exec Maven Plugin](https://www.mojohaus.org/exec-maven-plugin/).

This should allow you to run your project using:

```bash
mvn exec:exec
```

or

```bash
mvn exec:java
```

### 1.6. Code Documentation

Configure the [Apache Maven Javadoc Plugin](https://maven.apache.org/plugins/maven-javadoc-plugin/) in your project.

## 2. Recommended additional setup

In addition to the aforementioned setup, you may also want to configure the following plugins:

1. Configure the [Apache Maven Clean Plugin](https://maven.apache.org/plugins/maven-clean-plugin/) to remove additional files you created during build, test, and execution.

2. Configure the JaCoCo Maven Plugin to generate a test coverage report whenever you run your unit tests.
    - [JaCoCo](https://www.eclemma.org/jacoco/)
    - [Plugin](https://www.eclemma.org/jacoco/trunk/doc/maven.html)
    - Tutorials
        - https://mkyong.com/maven/maven-jacoco-code-coverage-example/
        - https://www.baeldung.com/jacoco

3. Configure [Maven Wrapper](https://github.com/takari/maven-wrapper) so others can build your project without installing Maven on their machines.

## 3. Optional setup: OS-specific artifact generation

For Windows:
- [launch4j](http://launch4j.sourceforge.net/)
- [launch4j Maven Plugin](https://github.com/lukaszlenart/launch4j-maven-plugin)

For macOS:
- [AppBundle Maven Plugin](https://github.com/federkasten/appbundle-maven-plugin)

For Debian and Ubuntu:
- [Debian Maven Plugin:](http://debian-maven.sourceforge.net/)

Multi-platform:
- [Mojo Codehaus Appassembler Plugin](https://www.mojohaus.org/appassembler/)

## 4. Optional setup: Code formatters

Google Java Style:
- https://google.github.io/styleguide/javaguide.html
- https://github.com/google/google-java-format#third-party-integrations

Plugins to automatically format your code:
- [Formatter Maven Plugin](https://code.revelc.net/formatter-maven-plugin/)
- [Spotless Maven Plugin](https://github.com/diffplug/spotless)
- [FMT Maven Plugin](https://github.com/coveooss/fmt-maven-plugin)

## 5. Optional setup: Static code analyzers

You can use a plugins to automatically analyze your code.

- [Apache Maven Checkstyle Plugin](https://maven.apache.org/plugins/maven-checkstyle-plugin/):
  - [Checkstyle](https://checkstyle.org/) 
  
- [Apache Maven PMD Plugin](https://maven.apache.org/plugins/maven-pmd-plugin/):
  - [PMD](https://pmd.github.io/)

- [FindBugs Maven Plugin](https://www.mojohaus.org/findbugs-maven-plugin/): 
  - [FindBugs](http://findbugs.sourceforge.net/)