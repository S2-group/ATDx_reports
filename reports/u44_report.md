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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-distribution-journal.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-distribution-journal) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-distribution-journal) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-distribution-journal.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-i18n.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-i18n) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-i18n) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-i18n.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-resourceresolver.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-resourceresolver) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-resourceresolver) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-resourceresolver.json)</p>|<p align="center">Project 5</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-servlet-helpers.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-servlet-helpers) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-servlet-helpers) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-servlet-helpers.json)</p>
# Project report summaries
## Project 1: _apache/sling-org-apache-sling-distribution-journal_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-distribution-journal.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-distribution-journal) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-distribution-journal) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-distribution-journal.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                 |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                    |
|:---------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------------|
| LocalStore.java            |              3 |             0 |           3 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/subscriber/LocalStore.java           |
| DistributionPublisher.java |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/publisher/DistributionPublisher.java |
| PubQueueCache.java         |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/queue/impl/PubQueueCache.java        |
| JMXRegistration.java       |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/shared/JMXRegistration.java          |
| PackageRepo.java           |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/publisher/PackageRepo.java           |
| BookKeeper.java            |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/subscriber/BookKeeper.java           |
| LimitPoller.java           |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/shared/LimitPoller.java              |
| PackageMessageFactory.java |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/publisher/PackageMessageFactory.java |
| Announcer.java             |              1 |             0 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/subscriber/Announcer.java            |
| PubQueueCacheService.java  |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/distribution/journal/impl/queue/impl/PubQueueCacheService.java |

## Project 2: _apache/sling-org-apache-sling-feature_
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

## Project 3: _apache/sling-org-apache-sling-i18n_
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

## Project 4: _apache/sling-org-apache-sling-resourceresolver_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-resourceresolver.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-resourceresolver) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-resourceresolver) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-resourceresolver.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                            |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                         |
|:--------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------------------------------|
| URI.java                              |             56 |             1 |          54 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/helper/URI.java                               |
| ResourceResolverFactoryActivator.java |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/ResourceResolverFactoryActivator.java         |
| MapEntries.java                       |              3 |             0 |           3 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/mapping/MapEntries.java                       |
| FactoryPreconditions.java             |              3 |             0 |           0 |      0 |           3 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/FactoryPreconditions.java                     |
| ResourceResolverImpl.java             |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/ResourceResolverImpl.java                     |
| URIException.java                     |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/helper/URIException.java                      |
| ResourceResolverWebConsolePlugin.java |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/console/ResourceResolverWebConsolePlugin.java |
| ResourceChangeListenerInfo.java       |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/observation/ResourceChangeListenerInfo.java   |
| ResourceProviderHandler.java          |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/providers/ResourceProviderHandler.java        |
| MapEntry.java                         |              1 |             1 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/resourceresolver/impl/mapping/MapEntry.java                         |

## Project 5: _apache/sling-org-apache-sling-servlet-helpers_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-servlet-helpers.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-servlet-helpers) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-servlet-helpers) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-servlet-helpers.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                        | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                      |
|:----------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:--------------------------------------------------------------------------------|
| MockSlingHttpServletRequest.java  | 2              | 0             | 2           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/servlethelpers/MockSlingHttpServletRequest.java  |
| ResponseBodySupport.java          | 2              | 0             | 2           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/servlethelpers/ResponseBodySupport.java          |
| AdaptableUtil.java                | 2              | 0             | 1           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/servlethelpers/AdaptableUtil.java                |
| MockSlingHttpServletResponse.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/servlethelpers/MockSlingHttpServletResponse.java |
| MockRequestPathInfo.java          | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/servlethelpers/MockRequestPathInfo.java          |
| -                                 | -              | -             | -           | -      | -           | -           | -            | -                                                                               |
| -                                 | -              | -             | -           | -      | -           | -           | -            | -                                                                               |
| -                                 | -              | -             | -           | -      | -           | -           | -            | -                                                                               |
| -                                 | -              | -             | -           | -      | -           | -           | -            | -                                                                               |
| -                                 | -              | -             | -           | -      | -           | -           | -            | -                                                                               |

