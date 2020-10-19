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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-jspc-maven-plugin.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-jspc-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-jspc-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-jspc-maven-plugin.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-maven-launchpad-plugin.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-maven-launchpad-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-maven-launchpad-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-maven-launchpad-plugin.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-maven-plugin.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-maven-plugin.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-api.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-api) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-api) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-api.json)</p>|<p align="center">Project 5</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-app-cms.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-app-cms) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-app-cms) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-app-cms.json)</p>|<p align="center">Project 6</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-auth-core.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-auth-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-auth-core) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-auth-core.json)</p>
 | |
|<p align="center">Project 7</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-auth-form.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-auth-form) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-auth-form) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-auth-form.json)</p>|<p align="center">Project 8</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-bundleresource-impl.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-bundleresource-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-bundleresource-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-bundleresource-impl.json)</p>|<p align="center">Project 9</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-caconfig-impl.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-caconfig-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-caconfig-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-caconfig-impl.json)</p>

# Project report summaries
## Project 1: _apache/sling-jspc-maven-plugin_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-jspc-maven-plugin.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-jspc-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-jspc-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-jspc-maven-plugin.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                 | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                           |
|:---------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------|
| JspCServletContext.java    | 4              | 0             | 0           | 0      | 4           | 0           | 0            | src/main/java/org/apache/sling/maven/jspc/JspCServletContext.java    |
| JspcMojo.java              | 3              | 0             | 2           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/maven/jspc/JspcMojo.java              |
| JspCTldLocationsCache.java | 2              | 0             | 2           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/jspc/JspCTldLocationsCache.java |
| JspCIOProvider.java        | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/jspc/JspCIOProvider.java        |
| JspCClassLoaderWriter.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/jspc/JspCClassLoaderWriter.java |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                    |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                    |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                    |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                    |
| -                          | -              | -             | -           | -      | -           | -           | -            | -                                                                    |

## Project 2: _apache/sling-maven-launchpad-plugin_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-maven-launchpad-plugin.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-maven-launchpad-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-maven-launchpad-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-maven-launchpad-plugin.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                               | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                   |
|:-----------------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------------------|
| LaunchpadPluginLifecycleParticipant.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/projectsupport/LaunchpadPluginLifecycleParticipant.java |
| RunMojo.java                             | 1              | 1             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/projectsupport/RunMojo.java                             |
| StartMojo.java                           | 1              | 1             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/projectsupport/StartMojo.java                           |
| AttachPartialBundleListMojo.java         | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/maven/projectsupport/AttachPartialBundleListMojo.java         |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |
| -                                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                            |

## Project 3: _apache/sling-maven-plugin_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-maven-plugin.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-maven-plugin.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                       | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                     |
|:---------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------------------|
| GenerateAdapterMetadataMojo.java | 3              | 0             | 3           | 0      | 0           | 0           | 0            | sling-maven-plugin/src/main/java/org/apache/sling/maven/bundlesupport/GenerateAdapterMetadataMojo.java         |
| WebDavPutDeployMethod.java       | 3              | 0             | 3           | 0      | 0           | 0           | 0            | sling-maven-plugin/src/main/java/org/apache/sling/maven/bundlesupport/deploy/method/WebDavPutDeployMethod.java |
| AbstractBundleInstallMojo.java   | 1              | 0             | 0           | 0      | 1           | 0           | 0            | sling-maven-plugin/src/main/java/org/apache/sling/maven/bundlesupport/AbstractBundleInstallMojo.java           |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |

## Project 4: _apache/sling-org-apache-sling-api_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-api.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-api) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-api) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-api.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name               |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                       |
|:-------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------------|
| ResourceProviderDTO.java |             10 |             0 |           0 |      0 |          10 |           0 |            0 | src/main/java/org/apache/sling/api/resource/runtime/dto/ResourceProviderDTO.java |
| ResourceUtil.java        |              7 |             0 |           0 |      0 |           7 |           0 |            0 | src/main/java/org/apache/sling/api/resource/ResourceUtil.java                    |
| SlingConstants.java      |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/sling/api/SlingConstants.java                           |
| ResourceChange.java      |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/sling/api/resource/observation/ResourceChange.java      |
| CompositeValueMap.java   |              3 |             2 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/api/wrappers/CompositeValueMap.java               |
| NonExistingResource.java |              3 |             3 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/api/resource/NonExistingResource.java             |
| ResourceMetadata.java    |              2 |             1 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/api/resource/ResourceMetadata.java                |
| ResourceProvider.java    |              2 |             0 |           0 |      0 |           2 |           0 |            0 | src/main/java/org/apache/sling/api/resource/ResourceProvider.java                |
| RuntimeDTO.java          |              2 |             0 |           0 |      0 |           2 |           0 |            0 | src/main/java/org/apache/sling/api/resource/runtime/dto/RuntimeDTO.java          |
| ValueMapDecorator.java   |              2 |             2 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/api/wrappers/ValueMapDecorator.java               |

## Project 5: _apache/sling-org-apache-sling-app-cms_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-app-cms.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-app-cms) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-app-cms) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-app-cms.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name               | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                             |
|:-------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------------|
| FormRequestImpl.java     | 3              | 0             | 3           | 0      | 0           | 0           | 0            | reference/src/main/java/org/apache/sling/cms/reference/forms/impl/FormRequestImpl.java |
| BaseInsightProvider.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | core/src/main/java/org/apache/sling/cms/core/insights/impl/BaseInsightProvider.java    |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |
| -                        | -              | -             | -           | -      | -           | -           | -            | -                                                                                      |

## Project 6: _apache/sling-org-apache-sling-auth-core_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-auth-core.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-auth-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-auth-core) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-auth-core.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                            | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                       |
|:--------------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------|
| AbstractAuthenticationHandler.java    | 9              | 0             | 0           | 0      | 9           | 0           | 0            | src/main/java/org/apache/sling/auth/core/spi/AbstractAuthenticationHandler.java  |
| AuthenticationInfo.java               | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/engine/auth/AuthenticationInfo.java               |
| AuthenticationHandler.java            | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/engine/auth/AuthenticationHandler.java            |
| Authenticator.java                    | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/engine/auth/Authenticator.java                    |
| NoAuthenticationHandlerException.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/engine/auth/NoAuthenticationHandlerException.java |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                |

## Project 7: _apache/sling-org-apache-sling-auth-form_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-auth-form.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-auth-form) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-auth-form) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-auth-form.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                   |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-----------------------------------------------------------------------------|
| FormAuthenticationHandler.java | 3              | 0             | 3           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/auth/form/impl/FormAuthenticationHandler.java |
| TokenStore.java                | 3              | 0             | 3           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/auth/form/impl/TokenStore.java                |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                            |

## Project 8: _apache/sling-org-apache-sling-bundleresource-impl_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-bundleresource-impl.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-bundleresource-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-bundleresource-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-bundleresource-impl.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                       | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                          |
|:---------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:------------------------------------------------------------------------------------|
| BundleResourceURLConnection.java | 4              | 4             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/bundleresource/impl/BundleResourceURLConnection.java |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |
| -                                | -              | -             | -           | -      | -           | -           | -            | -                                                                                   |

## Project 9: _apache/sling-org-apache-sling-caconfig-impl_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-caconfig-impl.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-caconfig-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-caconfig-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-caconfig-impl.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                            | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                           |
|:--------------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-----------------------------------------------------------------------------------------------------|
| ConfigurationResourceWrapper.java     | 8              | 8             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/caconfig/impl/ConfigurationResourceWrapper.java                       |
| ConfigurationDataImpl.java            | 2              | 0             | 0           | 0      | 2           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/impl/ConfigurationDataImpl.java                   |
| ConfigurationBuilderImpl.java         | 2              | 0             | 0           | 0      | 2           | 0           | 0            | src/main/java/org/apache/sling/caconfig/impl/ConfigurationBuilderImpl.java                           |
| ConfigurationManager.java             | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/ConfigurationManager.java                         |
| ContextPathStrategyMultiplexer.java   | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/ContextPathStrategyMultiplexer.java               |
| OverrideStringParser.java             | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/caconfig/impl/override/OverrideStringParser.java                      |
| CAConfigInventoryPrinter.java         | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/impl/console/CAConfigInventoryPrinter.java        |
| ConfigurationOverrideMultiplexer.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/multiplexer/ConfigurationOverrideMultiplexer.java |
| ValueInfoImpl.java                    | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/caconfig/management/impl/ValueInfoImpl.java                           |
| -                                     | -              | -             | -           | -      | -           | -           | -            | -                                                                                                    |

