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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-discovery-impl.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-discovery-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-discovery-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-discovery-impl.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-feature.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-feature) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-feature) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-feature.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-scripting-esx.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-scripting-esx) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-scripting-esx) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-scripting-esx.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-scripting-jsp.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-scripting-jsp) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-scripting-jsp) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-scripting-jsp.json)</p>|<p align="center">Project 5</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/jspwiki-builder.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/jspwiki) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=jspwiki-builder) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/jspwiki-builder.json)</p>
# Project report summaries
## Project 1: _apache/sling-org-apache-sling-discovery-impl_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-discovery-impl.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-discovery-impl) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-discovery-impl) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-discovery-impl.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                     |
|:--------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-------------------------------------------------------------------------------|
| DiscoveryServiceImpl.java | 4              | 0             | 2           | 0      | 1           | 0           | 1            | src/main/java/org/apache/sling/discovery/impl/DiscoveryServiceImpl.java        |
| View.java                 | 3              | 0             | 3           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/discovery/impl/common/View.java                 |
| VotingHelper.java         | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/discovery/impl/cluster/voting/VotingHelper.java |
| VotingView.java           | 1              | 0             | 1           | 0      | 0           | 0           | 0            | src/main/java/org/apache/sling/discovery/impl/cluster/voting/VotingView.java   |
| ViewHelper.java           | 1              | 0             | 0           | 0      | 1           | 0           | 0            | src/main/java/org/apache/sling/discovery/impl/common/ViewHelper.java           |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                              |
| -                         | -              | -             | -           | -      | -           | -           | -            | -                                                                              |

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

## Project 3: _apache/sling-org-apache-sling-scripting-esx_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-scripting-esx.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-scripting-esx) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-scripting-esx) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-scripting-esx.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name        | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                     |
|:------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------|
| ModuleScript.java | 4              | 0             | 0           | 0      | 4           | 0           | 0            | src/main/java/org/apache/sling/scripting/esx/ModuleScript.java |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |
| -                 | -              | -             | -           | -      | -           | -           | -            | -                                                              |

## Project 4: _apache/sling-org-apache-sling-scripting-jsp_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/apache_sling-org-apache-sling-scripting-jsp.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/sling-org-apache-sling-scripting-jsp) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=apache_sling-org-apache-sling-scripting-jsp) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/apache_sling-org-apache-sling-scripting-jsp.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name               |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                             |
|:-------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------------------|
| PageDataImpl.java        |             34 |            33 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/PageDataImpl.java         |
| Dumper.java              |             22 |            21 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/Dumper.java               |
| Collector.java           |             14 |            13 |           0 |      0 |           1 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/Collector.java            |
| ELResolverImpl.java      |             13 |             0 |          13 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/el/ELResolverImpl.java             |
| JspValueExpression.java  |             13 |             0 |          13 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/el/JspValueExpression.java         |
| XMLEncodingDetector.java |             11 |             7 |           0 |      0 |           0 |           0 |            4 | src/main/java/org/apache/sling/scripting/jsp/jasper/xmlparser/XMLEncodingDetector.java |
| JspDocumentParser.java   |             11 |             8 |           1 |      0 |           2 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/JspDocumentParser.java    |
| Generator.java           |             11 |             0 |          11 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/Generator.java            |
| ELFunctionMapper.java    |             11 |            11 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/ELFunctionMapper.java     |
| Compiler.java            |             10 |             0 |          10 |      0 |           0 |           0 |            0 | src/main/java/org/apache/sling/scripting/jsp/jasper/compiler/Compiler.java             |

## Project 5: _apache/jspwiki_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/jspwiki-builder.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/jspwiki) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=jspwiki-builder) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/jspwiki-builder.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                       |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                     |
|:---------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-----------------------------------------------------------------------------------------------|
| WikiEngine.java                  |             28 |             0 |           3 |      0 |          25 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/WikiEngine.java                                     |
| ContextualDiffProvider.java      |             13 |             0 |           0 |      0 |          13 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/diff/ContextualDiffProvider.java                    |
| BasicPageFilter.java             |             10 |             5 |           4 |      0 |           1 |           0 |            0 | jspwiki-210-adapters/src/main/java/org/apache/wiki/api/filters/BasicPageFilter.java            |
| Env.java                         |              8 |             0 |           0 |      0 |           8 |           0 |            0 | jspwiki-it-tests/jspwiki-selenide-tests/src/main/java/org/apache/wiki/its/environment/Env.java |
| Acl.java                         |              5 |             0 |           0 |      0 |           5 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/auth/acl/Acl.java                                   |
| WikiTagBase.java                 |              5 |             4 |           1 |      0 |           0 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/tags/WikiTagBase.java                               |
| TextUtil.java                    |              5 |             0 |           5 |      0 |           0 |           0 |            0 | jspwiki-util/src/main/java/org/apache/wiki/util/TextUtil.java                                  |
| Heading.java                     |              4 |             0 |           0 |      0 |           4 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/parser/Heading.java                                 |
| AbstractFileProvider.java        |              4 |             0 |           1 |      0 |           3 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/providers/AbstractFileProvider.java                 |
| InternationalizationManager.java |              4 |             0 |           4 |      0 |           0 |           0 |            0 | jspwiki-main/src/main/java/org/apache/wiki/i18n/InternationalizationManager.java               |

