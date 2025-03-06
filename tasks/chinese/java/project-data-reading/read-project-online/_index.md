---
title: 使用 Aspose.Tasks 轻松读取 MS Project 在线数据
linktitle: 在Aspose.Tasks中读取项目在线数据
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 轻松读取 Microsoft Project Online 数据。增强您的项目管理能力。
type: docs
weight: 13
url: /zh/java/project-data-reading/read-project-online/
---
## 介绍
在项目管理领域，有效处理 Microsoft Project Online 数据对于简化操作至关重要。 Aspose.Tasks for Java 提供了一个强大的解决方案来轻松读取此类数据。本教程深入探讨如何利用 Aspose.Tasks 无缝访问和操作 MS Project Online 数据。
## 先决条件
在深入学习本教程之前，请确保您具备以下条件：
1. Java开发工具包（JDK）：安装JDK来编译和运行Java程序。
2.  Aspose.Tasks for Java Library：下载 Aspose.Tasks 库并将其包含在您的 Java 项目中。您可以从以下位置获取它[这里](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online 帐户：获取用于访问 MS Project Online 数据的有效凭据。
4. SharePoint 域地址：MS Project Online 数据所在的 SharePoint 域地址。
5. 用户名和密码：用于验证 MS Project Online 访问权限的凭据。
## 导入包
在您的 Java 项目中，导入必要的 Aspose.Tasks 包以实现无缝集成：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 步骤 1：设置 SharePoint 域地址、用户名和密码
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
代替`"https://contoso.sharepoint.com"`与您的 SharePoint 域地址，`"admin@contoso.onmicrosoft.com"`与您的用户名，以及`"MyPassword"`用你的密码。
## 步骤 2：使用 Project Server 凭据进行身份验证
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
创造`ProjectServerCredentials`包含 SharePoint 域地址、用户名和密码的对象。然后初始化`ProjectServerManager`有了这些凭证。
## 步骤 3：检索项目列表并显示信息
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
迭代获得的项目列表`reader.getProjectList()`并显示项目详细信息，例如名称、创建日期和上次保存日期。
## 步骤 4：加载单个项目并输出资源计数
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
对于每个项目，使用加载它`reader.getProject(p.getId())`并输出项目名称以及关联资源的数量。

## 结论
Aspose.Tasks for Java 简化了读取 MS Project Online 数据的过程，为开发人员提供了一个强大的工具集来简化项目管理任务。通过遵循本教程，您可以有效地将 Aspose.Tasks 集成到您的 Java 应用程序中，以轻松访问和操作项目数据。
## 常见问题解答
### 问：我可以使用 Aspose.Tasks for Java 修改 MS Project Online 数据吗？
答：是的，Aspose.Tasks 提供了广泛的功能，不仅可以读取，还可以通过编程方式修改 MS Project Online 数据。
### 问：Aspose.Tasks 是否支持其他项目管理文件格式？
答：当然，Aspose.Tasks 支持各种文件格式，包括 MPP、XML 等，确保与各种项目管理系统的兼容性。
### 问：Aspose.Tasks for Java 是否有免费试用版？
答：是的，您可以通过以下方式免费试用：[这里](https://releases.aspose.com/)探索 Aspose.Tasks 的特性和功能。
### 问：在哪里可以找到 Aspose.Tasks for Java 的综合文档？
答：可以参考详细文档[这里](https://reference.aspose.com/tasks/java/)有关在 Java 项目中使用 Aspose.Tasks 的全面指导。
### 问：Aspose.Tasks for Java 有哪些支持选项？
答：如果您遇到任何问题或有疑问，可以从 Aspose.Tasks 社区论坛寻求帮助[这里](https://forum.aspose.com/c/tasks/15).