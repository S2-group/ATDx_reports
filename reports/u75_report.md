# ATDx Report Summary
Our ATDx analysis targets a portfolio of software projects and identifies the pain points of each project in terms of Architectural Technical Debt (ATD). This evaluation is based on a statistical analysis of the violations of SonarCloud rules.

## ATDx in a nutshell
![ATDx in a nutshell](https://raw.githubusercontent.com/S2-group/ATDx_reports/master/plots/atdx_in_a_nutshell.jpg)

ATDx works by comparing architectural debt metrics across the projects of a software portfolio. Intuitively, it ensures that measurements across different projects are comparable, and then evaluates the severity of Architectural Technical Debt by confronting the measurements across the projects.

The ATDx approach is by itself tool-independent, and can be customized according the analysis tools available, and the portfolio considered.
In the case of this report, we used an instance of ATDx based on the static analysis tool [SonarQube](https://www.sonarqube.org/).

The instance of ATDx used to analyze your projects provides an overview of the architectural technical debt in a project in 6 distinct dimensions:
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

If you are curious about more theoretical background on ATDx, you can have a look at [this scientific publication](https://robertoverdecchia.github.io/papers/ENASE_2020.pdf).

## ATDx radar charts of your projects
||||
|-|-|-|
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_cli.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/cli) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_cli) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_cli.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-refrepo.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-refrepo) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-refrepo) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-refrepo.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-validation.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-validation) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-validation) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-validation.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-ves-agent.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-ves-agent) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-ves-agent) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-ves-agent.json)</p>
# ATDx project report summaries
## Project 1: _onap/cli_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_cli.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/cli) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_cli) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_cli.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                           |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                 |
|:-------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------------------|
| OpenRemoteCli.java                   |              4 |             0 |           4 |      0 |           0 |           0 |            0 | grpc/grpc-client/src/main/java/org/open/infc/grpc/client/OpenRemoteCli.java                |
| OnapCommand.java                     |              3 |             0 |           3 |      0 |           0 |           0 |            0 | framework/src/main/java/org/onap/cli/fw/cmd/OnapCommand.java                               |
| OnapCommandArtifactStore.java        |              2 |             0 |           2 |      0 |           0 |           0 |            0 | framework/src/main/java/org/onap/cli/fw/store/OnapCommandArtifactStore.java                |
| OnapCommandDiscoveryUtils.java       |              2 |             0 |           1 |      0 |           1 |           0 |            0 | framework/src/main/java/org/onap/cli/fw/utils/OnapCommandDiscoveryUtils.java               |
| OpenInterfaceGrpcClient.java         |              2 |             0 |           2 |      0 |           0 |           0 |            0 | grpc/grpc-client/src/main/java/org/open/infc/grpc/client/OpenInterfaceGrpcClient.java      |
| OnapCommandSchemaSnmpLoader.java     |              2 |             0 |           1 |      0 |           1 |           0 |            0 | profiles/snmp/src/main/java/org/onap/cli/fw/snmp/schema/OnapCommandSchemaSnmpLoader.java   |
| OnapCommandSchemaCmdLoader.java      |              1 |             0 |           1 |      0 |           0 |           0 |            0 | profiles/command/src/main/java/org/onap/cli/fw/cmd/schema/OnapCommandSchemaCmdLoader.java  |
| ProcessRunner.java                   |              1 |             0 |           1 |      0 |           0 |           0 |            0 | framework/src/main/java/org/onap/cli/fw/utils/ProcessRunner.java                           |
| OnapCommandExceutionShowCommand.java |              1 |             0 |           1 |      0 |           0 |           0 |            0 | framework/src/main/java/org/onap/cli/fw/cmd/execution/OnapCommandExceutionShowCommand.java |
| MockResponse.java                    |              1 |             0 |           1 |      0 |           0 |           0 |            0 | validate/sample-mock-generator/src/main/java/org/onap/cli/http/mock/MockResponse.java      |

## Project 2: _onap/vnfsdk-refrepo_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-refrepo.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-refrepo) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-refrepo) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-refrepo.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                             |
|:--------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-------------------------------------------------------------------------------------------------------|
| VTPExecutionResource.java | 2              | 0             | 2           | 0      | 0           | 0           | 0            | vnfmarket-be/vnf-sdk-marketplace/src/main/java/org/onap/vtp/execution/VTPExecutionResource.java        |
| BaseHandler.java          | 1              | 0             | 1           | 0      | 0           | 0           | 0            | vnfmarket-be/vnf-sdk-marketplace/src/main/java/org/onap/vnfsdk/marketplace/db/wrapper/BaseHandler.java |
| VTPResource.java          | 1              | 0             | 1           | 0      | 0           | 0           | 0            | vnfmarket-be/vnf-sdk-marketplace/src/main/java/org/onap/vtp/VTPResource.java                           |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                                                      |

## Project 3: _onap/vnfsdk-validation_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-validation.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-validation) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-validation) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-validation.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                 | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                       |
|:---------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------|
| ValidationException.java   | 3              | 1             | 2           | 0      | 0           | 0           | 0            | csarvalidation/src/main/java/org/onap/validation/csar/ValidationException.java   |
| ValidatorSchemaLoader.java | 2              | 0             | 2           | 0      | 0           | 0           | 0            | csarvalidation/src/main/java/org/onap/validation/csar/ValidatorSchemaLoader.java |
| VTPValidateCSARBase.java   | 1              | 0             | 1           | 0      | 0           | 0           | 0            | csarvalidation/src/main/java/org/onap/cvc/csar/cc/VTPValidateCSARBase.java       |
| CsarUtil.java              | 1              | 0             | 0           | 0      | 1           | 0           | 0            | csarvalidation/src/main/java/org/onap/validation/csar/CsarUtil.java              |
| ManifestFileSplitter.java  | 1              | 0             | 0           | 0      | 0           | 0           | 1            | csarvalidation/src/main/java/org/onap/cvc/csar/parser/ManifestFileSplitter.java  |
| CsarValidator.java         | 1              | 0             | 0           | 0      | 1           | 0           | 0            | csarvalidation/src/main/java/org/onap/validation/csar/CsarValidator.java         |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                                |

## Project 4: _onap/vnfsdk-ves-agent_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_vnfsdk-ves-agent.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/vnfsdk-ves-agent) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_vnfsdk-ves-agent) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_vnfsdk-ves-agent.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                  |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                         |
|:----------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------|
| EvelMobileFlow.java         |              5 |             2 |           0 |      0 |           3 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelMobileFlow.java         |
| EvelScalingMeasurement.java |              4 |             2 |           1 |      0 |           1 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelScalingMeasurement.java |
| RingBuffer.java             |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/evel_javalibrary/att/com/RingBuffer.java             |
| EvelSipSignaling.java       |              3 |             2 |           0 |      0 |           1 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelSipSignaling.java       |
| EvelThresholdCross.java     |              3 |             2 |           0 |      0 |           1 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelThresholdCross.java     |
| AgentMain.java              |              3 |             0 |           0 |      0 |           3 |           0 |            0 | src/main/java/evel_javalibrary/att/com/AgentMain.java              |
| EvelVoiceQuality.java       |              3 |             2 |           0 |      0 |           1 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelVoiceQuality.java       |
| EvelFault.java              |              3 |             2 |           0 |      0 |           1 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelFault.java              |
| EvelSyslog.java             |              2 |             2 |           0 |      0 |           0 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelSyslog.java             |
| EvelPnfRegistration.java    |              2 |             2 |           0 |      0 |           0 |           0 |            0 | src/main/java/evel_javalibrary/att/com/EvelPnfRegistration.java    |

