---
title: 在 Aspose.Tasks 中生成时间分段数据
linktitle: 在 Aspose.Tasks 中生成资源分配的时间分段数据
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 生成资源分配的时间分段数据。通过这份综合指南提高项目管理效率。
type: docs
weight: 24
url: /zh/java/resource-assignments/timephased-data-generation/
---
## 介绍
在本教程中，我们将逐步介绍使用 Aspose.Tasks for Java 生成资源分配的时间分段数据的过程。时间分段数据提供了有关项目内资源如何随时间分配的宝贵见解，帮助项目经理做出明智的决策。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1.  Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。您可以从以下位置下载并安装 JDK[这里](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java 库：您需要有 Aspose.Tasks for Java 库。您可以从[网站](https://releases.aspose.com/tasks/java/).

## 导入包
首先，让我们导入使用 Aspose.Tasks 所需的包：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## 第1步：读取源MPP文件
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
//读取源MPP文件
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：获取任务和资源分配
```java
//获取项目的第一个任务
Task task = project.getRootTask().getChildren().getById(1);
//获取项目的第一个资源分配
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## 步骤 3：生成具有平坦轮廓的时间分段数据
```java
//平坦轮廓是默认轮廓
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 4 步：将轮廓更改为海龟
```java
//将轮廓更改为海龟
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 5 步：将轮廓更改为 BackLoaded
```java
//将轮廓更改为 BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 6 步：将轮廓更改为 FrontLoaded
```java
//将轮廓更改为 FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第7步：将轮廓更改为钟形
```java
//将轮廓更改为 Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 8 步：将等值线更改为 EarlyPeak
```java
//将轮廓更改为 EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 9 步：将轮廓更改为 LatePeak
```java
//将轮廓更改为 LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 第 10 步：将等值线更改为 DoublePeak
```java
//将轮廓更改为 DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 结论
在本教程中，我们介绍了如何使用 Aspose.Tasks for Java 生成资源分配的时间分段数据。了解不同的工作轮廓可以帮助项目经理有效地管理项目中的资源分配和调度。
## 常见问题解答
### 我可以将 Aspose.Tasks 与其他 Java 库一起使用吗？
是的，Aspose.Tasks 可以与其他 Java 库集成以增强项目管理功能。
### Aspose.Tasks适合大型企业项目吗？
当然，Aspose.Tasks 旨在处理各种规模的项目，包括大型企业项目。
### Aspose.Tasks 是否提供对不同项目文件格式的支持？
是的，Aspose.Tasks 支持各种项目文件格式，包括 MPP、XML 和 MPX。
### 我可以根据我的项目要求定制工作轮廓吗？
是的，Aspose.Tasks 允许用户定义自定义工作轮廓以满足其特定的项目需求。
### 是否有社区论坛可以让我获得有关 Aspose.Tasks 的帮助？
是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以寻求支持和讨论。