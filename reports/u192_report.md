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
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/apache_incubator-ratis.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/incubator-ratis) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_incubator-ratis) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/apache_incubator-ratis.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/knox-gateway.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/knox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=knox-gateway) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/knox-gateway.json)</p>
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

## Project 2: _apache/knox_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/knox-gateway.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/knox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=knox-gateway) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/knox-gateway.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name             |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                       |
|:-----------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------------------------|
| DefaultDispatch.java   |             11 |            10 |           0 |      0 |           1 |           0 |            0 | gateway-adapter/src/main/java/org/apache/hadoop/gateway/dispatch/DefaultDispatch.java            |
| GatewayTestDriver.java |             11 |             0 |           2 |      0 |           9 |           0 |            0 | gateway-test-release-utils/src/main/java/org/apache/knox/gateway/GatewayTestDriver.java          |
| KnoxCLI.java           |             10 |             0 |           8 |      0 |           2 |           0 |            0 | gateway-server/src/main/java/org/apache/knox/gateway/util/KnoxCLI.java                           |
| KnoxLdapRealm.java     |              8 |             4 |           3 |      0 |           1 |           0 |            0 | gateway-adapter/src/main/java/org/apache/hadoop/gateway/shirorealm/KnoxLdapRealm.java            |
| AclParser.java         |              6 |             0 |           1 |      0 |           5 |           0 |            0 | gateway-provider-security-authz-acls/src/main/java/org/apache/knox/gateway/filter/AclParser.java |
| NiFiResponseUtil.java  |              6 |             0 |           5 |      0 |           1 |           0 |            0 | gateway-service-nifi/src/main/java/org/apache/knox/gateway/dispatch/NiFiResponseUtil.java        |
| KnoxSession.java       |              5 |             0 |           5 |      0 |           0 |           0 |            0 | gateway-shell/src/main/java/org/apache/knox/gateway/shell/KnoxSession.java                       |
| KnoxSh.java            |              4 |             0 |           3 |      0 |           1 |           0 |            0 | gateway-shell/src/main/java/org/apache/knox/gateway/shell/KnoxSh.java                            |
| KnoxPamRealm.java      |              4 |             2 |           1 |      0 |           1 |           0 |            0 | gateway-adapter/src/main/java/org/apache/hadoop/gateway/shirorealm/KnoxPamRealm.java             |
| RegEntry.java          |              4 |             0 |           0 |      0 |           4 |           0 |            0 | gateway-server/src/main/java/org/apache/knox/gateway/services/registry/impl/RegEntry.java        |
