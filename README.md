# testproject-byok2

A Gradle-based Java project with SonarQube integration and logging support.

## Features

- **Java 17** - Modern Java development
- **Gradle 9.3.0** - Build automation and dependency management
- **SonarQube Plugin** - Code quality and security analysis
- **Logging** - SLF4J API with Logback implementation
- **JUnit 5** - Unit testing framework

## Project Structure

```
testproject-byok2/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/example/testproject/
│   │   │   │       └── App.java
│   │   │   └── resources/
│   │   │       └── logback.xml
│   │   └── test/
│   │       └── java/
│   │           └── com/example/testproject/
│   │               └── AppTest.java
│   └── build.gradle
├── gradle/
│   └── wrapper/
├── settings.gradle
└── README.md
```

## Prerequisites

- Java 17 or higher
- No need to install Gradle - the Gradle wrapper is included

## Building the Project

```bash
./gradlew build
```

This command will:
- Compile the source code
- Run all tests
- Package the application

## Running the Application

```bash
./gradlew run
```

## Running Tests

```bash
./gradlew test
```

## SonarQube Analysis

The project is configured with the SonarQube plugin for code quality analysis.

### Configuration

The SonarQube configuration is in `app/build.gradle`:
- Project Key: `testproject-byok2`
- Project Name: `Test Project BYOK2`
- Host URL: `http://localhost:9000` (default SonarQube server)

### Running Analysis

To run SonarQube analysis (requires a running SonarQube server):

```bash
./gradlew sonar
```

For custom SonarQube server or authentication:

```bash
./gradlew sonar \
  -Dsonar.host.url=https://your-sonarqube-server.com \
  -Dsonar.login=your-token
```

## Logging

The project uses SLF4J with Logback for logging.

### Configuration

Logging is configured in `app/src/main/resources/logback.xml`:
- **Console Appender**: Logs to console
- **File Appender**: Logs to `logs/application.log` with daily rotation
- **Root Level**: INFO
- **Application Level**: DEBUG for `com.example.testproject` package

### Log Format

```
yyyy-MM-dd HH:mm:ss.SSS [thread] LEVEL logger - message
```

### Using Logging in Code

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class MyClass {
    private static final Logger logger = LoggerFactory.getLogger(MyClass.class);
    
    public void myMethod() {
        logger.debug("Debug message");
        logger.info("Info message");
        logger.warn("Warning message");
        logger.error("Error message");
    }
}
```

## Dependencies

- **Guava** - Google's core libraries for Java
- **SLF4J API 2.0.9** - Logging facade
- **Logback Classic 1.4.14** - Logging implementation
- **JUnit Jupiter** - Testing framework

## Gradle Tasks

Common tasks:
- `./gradlew build` - Build the project
- `./gradlew test` - Run tests
- `./gradlew run` - Run the application
- `./gradlew clean` - Clean build artifacts
- `./gradlew sonar` - Run SonarQube analysis
- `./gradlew tasks` - List all available tasks

## License

This is a test project for demonstration purposes.
