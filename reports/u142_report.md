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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-slingfeature-maven-plugin.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-slingfeature-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-slingfeature-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-slingfeature-maven-plugin.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-whiteboard.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-whiteboard) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-whiteboard) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-whiteboard.json)</p>
# ATDx project report summaries
## Project 1: _apache/sling-slingfeature-maven-plugin_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-slingfeature-maven-plugin.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-slingfeature-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-slingfeature-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-slingfeature-maven-plugin.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name              |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                 |
|:------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------|
| ProjectHelper.java      |             16 |             0 |          15 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/ProjectHelper.java            |
| Aggregate.java          |             11 |             0 |           0 |      0 |          11 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/mojos/Aggregate.java          |
| UpdateVersionsMojo.java |              9 |             0 |           1 |      0 |           8 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/mojos/UpdateVersionsMojo.java |
| Preprocessor.java       |              7 |             0 |           7 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/Preprocessor.java             |
| InfoMojo.java           |              4 |             0 |           0 |      0 |           2 |           0 |            2 | src/main/java/org/apache/sling/feature/maven/mojos/InfoMojo.java           |
| Environment.java        |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/Environment.java              |
| FeatureProjectInfo.java |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/FeatureProjectInfo.java       |
| ApisJarMojo.java        |              3 |             0 |           3 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/mojos/ApisJarMojo.java        |
| JarDecompressor.java    |              2 |             1 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/mojos/JarDecompressor.java    |
| Substitution.java       |              2 |             0 |           1 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/maven/Substitution.java             |

## Project 2: _apache/sling-whiteboard_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-whiteboard.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-whiteboard) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-whiteboard) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-whiteboard.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                      | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                     |
|:--------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-----------------------------------------------------------------------------------------------|
| AuthenticationHandlerSAML2.java | 14             | 0             | 14          | 0      | 0           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/AuthenticationHandlerSAML2.java         |
| ModelPersistorImpl.java         | 10             | 0             | 10          | 0      | 0           | 0           | 0            | SlingModelPersist/src/main/java/org/apache/sling/models/persistor/impl/ModelPersistorImpl.java |
| KeyPairCredentials.java         | 8              | 0             | 7           | 0      | 1           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/sp/KeyPairCredentials.java              |
| VerifySignatureCredentials.java | 7              | 0             | 6           | 0      | 1           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/sp/VerifySignatureCredentials.java      |
| ModelPersistor.java             | 4              | 0             | 4           | 0      | 0           | 0           | 0            | SlingModelPersist/src/main/java/org/apache/sling/models/persistor/ModelPersistor.java          |
| TokenStore.java                 | 3              | 0             | 3           | 0      | 0           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/TokenStore.java                         |
| Saml2UserMgtServiceImpl.java    | 2              | 0             | 0           | 0      | 2           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/impl/Saml2UserMgtServiceImpl.java       |
| Activator.java                  | 1              | 0             | 1           | 0      | 0           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/Activator.java                          |
| Helpers.java                    | 1              | 0             | 0           | 0      | 1           | 0           | 0            | saml-handler/src/main/java/org/apache/sling/auth/saml2/Helpers.java                            |
| -                               | -              | -             | -           | -      | -           | -           | -            | -                                                                                              |

