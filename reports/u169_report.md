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
|||
|-|-|
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-engine.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/policy-engine) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-engine) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-engine.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-models.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/policy-models) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-models) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-models.json)</p>
# Project report summaries
## Project 1: _onap/policy-engine_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-engine.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/policy-engine) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-engine) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-engine.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                    |
|:-------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------------|
| PolicyEngine.java              |             21 |             0 |           0 |      0 |          21 |           0 |            0 | PolicyEngineAPI/src/main/java/org/onap/policy/api/PolicyEngine.java                           |
| ElkConnector.java              |              7 |             0 |           7 |      0 |           0 |           0 |            0 | ONAP-PAP-REST/src/main/java/org/onap/policy/pap/xacml/rest/elk/client/ElkConnector.java       |
| ElkConnectorImpl.java          |              7 |             0 |           7 |      0 |           0 |           0 |            0 | ONAP-PAP-REST/src/main/java/org/onap/policy/pap/xacml/rest/elk/client/ElkConnectorImpl.java   |
| PolicyEngineServices.java      |              5 |             0 |           0 |      0 |           5 |           0 |            0 | ONAP-PDP-REST/src/main/java/org/onap/policy/pdp/rest/api/controller/PolicyEngineServices.java |
| SavePolicyHandler.java         |              4 |             0 |           4 |      0 |           0 |           0 |            0 | ONAP-PAP-REST/src/main/java/org/onap/policy/pap/xacml/rest/handler/SavePolicyHandler.java     |
| PolicyApiUtils.java            |              4 |             0 |           3 |      0 |           1 |           0 |            0 | ONAP-PDP-REST/src/main/java/org/onap/policy/pdp/rest/api/utils/PolicyApiUtils.java            |
| StdPolicyEngine.java           |              4 |             0 |           0 |      0 |           4 |           0 |            0 | PolicyEngineAPI/src/main/java/org/onap/policy/std/StdPolicyEngine.java                        |
| StdEngine.java                 |              3 |             0 |           0 |      0 |           1 |           0 |            2 | ONAP-XACML/src/main/java/org/onap/policy/xacml/std/pap/StdEngine.java                         |
| PolicyElasticData.java         |              2 |             0 |           0 |      0 |           2 |           0 |            0 | ONAP-PAP-REST/src/main/java/org/onap/policy/pap/xacml/rest/elk/client/PolicyElasticData.java  |
| DecisionRequestParameters.java |              2 |             0 |           0 |      0 |           2 |           0 |            0 | PolicyEngineAPI/src/main/java/org/onap/policy/api/DecisionRequestParameters.java              |

## Project 2: _onap/policy-models_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-models.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/policy-models) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-models) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-models.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                            | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                                             |
|:--------------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------|
| PdpStatisticsProvider.java            | 1              | 0             | 0           | 0      | 1           | 0           | 0            | models-pdp/src/main/java/org/onap/policy/models/pdp/persistence/provider/PdpStatisticsProvider.java                                    |
| PfDao.java                            | 1              | 0             | 0           | 0      | 1           | 0           | 0            | models-dao/src/main/java/org/onap/policy/models/dao/PfDao.java                                                                         |
| BasicBidirectionalTopicOperation.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | models-interactions/model-actors/actor.test/src/main/java/org/onap/policy/controlloop/actor/test/BasicBidirectionalTopicOperation.java |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                                      |

