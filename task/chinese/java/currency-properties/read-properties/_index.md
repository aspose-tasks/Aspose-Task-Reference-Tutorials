---
title: 读取 Aspose.Tasks 项目中的货币属性
linktitle: 读取 Aspose.Tasks 项目中的货币属性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project 文件中提取货币信息。提供分步指南。
type: docs
weight: 10
url: /zh/java/currency-properties/read-properties/
---
## 介绍
在本教程中，我们将学习如何利用 Aspose.Tasks for Java 从 Microsoft Project 文件读取货币属性。 Aspose.Tasks 是一个功能强大的 Java API，使开发人员能够操作 Microsoft Project 文档，而无需安装 Microsoft Project。通过执行下面概述的步骤，您将能够轻松提取与货币相关的信息。
## 先决条件
在继续本教程之前，请确保您满足以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Tasks for Java JAR：从以下位置下载 Aspose.Tasks for Java 库[这里](https://releases.aspose.com/tasks/java/)并将其包含在您的 Java 项目中。
## 导入包
首先将必要的包导入到您的 Java 类中：
```java
import com.aspose.tasks.*;
```
## 第 1 步：设置您的项目目录
首先，设置 Microsoft Project 文件所在的项目目录。您可以按如下方式定义此目录路径：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`与项目目录的实际路径。
## 第 2 步：创建项目读取器实例
实例化一个`Project`通过提供 Microsoft Project 文件的路径来对象：
```java
Project project = new Project(dataDir + "project.mpp");
```
确保更换`"project.mpp"`与您的 MS Project 文件的名称。
## 步骤 3：显示货币属性
从项目文件中检索并显示货币属性：
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
该代码段从 MS Project 文件中获取货币代码、数字、符号和符号位置等信息，并将其打印到控制台。
## 第 4 步：流程完成
最后，打印一条消息，指示该过程成功完成：
```java
System.out.println("Process completed Successfully");
```
## 结论
在本教程中，我们探讨了如何使用 Aspose.Tasks for Java 从 Microsoft Project 文件读取货币属性。通过遵循概述的步骤，您可以轻松地以编程方式从项目文件中提取与货币相关的信息，从而能够无缝集成到您的 Java 应用程序中。
## 常见问题解答
### 问：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？
答：Aspose.Tasks 支持各种版本的 Microsoft Project，包括 MS Project 2003-2021 生成的 MPP 文件。
### 问：我可以使用 Aspose.Tasks 修改货币属性吗？
答：是的，Aspose.Tasks 允许您以编程方式读取和修改 MS Project 文件中的货币属性。
### 问：Aspose.Tasks 适合商业用途吗？
答：是的，Aspose.Tasks 是一个专为专业用途而设计的商业库。您可以购买许可证[这里](https://purchase.aspose.com/buy).
### 问：Aspose.Tasks 提供免费试用吗？
答：是的，您可以免费试用 Aspose.Tasks[这里](https://releases.aspose.com/).
### 问：我可以在哪里寻求 Aspose.Tasks 的帮助或支持？
答：您可以访问Aspose.Tasks论坛[这里](https://forum.aspose.com/c/tasks/15)如有任何帮助或疑问。