---
title: 读取 Aspose.Tasks 中资源的时间分段数据
linktitle: 读取 Aspose.Tasks 中资源的时间分段数据
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project 资源中提取时间分段数据。分步教程。
type: docs
weight: 15
url: /zh/java/resource-management/read-timephased-data/
---
## 介绍
在本教程中，我们将指导您完成使用 Aspose.Tasks for Java 读取 MS Project 资源的时间分段数据的过程。该库提供了以编程方式管理 Microsoft Project 文件的强大功能。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1.  Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。您可以从[网站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)并按照安装说明进行操作。
2.  Aspose.Tasks for Java 库：从以下位置下载 Aspose.Tasks for Java 库：[下载页面](https://releases.aspose.com/tasks/java/)并按照文档中提供的安装说明进行操作。

## 导入包
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## 第 1 步：设置数据目录
首先，定义 MS Project 文件所在的目录。
```java
String dataDir = "Your Data Directory";
```
## 第 2 步：读取 MS 项目模板文件
指定 MS Project 模板文件的名称。
```java
String fileName = "ResourceTimephasedData.mpp";
```
## 第 3 步：将输入文件读取为项目
使用 Aspose.Tasks 读取输入文件并将其加载为 Project 对象。
```java
Project project = new Project(dataDir + fileName);
```
## 第四步：通过ID获取资源
通过其唯一标识符 (ID) 从项目中检索所需的资源。
```java
Resource resource = project.getResources().getByUid(1);
```
## 步骤 5：打印资源工作的时间分段数据
打印资源工作的时间分段数据。
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## 步骤 6：打印资源成本的时间分段数据
打印资源成本的时间分段数据。
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 读取 MS Project 资源的时间分段数据。通过执行这些步骤，您可以以编程方式有效地从项目文件中提取有价值的信息。
## 常见问题解答
### Aspose.Tasks 可以处理除 Microsoft Project 之外的其他类型的项目文件吗？
是的，Aspose.Tasks 支持各种文件格式，包括 MPP、XML 和 CSV。
### Aspose.Tasks是否兼容不同的Java开发环境？
是的，Aspose.Tasks 与所有主要的 Java IDE 和框架兼容。
### 我可以使用 Aspose.Tasks 操作项目数据吗？
当然，Aspose.Tasks 提供了广泛的 API 用于创建、修改和分析项目数据。
### Aspose.Tasks适合企业级项目吗？
是的，Aspose.Tasks 由于其可靠性和可扩展性而广泛应用于企业环境中。
### 如果在使用 Aspose.Tasks 时遇到问题，我可以在哪里找到支持？
您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求社区和支持团队的帮助。