# Gradle Build Templates

Provides quick bootstrap scripts for spring-boot, spring-modules/jar which includes common plugins/capabilities used across microservices.
Versions can be managed by the services which imports the scripts. Additional configurations for the plugins can be applied by the DSL related to the plugins.

## How to use the common scripts

Add the following snippet to `build.gradle` to include build script configuration - TBD (move to plugin management)
```
buildscript { 
	apply from: "https://raw.githubusercontent.com/<account>/gradle-build-templates/master/gradle-common/init-buildscript.gradle", to: buildscript
}
```

### Spring boot
Enable spring boot bootstrap configurations by applying configuration
```
apply from: 'https://raw.githubusercontent.com/<account>/gradle-build-templates/master/spring-boot/spring-rest-jumpstart.gradle'
```

### Spring JAR
Enable spring jar bootstrap configurations by applying configuration
```
apply from: 'https://raw.githubusercontent.com/<account>/gradle-build-templates/master/spring-library/spring-jar-jumpstart.gradle'
```

## Supported common plugins

- java
- groovy
- scala
- idea
- maven
- gradle-lombok
- sonarqube
- scala
- checkstyle
- pmd
- jacoco
- spotbugs
- lombok

## Support highlevel common scripts/tasks

- code quality
- docker
- packaging
- datadog
- integration tests
- performance tests
- semantic release

## Configurable gradle properties

| Property Name                         | Dependency/Plugin     | Default                   |
|---------------------------------------|-----------------------|---------------------------|
| `localSpringProfile`                  | Spring                | local                     |
| `gradleTemplatesSource`               | gradle                |                           |
| `codeQualityResources`                | plugins               |                           |
| `integrationTestSpringProfile`        | spring                | integrationTest           |
| `integrationTestSourceRoot`           | gradle                | src/integration-test      |
| `performanceTestSourceRoot`           | gradle                | src/perf-test             |

| Property Name                         | Dependency/Plugin     | Default                   |
|---------------------------------------|-----------------------|---------------------------|
| `springCloudVersion`                  | Spring                | Hoxton.SR3	            |
| `scalaVersion`                        | scala                 | 2.13.1                    |
| `gatlingVersion`                      | gatling               | 3.3.1                     |
| `checkStyleVersion`                   | checkstyle            | 8.17                      |
| `pmdVersion`                          | pmd                   | 6.21.0                    |
| `jacocoVersion`                       | jacoco                | 0.8.5                     |
| `spotBugsVersion`                     | spotBugs              | 3.1.11                    |

## Spring jar gradle bootstrap

Provides quick bootstrap scripts for a spring library which helps building, packaging and containerzing spring library projects.

* Supported plugins

- Java jar

## Semantic versioning

Given a version number MAJOR.MINOR.PATCH, increment the:

MAJOR version when you make incompatible API changes,
MINOR version when you add functionality in a backwards compatible manner, and
PATCH version when you make backwards compatible bug fixes.
Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

source: https://semver.org/
