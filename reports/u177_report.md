# ATDx Report Summary
Our ATDx analysis targets a portfolio of software projects and identifies the pain points of each project in terms of Architectural Technical Debt (ATD). This evaluation is based on a statistical analysis of the violations of SonarCloud rules.

ATDx provides an overview of the architectural technical debt in a project  in 6 distinct dimensions:
* **Inheritance**: flaws concerning inheritance mechanisms between classes, such as overrides and inheritance of methods or fields
* **Exception**: flaws regarding the management of Java exceptions and the subclassing of the “Exception” Java class.
* **JVMS**: potential misuses of the Java Virtual Machine, e.g., the incorrect usage of the specific Java class “Serializable”
* **Threading**: flaws arising from the implementation of multiple execution threads, which could potentially lead to concurrency problems
* **Interface**: flaws related to the usage of Java interfaces
* **Complexity**: flaws derived from prominent complexity measures, such as McCabe’s cyclomatic complexity

For each project, the dimensions assume a value between 0 and 5, where 0 denotes minimum architectural debt of the project in that dimension, and 5 maximum architectural debt.

In the reminder of this report, we firstly provide a set of radar charts (one for each project). Then for each project we give:
1. The same radar chart as shown at the beginning
2. A table showing the top-10 classes of the project with the highest architectural technical debt.

Note that if numerous classes with 1 violation are reported, this might point to a widespread problem (only a maximum of 10 classes are provided per project for the sake of readability). Similarly, empty rows indicate that only a few classes are affected by ATDx violations.

## Radar charts
|||
|-|-|
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_incubator-tamaya-extensions.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/incubator-tamaya-extensions) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-tamaya-extensions) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_incubator-tamaya-extensions.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_incubator-tamaya-sandbox.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/incubator-tamaya-sandbox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-tamaya-sandbox) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_incubator-tamaya-sandbox.json)</p>
# Project report summaries
## Project 1: _apache/incubator-tamaya-extensions_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_incubator-tamaya-extensions.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/incubator-tamaya-extensions) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-tamaya-extensions) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_incubator-tamaya-extensions.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                              |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                |
|:----------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------------------------|
| ConfigCommands.java                     |              7 |             0 |           7 |      0 |           0 |           0 |            0 | modules/osgi/common/src/main/java/org/apache/tamaya/osgi/commands/ConfigCommands.java                     |
| DefaultDynamicValue.java                |              5 |             4 |           0 |      0 |           1 |           0 |            0 | modules/injection/standalone/src/main/java/org/apache/tamaya/inject/internal/DefaultDynamicValue.java     |
| ConfigResources.java                    |              3 |             0 |           2 |      0 |           1 |           0 |            0 | modules/resources/src/main/java/org/apache/tamaya/resource/ConfigResources.java                           |
| Resolver.java                           |              3 |             0 |           0 |      0 |           3 |           0 |            0 | modules/resolver/src/main/java/org/apache/tamaya/resolver/Resolver.java                                   |
| ConfiguredFieldImpl.java                |              3 |             0 |           3 |      0 |           0 |           0 |            0 | modules/injection/standalone/src/main/java/org/apache/tamaya/inject/internal/ConfiguredFieldImpl.java     |
| BackupCommands.java                     |              3 |             0 |           3 |      0 |           0 |           0 |            0 | modules/osgi/common/src/main/java/org/apache/tamaya/osgi/commands/BackupCommands.java                     |
| ResourceResolver.java                   |              2 |             0 |           2 |      0 |           0 |           0 |            0 | modules/resources/src/main/java/org/apache/tamaya/resource/ResourceResolver.java                          |
| SpringConfigInjectionPostProcessor.java |              2 |             0 |           2 |      0 |           0 |           0 |            0 | modules/spring/src/main/java/org/apache/tamaya/integration/spring/SpringConfigInjectionPostProcessor.java |
| SettingsCommands.java                   |              2 |             0 |           2 |      0 |           0 |           0 |            0 | modules/osgi/gogo-shell/src/main/java/org/apache/tamaya/gogo/shell/SettingsCommands.java                  |
| HistoryCommands.java                    |              2 |             0 |           2 |      0 |           0 |           0 |            0 | modules/osgi/gogo-shell/src/main/java/org/apache/tamaya/gogo/shell/HistoryCommands.java                   |

## Project 2: _apache/incubator-tamaya-sandbox_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_incubator-tamaya-sandbox.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/incubator-tamaya-sandbox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-tamaya-sandbox) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_incubator-tamaya-sandbox.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                         | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                |
|:-----------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:----------------------------------------------------------------------------------------------------------|
| ResourcePropertySourceFactory.java | 2              | 2             | 0           | 0      | 0           | 0           | 0            | metamodel/src/main/java/org/apache/tamaya/metamodel/internal/factories/ResourcePropertySourceFactory.java |
| ConfiguredSystemProperties.java    | 2              | 2             | 0           | 0      | 0           | 0           | 0            | configured-sysprops/src/main/java/org/apache/tamaya/sysprops/ConfiguredSystemProperties.java              |
| HJSONPropertySource.java           | 1              | 1             | 0           | 0      | 0           | 0           | 0            | hjson/src/main/java/org/apache/tamaya/hjson/HJSONPropertySource.java                                      |
| JavaConfigSource.java              | 1              | 1             | 0           | 0      | 0           | 0           | 0            | configjsr/src/main/java/org/apache/tamaya/jsr382/JavaConfigSource.java                                    |
| BaseRemotePropertySource.java      | 1              | 1             | 0           | 0      | 0           | 0           | 0            | remote/src/main/java/org/apache/tamaya/remote/BaseRemotePropertySource.java                               |
| -                                  | -              | -             | -           | -      | -           | -           | -            | -                                                                                                         |
| -                                  | -              | -             | -           | -      | -           | -           | -            | -                                                                                                         |
| -                                  | -              | -             | -           | -      | -           | -           | -            | -                                                                                                         |
| -                                  | -              | -             | -           | -      | -           | -           | -            | -                                                                                                         |
| -                                  | -              | -             | -           | -      | -           | -           | -            | -                                                                                                         |

