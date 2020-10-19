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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/JMeter.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/jmeter) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=JMeter) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/JMeter.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-compress.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/commons-compress) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-compress) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-compress.json)</p>
# Project report summaries
## Project 1: _apache/jmeter_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/JMeter.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/jmeter) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=JMeter) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/JMeter.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                        |
|:-------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:--------------------------------------------------------------------------------------------------|
| LoggingManager.java            |             16 |             0 |           0 |      0 |          16 |           0 |            0 | src/jorphan/src/main/java/org/apache/jorphan/logging/LoggingManager.java                          |
| SampleResult.java              |             10 |             1 |           0 |      0 |           9 |           0 |            0 | src/core/src/main/java/org/apache/jmeter/samplers/SampleResult.java                               |
| Logger.java                    |             10 |             0 |           0 |      0 |          10 |           0 |            0 | src/jorphan/src/main/java/org/apache/log/Logger.java                                              |
| JMeterUtils.java               |              8 |             0 |           5 |      0 |           3 |           0 |            0 | src/core/src/main/java/org/apache/jmeter/util/JMeterUtils.java                                    |
| XMLDefaultMutableTreeNode.java |              5 |             0 |           4 |      0 |           1 |           0 |            0 | src/components/src/main/java/org/apache/jmeter/visualizers/XMLDefaultMutableTreeNode.java         |
| PreciseThroughputTimer.java    |              5 |             1 |           0 |      0 |           4 |           0 |            0 | src/components/src/main/java/org/apache/jmeter/timers/poissonarrivals/PreciseThroughputTimer.java |
| TableEditor.java               |              5 |             0 |           5 |      0 |           0 |           0 |            0 | src/core/src/main/java/org/apache/jmeter/testbeans/gui/TableEditor.java                           |
| TestBeanGUI.java               |              4 |             0 |           3 |      0 |           1 |           0 |            0 | src/core/src/main/java/org/apache/jmeter/testbeans/gui/TestBeanGUI.java                           |
| JMeterContext.java             |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/core/src/main/java/org/apache/jmeter/threads/JMeterContext.java                               |
| HTTPSamplerBase.java           |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/protocol/http/src/main/java/org/apache/jmeter/protocol/http/sampler/HTTPSamplerBase.java      |

## Project 2: _apache/commons-compress_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-compress.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/commons-compress) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-compress) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-compress.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                       |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                   |
|:---------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------------------------|
| SevenZFile.java                  |             17 |             0 |           3 |      0 |           3 |           0 |           11 | src/main/java/org/apache/commons/compress/archivers/sevenz/SevenZFile.java                   |
| Charsets.java                    |              7 |             0 |           0 |      0 |           7 |           0 |            0 | src/main/java/org/apache/commons/compress/utils/Charsets.java                                |
| TarArchiveOutputStream.java      |              5 |             0 |           1 |      0 |           4 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/tar/TarArchiveOutputStream.java          |
| TarArchiveEntry.java             |              5 |             0 |           0 |      0 |           2 |           0 |            3 | src/main/java/org/apache/commons/compress/archivers/tar/TarArchiveEntry.java                 |
| SevenZArchiveEntry.java          |              4 |             0 |           0 |      0 |           4 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/sevenz/SevenZArchiveEntry.java           |
| BZip2CompressorOutputStream.java |              3 |             1 |           0 |      0 |           0 |           0 |            2 | src/main/java/org/apache/commons/compress/compressors/bzip2/BZip2CompressorOutputStream.java |
| LocalFileHeader.java             |              3 |             0 |           0 |      0 |           3 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/arj/LocalFileHeader.java                 |
| Expander.java                    |              3 |             0 |           0 |      0 |           3 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/examples/Expander.java                   |
| JarArchiveEntry.java             |              2 |             0 |           0 |      0 |           2 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/jar/JarArchiveEntry.java                 |
| ZipArchiveEntry.java             |              2 |             1 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/apache/commons/compress/archivers/zip/ZipArchiveEntry.java                 |

