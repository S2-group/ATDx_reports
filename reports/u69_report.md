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
|<p align="center">Project 1</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-compress.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/commons-compress) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-compress) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-compress.json)</p>|<p align="center">Project 2</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-geometry.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/commons-geometry) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-geometry) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-geometry.json)</p>|<p align="center">Project 3</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-numbers.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/commons-numbers) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-numbers) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-numbers.json)</p>
 | |
|<p align="center">Project 4</p><img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-rng.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/apache/commons-rng) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-rng) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-rng.json)</p>
# Project report summaries
## Project 1: _apache/commons-compress_
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

## Project 2: _apache/commons-geometry_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-geometry.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/commons-geometry) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-geometry) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-geometry.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                   | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                             |
|:-----------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:-----------------------------------------------------------------------------------------------------------------------|
| Matrices.java                | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/internal/Matrices.java                  |
| QuaternionRotation.java      | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/threed/rotation/QuaternionRotation.java |
| AffineTransformMatrix3D.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/threed/AffineTransformMatrix3D.java     |
| Vector2D.java                | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/twod/Vector2D.java                      |
| Vector3D.java                | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/threed/Vector3D.java                    |
| Vector1D.java                | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-geometry-euclidean/src/main/java/org/apache/commons/geometry/euclidean/oned/Vector1D.java                      |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                      |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                      |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                      |
| -                            | -              | -             | -           | -      | -           | -           | -            | -                                                                                                                      |

## Project 3: _apache/commons-numbers_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-numbers.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/commons-numbers) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-numbers) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-numbers.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name             | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                    |
|:-----------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:----------------------------------------------------------------------------------------------|
| LinearCombination.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-numbers-arrays/src/main/java/org/apache/commons/numbers/arrays/LinearCombination.java |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |
| -                      | -              | -             | -           | -      | -           | -           | -            | -                                                                                             |

## Project 4: _apache/commons-rng_
|<img src="https://github.com/S2-group/ATDx_reports/blob/master/plots/commons-rng.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/apache/commons-rng) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=commons-rng) <br> [Complete issue report (JSON)](https://github.com/S2-group/ATDx_reports/blob/master/jsons/commons-rng.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                     | Total issues   | Inheritance   | Exception   | JVMS   | Interface   | Threading   | Complexity   | Fully qualified class name                                                                                     |
|:-------------------------------|:---------------|:--------------|:------------|:-------|:------------|:------------|:-------------|:---------------------------------------------------------------------------------------------------------------|
| NumberFactory.java             | 3              | 0             | 0           | 0      | 3           | 0           | 0            | commons-rng-core/src/main/java/org/apache/commons/rng/core/util/NumberFactory.java                             |
| LargeMeanPoissonSampler.java   | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-sampling/src/main/java/org/apache/commons/rng/sampling/distribution/LargeMeanPoissonSampler.java   |
| PoissonSamplerCache.java       | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-sampling/src/main/java/org/apache/commons/rng/sampling/distribution/PoissonSamplerCache.java       |
| BaseProvider.java              | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-core/src/main/java/org/apache/commons/rng/core/BaseProvider.java                                   |
| AbstractXoShiRo512.java        | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-core/src/main/java/org/apache/commons/rng/core/source64/AbstractXoShiRo512.java                    |
| BoxMullerLogNormalSampler.java | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-sampling/src/main/java/org/apache/commons/rng/sampling/distribution/BoxMullerLogNormalSampler.java |
| BoxMullerGaussianSampler.java  | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-sampling/src/main/java/org/apache/commons/rng/sampling/distribution/BoxMullerGaussianSampler.java  |
| SamplerBase.java               | 1              | 0             | 0           | 0      | 1           | 0           | 0            | commons-rng-sampling/src/main/java/org/apache/commons/rng/sampling/distribution/SamplerBase.java               |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |
| -                              | -              | -             | -           | -      | -           | -           | -            | -                                                                                                              |

