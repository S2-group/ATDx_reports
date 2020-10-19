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
||||
|-|-|-|
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_incubator-ratis.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/incubator-ratis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-ratis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_incubator-ratis.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_isis.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/isis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_isis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_isis.json)</p>|<p align="center">Project 3</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/servicecomb-toolkit.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/servicecomb-toolkit) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=servicecomb-toolkit) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/servicecomb-toolkit.json)</p>
 | |

# Project report summaries
## Project 1: _apache/incubator-ratis_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_incubator-ratis.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/incubator-ratis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-ratis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_incubator-ratis.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name            |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                              |
|:----------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------|
| NativeIO.java         |             40 |             3 |           1 |      0 |          36 |           0 |            0 | ratis-common/src/main/java/org/apache/ratis/io/nativeio/NativeIO.java                   |
| VerificationTool.java |              6 |             0 |           6 |      0 |           0 |           0 |            0 | ratis-logservice/src/main/java/org/apache/ratis/logservice/tool/VerificationTool.java   |
| RaftProperties.java   |              6 |             0 |           6 |      0 |           0 |           0 |            0 | ratis-common/src/main/java/org/apache/ratis/conf/RaftProperties.java                    |
| MetaStateMachine.java |              5 |             5 |           0 |      0 |           0 |           0 |            0 | ratis-logservice/src/main/java/org/apache/ratis/logservice/server/MetaStateMachine.java |
| NativeCrc32.java      |              5 |             0 |           2 |      0 |           3 |           0 |            0 | ratis-common/src/main/java/org/apache/ratis/util/NativeCrc32.java                       |
| ServerProtoUtils.java |              3 |             0 |           0 |      0 |           3 |           0 |            0 | ratis-server/src/main/java/org/apache/ratis/server/impl/ServerProtoUtils.java           |
| LogServiceClient.java |              3 |             0 |           3 |      0 |           0 |           0 |            0 | ratis-logservice/src/main/java/org/apache/ratis/logservice/api/LogServiceClient.java    |
| LogStateMachine.java  |              3 |             0 |           3 |      0 |           0 |           0 |            0 | ratis-logservice/src/main/java/org/apache/ratis/logservice/server/LogStateMachine.java  |
| LogAppender.java      |              3 |             0 |           3 |      0 |           0 |           0 |            0 | ratis-server/src/main/java/org/apache/ratis/server/impl/LogAppender.java                |
| NetUtils.java         |              2 |             0 |           1 |      0 |           1 |           0 |            0 | ratis-common/src/main/java/org/apache/ratis/util/NetUtils.java                          |

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

## Project 3: _apache/servicecomb-toolkit_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/servicecomb-toolkit.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/servicecomb-toolkit) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=servicecomb-toolkit) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/servicecomb-toolkit.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                                  |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                                                       |
|:--------------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| GenerateMojo.java                           |              6 |             0 |           6 |      0 |           0 |           0 |            0 | toolkit-maven-plugin/src/main/java/org/apache/servicecomb/toolkit/plugin/GenerateMojo.java                                                       |
| DefaultContractsGenerator.java              |              4 |             0 |           4 |      0 |           0 |           0 |            0 | contractgen/src/main/java/org/apache/servicecomb/toolkit/contractgen/DefaultContractsGenerator.java                                              |
| GenerateUtil.java                           |              4 |             0 |           3 |      0 |           1 |           0 |            0 | toolkit-maven-plugin/src/main/java/org/apache/servicecomb/toolkit/plugin/GenerateUtil.java                                                       |
| ParameterContext.java                       |              4 |             0 |           0 |      0 |           0 |           0 |            4 | oas-generator/oas-generator-core/src/main/java/org/apache/servicecomb/toolkit/generator/context/ParameterContext.java                            |
| VerifyMojo.java                             |              3 |             0 |           3 |      0 |           0 |           0 |            0 | toolkit-maven-plugin/src/main/java/org/apache/servicecomb/toolkit/plugin/VerifyMojo.java                                                         |
| CheckStyleBase.java                         |              3 |             0 |           3 |      0 |           0 |           0 |            0 | cli/src/main/java/org/apache/servicecomb/toolkit/cli/CheckStyleBase.java                                                                         |
| RequestMappingClassAnnotationProcessor.java |              2 |             0 |           2 |      0 |           0 |           0 |            0 | oas-generator/oas-generator-spring/src/main/java/org/apache/servicecomb/toolkit/generator/annotation/RequestMappingClassAnnotationProcessor.java |
| ClassMaker.java                             |              2 |             0 |           1 |      0 |           1 |           0 |            0 | common/src/main/java/org/apache/servicecomb/toolkit/common/ClassMaker.java                                                                       |
| OasObjectDiffValidatorUtils.java            |              2 |             0 |           0 |      0 |           2 |           0 |            0 | oas-validator/oas-validator-core/src/main/java/org/apache/servicecomb/toolkit/oasv/diffvalidation/util/OasObjectDiffValidatorUtils.java          |
| ParameterUtils.java                         |              2 |             0 |           0 |      0 |           2 |           0 |            0 | oas-validator/oas-validator-core/src/main/java/org/apache/servicecomb/toolkit/oasv/diffvalidation/util/ParameterUtils.java                       |

