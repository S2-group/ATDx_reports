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
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_appc.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/appc) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_appc) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_appc.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_ccsdk-sli-core.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/ccsdk-sli-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_ccsdk-sli-core) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_ccsdk-sli-core.json)</p>|<p align="center">Project 3</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_ccsdk-sli-northbound.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/ccsdk-sli-northbound) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_ccsdk-sli-northbound) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_ccsdk-sli-northbound.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_so.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/so) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_so) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_so.json)</p>
# Project report summaries
## Project 1: _onap/appc_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_appc.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/appc) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_appc) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_appc.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                  |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                                         |
|:----------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-----------------------------------------------------------------------------------------------------------------------------------|
| DGGeneralDBService.java     |             25 |             0 |          25 |      0 |           0 |           0 |            0 | appc-config/appc-data-services/provider/src/main/java/org/onap/appc/data/services/db/DGGeneralDBService.java                       |
| DesignDBService.java        |             19 |             0 |          19 |      0 |           0 |           0 |            0 | appc-inbound/appc-design-services/provider/src/main/java/org/onap/appc/design/dbervices/DesignDBService.java                       |
| RequestValidator.java       |             11 |             0 |          10 |      0 |           1 |           0 |            0 | appc-inbound/appc-interfaces-service/bundle/src/main/java/org/onap/appc/interfaces/service/executor/RequestValidator.java          |
| ConfigComponentAdaptor.java |              8 |             0 |           6 |      0 |           2 |           0 |            0 | appc-config/appc-config-adaptor/provider/src/main/java/org/onap/appc/ccadaptor/ConfigComponentAdaptor.java                         |
| FlowSequenceGenerator.java  |              7 |             0 |           7 |      0 |           0 |           0 |            0 | appc-config/appc-flow-controller/provider/src/main/java/org/onap/appc/flow/controller/node/FlowSequenceGenerator.java              |
| RequestFailedException.java |              7 |             0 |           7 |      0 |           0 |           0 |            0 | appc-adapters/appc-iaas-adapter/appc-iaas-adapter-bundle/src/main/java/org/onap/appc/adapter/iaas/impl/RequestFailedException.java |
| ArtificatTransformer.java   |              6 |             0 |           6 |      0 |           0 |           0 |            0 | appc-config/appc-config-params/provider/src/main/java/org/onap/sdnc/config/params/transformer/ArtificatTransformer.java            |
| ParseAdminArtifcat.java     |              6 |             0 |           6 |      0 |           0 |           0 |            0 | appc-config/appc-encryption-tool/provider/src/main/java/org/onap/appc/encryptiontool/fqdn/ParseAdminArtifcat.java                  |
| RequestFailedException.java |              5 |             0 |           5 |      0 |           0 |           0 |            0 | appc-adapters/appc-rest-adapter/appc-rest-adapter-bundle/src/main/java/org/onap/appc/adapter/rest/impl/RequestFailedException.java |
| ArtifactHandlerNode.java    |              5 |             0 |           5 |      0 |           0 |           0 |            0 | appc-inbound/appc-artifact-handler/provider/src/main/java/org/onap/appc/artifact/handler/node/ArtifactHandlerNode.java             |

## Project 2: _onap/ccsdk-sli-core_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_ccsdk-sli-core.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/ccsdk-sli-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_ccsdk-sli-core) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_ccsdk-sli-core.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name               |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                       |
|:-------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------------------------|
| MdsalHelper.java         |              6 |             0 |           0 |      0 |           6 |           0 |            0 | sli/provider/src/main/java/org/onap/ccsdk/sli/core/sli/provider/MdsalHelper.java                 |
| MessageWriter.java       |              3 |             0 |           0 |      0 |           2 |           1 |            0 | sli/common/src/main/java/org/onap/ccsdk/sli/core/sli/MessageWriter.java                          |
| DBConfigFactory.java     |              3 |             0 |           2 |      0 |           1 |           0 |            0 | dblib/provider/src/main/java/org/onap/ccsdk/sli/core/dblib/factory/DBConfigFactory.java          |
| SliStringUtils.java      |              3 |             0 |           3 |      0 |           0 |           0 |            0 | sliPluginUtils/provider/src/main/java/org/onap/ccsdk/sli/core/slipluginutils/SliStringUtils.java |
| BaseDBConfiguration.java |              3 |             0 |           3 |      0 |           0 |           0 |            0 | dblib/provider/src/main/java/org/onap/ccsdk/sli/core/dblib/config/BaseDBConfiguration.java       |
| MetricLogger.java        |              3 |             0 |           0 |      0 |           3 |           0 |            0 | sli/common/src/main/java/org/onap/ccsdk/sli/core/sli/MetricLogger.java                           |
| SliPluginUtils.java      |              2 |             0 |           1 |      0 |           1 |           0 |            0 | sliPluginUtils/provider/src/main/java/org/onap/ccsdk/sli/core/slipluginutils/SliPluginUtils.java |
| PrintYangToProp.java     |              2 |             0 |           0 |      0 |           2 |           0 |            0 | sli/provider/src/main/java/org/onap/ccsdk/sli/core/sli/provider/PrintYangToProp.java             |
| DBResourceManager.java   |              2 |             0 |           2 |      0 |           0 |           0 |            0 | dblib/provider/src/main/java/org/onap/ccsdk/sli/core/dblib/DBResourceManager.java                |
| CachedDataSource.java    |              2 |             0 |           2 |      0 |           0 |           0 |            0 | dblib/provider/src/main/java/org/onap/ccsdk/sli/core/dblib/CachedDataSource.java                 |

## Project 3: _onap/ccsdk-sli-northbound_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_ccsdk-sli-northbound.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/ccsdk-sli-northbound) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_ccsdk-sli-northbound) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_ccsdk-sli-northbound.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:------------------------------------------------------------------------------------------|
| LcmRpcInvocationException.java | 2              | 0             | 2           | 0      | 0           | 0           | 0            | lcm/provider/src/main/java/org/onap/ccsdk/sli/northbound/LcmRpcInvocationException.java   |
| SdncGroupModel.java            | 1              | 0             | 1           | 0      | 0           | 0           | 0            | ueb-listener/src/main/java/org/onap/ccsdk/sli/northbound/uebclient/SdncGroupModel.java    |
| SdncOdlConnection.java         | 1              | 0             | 1           | 0      | 0           | 0           | 0            | ueb-listener/src/main/java/org/onap/ccsdk/sli/northbound/uebclient/SdncOdlConnection.java |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                         |

## Project 4: _onap/so_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_so.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/so) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_so) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_so.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                          |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                 |
|:------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-----------------------------------------------------------------------------------------------------------|
| BBInputSetup.java                   |             20 |             0 |          16 |      0 |           4 |           0 |            0 | bpmn/MSOCommonBPMN/src/main/java/org/onap/so/bpmn/servicedecomposition/tasks/BBInputSetup.java             |
| NetworkAdapterResources.java        |             12 |             0 |          10 |      0 |           2 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/client/orchestration/NetworkAdapterResources.java             |
| ResourceModelInfo.java              |             12 |            12 |           0 |      0 |           0 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/client/oof/beans/ResourceModelInfo.java                       |
| MsoNetworkAdapterImpl.java          |             10 |             0 |           1 |      0 |           9 |           0 |            0 | adapters/mso-openstack-adapters/src/main/java/org/onap/so/adapters/network/MsoNetworkAdapterImpl.java      |
| BBInputSetupUtils.java              |             10 |             0 |          10 |      0 |           0 |           0 |            0 | bpmn/MSOCommonBPMN/src/main/java/org/onap/so/bpmn/servicedecomposition/tasks/BBInputSetupUtils.java        |
| WorkflowAction.java                 |              9 |             0 |           6 |      0 |           3 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/bpmn/infrastructure/workflow/tasks/WorkflowAction.java        |
| SDNCConfigurationResources.java     |              8 |             0 |           8 |      0 |           0 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/client/orchestration/SDNCConfigurationResources.java          |
| MsoNetworkAdapter.java              |              7 |             0 |           0 |      0 |           7 |           0 |            0 | adapters/mso-openstack-adapters/src/main/java/org/onap/so/adapters/network/MsoNetworkAdapter.java          |
| VnfAdapterVfModuleObjectMapper.java |              6 |             0 |           5 |      0 |           1 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/client/adapter/vnf/mapper/VnfAdapterVfModuleObjectMapper.java |
| AAIDeleteTasks.java                 |              6 |             0 |           6 |      0 |           0 |           0 |            0 | bpmn/so-bpmn-tasks/src/main/java/org/onap/so/bpmn/infrastructure/aai/tasks/AAIDeleteTasks.java             |
