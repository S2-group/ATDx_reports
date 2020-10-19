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
|||
|-|-|
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/pdfbox-reactor.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/pdfbox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=pdfbox-reactor) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/pdfbox-reactor.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/poi-parent.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/poi) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=poi-parent) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/poi-parent.json)</p>
# Project report summaries
## Project 1: _apache/pdfbox_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/pdfbox-reactor.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/pdfbox) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=pdfbox-reactor) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/pdfbox-reactor.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                   |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                             |
|:-----------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:---------------------------------------------------------------------------------------|
| PDPageContentStream.java     |             34 |             0 |           0 |      0 |          34 |           0 |            0 | pdfbox/src/main/java/org/apache/pdfbox/pdmodel/PDPageContentStream.java                |
| CMapParser.java              |             17 |             0 |           0 |      0 |           0 |           0 |           17 | fontbox/src/main/java/org/apache/fontbox/cmap/CMapParser.java                          |
| PDFDebugger.java             |             13 |             0 |          12 |      0 |           1 |           0 |            0 | debugger/src/main/java/org/apache/pdfbox/debugger/PDFDebugger.java                     |
| CCITTFactory.java            |             12 |             0 |           0 |      0 |           0 |           0 |           12 | pdfbox/src/main/java/org/apache/pdfbox/pdmodel/graphics/image/CCITTFactory.java        |
| PDFStreamParser.java         |             10 |             0 |           0 |      0 |           0 |           0 |           10 | pdfbox/src/main/java/org/apache/pdfbox/pdfparser/PDFStreamParser.java                  |
| BaseParser.java              |              8 |             0 |           0 |      0 |           0 |           0 |            8 | pdfbox/src/main/java/org/apache/pdfbox/pdfparser/BaseParser.java                       |
| OSXAdapter.java              |              6 |             0 |           6 |      0 |           0 |           0 |            0 | debugger/src/main/java/org/apache/pdfbox/debugger/ui/OSXAdapter.java                   |
| StandardSecurityHandler.java |              6 |             0 |           0 |      0 |           6 |           0 |            0 | pdfbox/src/main/java/org/apache/pdfbox/pdmodel/encryption/StandardSecurityHandler.java |
| Type2CharString.java         |              4 |             0 |           0 |      0 |           0 |           0 |            4 | fontbox/src/main/java/org/apache/fontbox/cff/Type2CharString.java                      |
| GlyphSubstitutionTable.java  |              4 |             0 |           0 |      0 |           0 |           0 |            4 | fontbox/src/main/java/org/apache/fontbox/ttf/GlyphSubstitutionTable.java               |

## Project 2: _apache/poi_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/poi-parent.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/poi) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=poi-parent) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/poi-parent.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                   |
|:--------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-----------------------------------------------------------------------------|
| FileInformationBlock.java |             34 |             0 |           0 |      0 |          34 |           0 |            0 | scratchpad/src/main/java/org/apache/poi/hwpf/model/FileInformationBlock.java |
| ClassID.java              |             28 |             0 |           1 |      0 |          27 |           0 |            0 | main/src/main/java/org/apache/poi/hpsf/ClassID.java                          |
| SXSSFCell.java            |             20 |             0 |           2 |      0 |           1 |           0 |           17 | ooxml/src/main/java/org/apache/poi/xssf/streaming/SXSSFCell.java             |
| XSSFChart.java            |             15 |             0 |           0 |      0 |          15 |           0 |            0 | ooxml/src/main/java/org/apache/poi/xssf/usermodel/XSSFChart.java             |
| HSLFShape.java            |             14 |             0 |           0 |      0 |           4 |           0 |           10 | scratchpad/src/main/java/org/apache/poi/hslf/usermodel/HSLFShape.java        |
| TableStyleType.java       |             13 |            13 |           0 |      0 |           0 |           0 |            0 | main/src/main/java/org/apache/poi/ss/usermodel/TableStyleType.java           |
| Range.java                |             13 |             0 |           0 |      0 |          13 |           0 |            0 | scratchpad/src/main/java/org/apache/poi/hwpf/usermodel/Range.java            |
| HeaderStories.java        |             13 |             0 |           0 |      0 |          13 |           0 |            0 | scratchpad/src/main/java/org/apache/poi/hwpf/usermodel/HeaderStories.java    |
| XSSFWorkbook.java         |             11 |             0 |           6 |      0 |           5 |           0 |            0 | ooxml/src/main/java/org/apache/poi/xssf/usermodel/XSSFWorkbook.java          |
| SXSSFWorkbook.java        |             11 |             0 |           5 |      0 |           6 |           0 |            0 | ooxml/src/main/java/org/apache/poi/xssf/streaming/SXSSFWorkbook.java         |

