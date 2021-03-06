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
|||
|-|-|
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-drools-applications.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/policy-drools-applications) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-drools-applications) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-drools-applications.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-drools-pdp.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/policy-drools-pdp) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-drools-pdp) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-drools-pdp.json)</p>
# ATDx project report summaries
## Project 1: _onap/policy-drools-applications_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-drools-applications.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/policy-drools-applications) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-drools-applications) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-drools-applications.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                           | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                  |
|:-------------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:--------------------------------------------------------------------------------------------|
| GuardContext.java                    | 2              | 0             | 0           | 0      | 2           | 0           | 0            | controlloop/m2/guard/src/main/java/org/onap/policy/guard/GuardContext.java                  |
| Util.java                            | 1              | 0             | 0           | 0      | 1           | 0           | 0            | controlloop/m2/base/src/main/java/org/onap/policy/m2/base/Util.java                         |
| DroolsSessionCommonSerializable.java | 1              | 1             | 0           | 0      | 0           | 0           | 0            | controlloop/m2/util/src/main/java/org/onap/policy/util/DroolsSessionCommonSerializable.java |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |
| -                                    | -              | -             | -           | -      | -           | -           | -            | -                                                                                           |

## Project 2: _onap/policy-drools-pdp_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/onap_policy-drools-pdp.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/policy-drools-pdp) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_policy-drools-pdp) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/onap_policy-drools-pdp.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                   |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-------------------------------------------------------------------------------------------------------------|
| Bucket.java                    | 11             | 2             | 1           | 2      | 0           | 0           | 6            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/Bucket.java                              |
| Server.java                    | 8              | 1             | 4           | 1      | 0           | 0           | 2            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/Server.java                              |
| TargetLock.java                | 7              | 0             | 1           | 0      | 0           | 0           | 6            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/TargetLock.java                          |
| Leader.java                    | 5              | 1             | 0           | 1      | 1           | 0           | 2            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/Leader.java                              |
| StateManagementFeatureApi.java | 4              | 0             | 4           | 0      | 0           | 0           | 0            | api-state-management/src/main/java/org/onap/policy/drools/statemanagement/StateManagementFeatureApi.java     |
| ServerPoolProperties.java      | 1              | 0             | 0           | 0      | 1           | 0           | 0            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/ServerPoolProperties.java                |
| Util.java                      | 1              | 0             | 0           | 0      | 1           | 0           | 0            | feature-server-pool/src/main/java/org/onap/policy/drools/serverpool/Util.java                                |
| DroolsPdpIntegrityMonitor.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | feature-state-management/src/main/java/org/onap/policy/drools/statemanagement/DroolsPdpIntegrityMonitor.java |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                                            |

