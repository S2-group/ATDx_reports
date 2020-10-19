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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-maven-plugin.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-maven-plugin) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-maven-plugin) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-maven-plugin.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-api.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-api) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-api) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-api.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature-io.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature-io) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature-io) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature-io.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature.json)</p>|<p align="center">Project 5</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-i18n.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-i18n) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-i18n) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-i18n.json)</p>|<p align="center">Project 6</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-installer-core.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-installer-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-installer-core) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-installer-core.json)</p>
 | |
|<p align="center">Project 7</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-installer-provider-jcr.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-installer-provider-jcr) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-installer-provider-jcr) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-installer-provider-jcr.json)</p>|<p align="center">Project 8</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-jackrabbit-accessmanager) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager.json)</p>|<p align="center">Project 9</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-jackrabbit-usermanager.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-jackrabbit-usermanager) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-jackrabbit-usermanager) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-jackrabbit-usermanager.json)</p>

# Project report summaries
## Project 1: _apache/sling-maven-plugin_
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

## Project 2: _apache/sling-org-apache-sling-api_
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

## Project 3: _apache/sling-org-apache-sling-feature-io_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature-io.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature-io) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature-io) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature-io.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                   | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                     |
|:-----------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-------------------------------------------------------------------------------|
| ConfiguratorUtil.java        | 3              | 0             | 2           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/ConfiguratorUtil.java                |
| ConfigurationJSONWriter.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/feature/io/json/ConfigurationJSONWriter.java    |
| ArtifactManagerConfig.java   | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/feature/io/artifacts/ArtifactManagerConfig.java |
| ArchiveWriter.java           | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/archive/ArchiveWriter.java           |
| IOUtils.java                 | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/IOUtils.java                         |
| JSONConstants.java           | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/json/JSONConstants.java              |
| CloseShieldWriter.java       | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/CloseShieldWriter.java               |
| ManifestUtils.java           | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/feature/io/json/ManifestUtils.java              |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                              |

## Project 4: _apache/sling-org-apache-sling-feature_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                 |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                     |
|:---------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------|
| ConfiguratorUtil.java      |              3 |             0 |           2 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/io/ConfiguratorUtil.java                |
| Extension.java             |              3 |             0 |           0 |      0 |           3 |           0 |            0 | src/main/java/org/apache/sling/feature/Extension.java                          |
| FeatureBuilder.java        |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/builder/FeatureBuilder.java             |
| JSONConstants.java         |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/io/json/JSONConstants.java              |
| IOUtils.java               |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/io/IOUtils.java                         |
| CloseShieldWriter.java     |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/io/CloseShieldWriter.java               |
| ArtifactManagerConfig.java |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/feature/io/artifacts/ArtifactManagerConfig.java |
| Configuration.java         |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/feature/Configuration.java                      |
| BuilderUtil.java           |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/builder/BuilderUtil.java                |
| BuilderContext.java        |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/feature/builder/BuilderContext.java             |

## Project 5: _apache/sling-org-apache-sling-i18n_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-i18n.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-i18n) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-i18n) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-i18n.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                              |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:------------------------------------------------------------------------|
| JcrResourceBundleProvider.java | 3              | 0             | 1           | 0      | 2           | 0           | 0            | src/main/java/org/apache/sling/i18n/impl/JcrResourceBundleProvider.java |
| JcrResourceBundle.java         | 1              | 1             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/i18n/impl/JcrResourceBundle.java         |
| LocaleResolver.java            | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/i18n/LocaleResolver.java                 |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                       |

## Project 6: _apache/sling-org-apache-sling-installer-core_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-installer-core.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-installer-core) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-installer-core) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-installer-core.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                  | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                     |
|:----------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-------------------------------------------------------------------------------|
| OsgiInstallerImpl.java      | 5              | 0             | 0           | 0      | 5           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/OsgiInstallerImpl.java      |
| Util.java                   | 4              | 0             | 0           | 0      | 4           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/Util.java                   |
| RegisteredResourceImpl.java | 2              | 0             | 1           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/RegisteredResourceImpl.java |
| InstallationContext.java    | 2              | 0             | 0           | 0      | 2           | 0           | 0            | src/main/java/org/apache/sling/installer/api/tasks/InstallationContext.java    |
| Activator.java              | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/Activator.java              |
| InternalResource.java       | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/InternalResource.java       |
| FileDataStore.java          | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/FileDataStore.java          |
| BundleUtil.java             | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/installer/core/impl/tasks/BundleUtil.java       |
| -                           | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                           | -              | -             | -           | -      | -           | -           | -            | -                                                                              |

## Project 7: _apache/sling-org-apache-sling-installer-provider-jcr_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-installer-provider-jcr.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-installer-provider-jcr) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-installer-provider-jcr) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-installer-provider-jcr.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name             | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                        |
|:-----------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:----------------------------------------------------------------------------------|
| JcrInstaller.java      | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/installer/provider/jcr/impl/JcrInstaller.java      |
| FileNodeConverter.java | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/installer/provider/jcr/impl/FileNodeConverter.java |
| JcrUtil.java           | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/installer/provider/jcr/impl/JcrUtil.java           |
| WatchedFolder.java     | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/installer/provider/jcr/impl/WatchedFolder.java     |
| FolderNameFilter.java  | 1              | 1             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/installer/provider/jcr/impl/FolderNameFilter.java  |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                 |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                 |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                 |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                 |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                 |

## Project 8: _apache/sling-org-apache-sling-jcr-jackrabbit-accessmanager_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-jackrabbit-accessmanager) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-jackrabbit-accessmanager.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                      |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:------------------------------------------------------------------------------------------------|
| AbstractAccessPostServlet.java | 5              | 0             | 0           | 0      | 5           | 0           | 0            | src/main/java/org/apache/sling/jcr/jackrabbit/accessmanager/post/AbstractAccessPostServlet.java |
| ModifyAceServlet.java          | 2              | 1             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/jcr/jackrabbit/accessmanager/post/ModifyAceServlet.java          |
| ModifyAce.java                 | 2              | 0             | 0           | 0      | 2           | 0           | 0            | src/main/java/org/apache/sling/jcr/jackrabbit/accessmanager/ModifyAce.java                      |
| DeleteAcesServlet.java         | 1              | 1             | 0           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/jcr/jackrabbit/accessmanager/post/DeleteAcesServlet.java         |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                               |

## Project 9: _apache/sling-org-apache-sling-jcr-jackrabbit-usermanager_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-jcr-jackrabbit-usermanager.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-jcr-jackrabbit-usermanager) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-jcr-jackrabbit-usermanager) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-jcr-jackrabbit-usermanager.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                          |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                            |
|:------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:------------------------------------------------------------------------------------------------------|
| AbstractPostServlet.java            |              5 |             0 |           0 |      0 |           5 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/AbstractPostServlet.java              |
| AuthorizablePrivilegesInfoImpl.java |              4 |             0 |           4 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/AuthorizablePrivilegesInfoImpl.java        |
| AuthorizableValueMap.java           |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/resource/AuthorizableValueMap.java         |
| DeleteAuthorizableServlet.java      |              2 |             2 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/DeleteAuthorizableServlet.java        |
| CreateGroupServlet.java             |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/CreateGroupServlet.java               |
| ChangeUserPasswordServlet.java      |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/ChangeUserPasswordServlet.java        |
| CreateUserServlet.java              |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/CreateUserServlet.java                |
| UpdateUserServlet.java              |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/UpdateUserServlet.java                |
| UpdateGroupServlet.java             |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/post/UpdateGroupServlet.java               |
| AuthorizableResourceProvider.java   |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/jackrabbit/usermanager/impl/resource/AuthorizableResourceProvider.java |

