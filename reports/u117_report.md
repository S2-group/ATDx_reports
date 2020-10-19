# ATDx Report Summary
Our ATDx analysis targets a portfolio of software projects and identifies the pain points of each project in terms of Architectural Technical Debt (ATD). This evaluation is based on a statistical analysis of the violations of SonarCloud rules.

[ATDx](https://robertoverdecchia.github.io/papers/ENASE_2020.pdf) provides an overview of the architectural technical debt in a project  in 6 distinct dimensions:
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
||||
|-|-|-|
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-resource.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-resource) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-resource) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-resource.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-models-impl.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-models-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-models-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-models-impl.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-pipes.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-pipes) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-pipes) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-pipes.json)</p>
 | |

# Project report summaries
## Project 1: _apache/sling-org-apache-sling-jcr-resource_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-resource.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-resource) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-resource) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-resource.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                               |
|:--------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-----------------------------------------------------------------------------------------|
| JcrResourceProvider.java  | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/jcr/resource/internal/helper/jcr/JcrResourceProvider.java |
| JcrResourceUtil.java      | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/jcr/resource/internal/helper/JcrResourceUtil.java         |
| JcrValueMap.java          | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/jcr/resource/internal/JcrValueMap.java                    |
| JcrResourceConstants.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/jcr/resource/api/JcrResourceConstants.java                |
| NodeUtil.java             | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/jcr/resource/internal/NodeUtil.java                       |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                        |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                        |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                        |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                        |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                        |

## Project 2: _apache/sling-org-apache-sling-models-impl_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-models-impl.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-models-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-models-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-models-impl.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name               | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                          |
|:-------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:--------------------------------------------------------------------|
| ModelAdapterFactory.java | 7              | 0             | 6           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/models/impl/ModelAdapterFactory.java |
| ExportServlet.java       | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/models/impl/ExportServlet.java       |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                   |

## Project 3: _apache/sling-org-apache-sling-pipes_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-pipes.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-pipes) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-pipes) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-pipes.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name             |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                           |
|:-----------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------|
| GogoCommands.java      |              7 |             0 |           1 |      0 |           0 |           0 |            6 | src/main/java/org/apache/sling/pipes/internal/GogoCommands.java      |
| JsonUtil.java          |              5 |             0 |           4 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/pipes/internal/JsonUtil.java          |
| PlumberImpl.java       |              4 |             0 |           4 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/internal/PlumberImpl.java       |
| MultiPropertyPipe.java |              4 |             0 |           2 |      0 |           0 |           0 |            2 | src/main/java/org/apache/sling/pipes/internal/MultiPropertyPipe.java |
| PipeBuilder.java       |              4 |             0 |           4 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/PipeBuilder.java                |
| CommandUtil.java       |              2 |             0 |           1 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/pipes/internal/CommandUtil.java       |
| SuperPipe.java         |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/SuperPipe.java                  |
| Plumber.java           |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/Plumber.java                    |
| Pipe.java              |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/Pipe.java                       |
| ReferencePipe.java     |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/pipes/internal/ReferencePipe.java     |

