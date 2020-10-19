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
|<p align="center">Project 1</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_msb-apigateway.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/msb-apigateway) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_msb-apigateway) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_msb-apigateway.json)</p>|<p align="center">Project 2</p><img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_msb-java-sdk.jpg"/> <p style="text-align:left">[Project on Github](https://github.com/onap/msb-java-sdk) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_msb-java-sdk) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_msb-java-sdk.json)</p>
# Project report summaries
## Project 1: _onap/msb-apigateway_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_msb-apigateway.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/msb-apigateway) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_msb-apigateway) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_msb-apigateway.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name           |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                                |
|:---------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:----------------------------------------------------------------------------------------------------------|
| HttpClientUtil.java  |              7 |             0 |           6 |      0 |           1 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/util/HttpClientUtil.java            |
| IServiceDAO.java     |              5 |             0 |           5 |      0 |           0 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/dao/service/IServiceDAO.java        |
| IRouteDAO.java       |              5 |             0 |           5 |      0 |           0 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/dao/route/IRouteDAO.java            |
| ConsulCache.java     |              4 |             0 |           4 |      0 |           0 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/consulextend/cache/ConsulCache.java |
| FileUtil.java        |              4 |             0 |           3 |      0 |           1 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/util/FileUtil.java                  |
| JacksonJsonUtil.java |              4 |             0 |           3 |      0 |           1 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/util/JacksonJsonUtil.java           |
| ServiceDAOImpl.java  |              3 |             0 |           3 |      0 |           0 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/dao/service/ServiceDAOImpl.java     |
| RouteDAOImpl.java    |              3 |             0 |           3 |      0 |           0 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/dao/route/RouteDAOImpl.java         |
| IuiRouteService.java |              3 |             0 |           2 |      0 |           1 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/service/IuiRouteService.java        |
| JedisUtil.java       |              3 |             0 |           2 |      0 |           1 |           0 |            0 | apiroute/apiroute-service/src/main/java/org/onap/msb/apiroute/wrapper/util/JedisUtil.java                 |

## Project 2: _onap/msb-java-sdk_
|<img src="https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/plots/onap_msb-java-sdk.jpg"/>|<p style="text-align:left">[Project on Github](https://github.com/onap/msb-java-sdk) <br> [Project on SonarCloud ](https://sonarcloud.io/dashboard?id=onap_msb-java-sdk) <br> [Complete issue report (JSON)](https://github.com/robertoverdecchia/ATDx_report_sandbox/blob/master/jsons/onap_msb-java-sdk.json)</p>
|-|-|
### Top classes with architectural debt violations
| Class name                                |   Total issues |   Inheritance |   Exception |   JVMS |   Interface |   Threading |   Complexity | Fully qualified class name                                                                       |
|:------------------------------------------|---------------:|--------------:|------------:|-------:|------------:|------------:|-------------:|:-------------------------------------------------------------------------------------------------|
| RetrofitServiceUtils.java                 |              4 |             0 |           3 |      0 |           1 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/RetrofitServiceUtils.java                              |
| RetrofitServiceHandlerFactory.java        |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/RetrofitServiceHandlerFactory.java             |
| LBBuilder.java                            |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/impl/LBBuilder.java                            |
| ConverterFactoryBuilder.java              |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/impl/ConverterFactoryBuilder.java              |
| ProxyRetrofitCall.java                    |              2 |             2 |           0 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/ProxyRetrofitCall.java                                 |
| RouteException.java                       |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/discovery/common/RouteException.java                              |
| RetrofitServiceHandler.java               |              2 |             0 |           2 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/RetrofitServiceHandler.java                    |
| HandlerContextBuilder.java                |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/HandlerContextBuilder.java                     |
| ServiceHttpEndPointBeanObjectBuilder.java |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/httpclient/handler/impl/ServiceHttpEndPointBeanObjectBuilder.java |
| CustomDateSerializer.java                 |              1 |             0 |           1 |      0 |           0 |           0 |            0 | src/main/java/org/onap/msb/sdk/discovery/entity/CustomDateSerializer.java                        |
