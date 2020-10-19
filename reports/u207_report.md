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
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache-dolphinscheduler.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/incubator-dolphinscheduler) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache-dolphinscheduler) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache-dolphinscheduler.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_isis.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/isis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_isis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_isis.json)</p>
# Project report summaries
## Project 1: _apache/incubator-dolphinscheduler_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache-dolphinscheduler.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/incubator-dolphinscheduler) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache-dolphinscheduler) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache-dolphinscheduler.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                    |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                      |
|:------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------------------------------|
| UpgradeDao.java               |             18 |             0 |          18 |      0 |           0 |           0 |            0 | dolphinscheduler-dao/src/main/java/org/apache/dolphinscheduler/dao/upgrade/UpgradeDao.java                      |
| ResourcesService.java         |             12 |             0 |          11 |      0 |           1 |           0 |            0 | dolphinscheduler-api/src/main/java/org/apache/dolphinscheduler/api/service/ResourcesService.java                |
| SchedulerService.java         |             11 |             0 |           6 |      0 |           2 |           0 |            3 | dolphinscheduler-api/src/main/java/org/apache/dolphinscheduler/api/service/SchedulerService.java                |
| SSHTask.java                  |             10 |             0 |          10 |      0 |           0 |           0 |            0 | dolphinscheduler-server/src/main/java/org/apache/dolphinscheduler/server/worker/task/ssh/SSHTask.java           |
| UsersService.java             |              7 |             0 |           5 |      0 |           2 |           0 |            0 | dolphinscheduler-api/src/main/java/org/apache/dolphinscheduler/api/service/UsersService.java                    |
| SqlTask.java                  |              7 |             0 |           7 |      0 |           0 |           0 |            0 | dolphinscheduler-server/src/main/java/org/apache/dolphinscheduler/server/worker/task/sql/SqlTask.java           |
| DataxTask.java                |              7 |             0 |           7 |      0 |           0 |           0 |            0 | dolphinscheduler-server/src/main/java/org/apache/dolphinscheduler/server/worker/task/datax/DataxTask.java       |
| ProcessImplForWin32.java      |              7 |             1 |           6 |      0 |           0 |           0 |            0 | dolphinscheduler-common/src/main/java/org/apache/dolphinscheduler/common/utils/process/ProcessImplForWin32.java |
| ExecutorService.java          |              6 |             0 |           4 |      0 |           2 |           0 |            0 | dolphinscheduler-api/src/main/java/org/apache/dolphinscheduler/api/service/ExecutorService.java                 |
| ProcessDefinitionService.java |              6 |             0 |           5 |      0 |           1 |           0 |            0 | dolphinscheduler-api/src/main/java/org/apache/dolphinscheduler/api/service/ProcessDefinitionService.java        |

## Project 2: _apache/isis_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_isis.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/isis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_isis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_isis.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                         |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                                                |
|:-----------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:------------------------------------------------------------------------------------------------------------------------------------------|
| CommonDtoUtils.java                |             29 |             0 |           1 |      0 |           1 |           0 |           27 | api/applib/src/main/java/org/apache/isis/applib/util/schema/CommonDtoUtils.java                                                           |
| IsisConfiguration.java             |             26 |             0 |           0 |      0 |          26 |           0 |            0 | core/config/src/main/java/org/apache/isis/core/config/IsisConfiguration.java                                                              |
| PojoTester.java                    |             21 |            21 |           0 |      0 |           0 |           0 |            0 | testing/unittestsupport/applib/src/main/java/org/apache/isis/testing/unittestsupport/applib/bean/PojoTester.java                          |
| _Json.java                         |             17 |             0 |          16 |      0 |           1 |           0 |            0 | core/commons/src/main/java/org/apache/isis/core/commons/internal/resources/_Json.java                                                     |
| ExcelService.java                  |             16 |             0 |          16 |      0 |           0 |           0 |            0 | subdomains/excel/applib/src/main/java/org/apache/isis/subdomains/excel/applib/dom/ExcelService.java                                       |
| ValueTypeContractTestAbstract.java |             12 |             0 |          12 |      0 |           0 |           0 |            0 | core/internaltestsupport/src/main/java/org/apache/isis/core/internaltestsupport/value/ValueTypeContractTestAbstract.java                  |
| ValueTypeContractTestAbstract.java |             12 |             0 |          12 |      0 |           0 |           0 |            0 | testing/unittestsupport/applib/src/main/java/org/apache/isis/testing/unittestsupport/applib/core/value/ValueTypeContractTestAbstract.java |
| JsonMapper.java                    |              9 |             0 |           9 |      0 |           0 |           0 |            0 | viewers/restfulobjects/applib/src/main/java/org/apache/isis/viewer/restfulobjects/applib/util/JsonMapper.java                             |
| Parent.java                        |              8 |             0 |           8 |      0 |           0 |           0 |            0 | testing/unittestsupport/applib/src/main/java/org/apache/isis/testing/unittestsupport/applib/core/bidir/Parent.java                        |
| DomainEventHelper.java             |              7 |             0 |           6 |      0 |           1 |           0 |            0 | core/metamodel/src/main/java/org/apache/isis/core/metamodel/facets/DomainEventHelper.java                                                 |

