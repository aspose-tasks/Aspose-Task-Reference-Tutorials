---
date: 2025-12-15
description: 学习如何使用 Aspose.Tasks Java 读取 MS Project Online 数据。本指南展示了如何检索项目列表、列出 SharePoint
  项目以及获取资源计数。
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java - 轻松读取 MS Project 在线数据
url: /zh/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java：轻松读取 MS Project Online 数据

## 介绍
在项目管理领域，高效处理 Microsoft Project Online 数据对于实现流畅的业务运营至关重要。**aspose tasks java** 提供了一个强大且易于使用的 API，让您无需手动编写底层 HTTP 调用即可读取 Project Online 数据。在本教程中，我们将演示如何获取项目列表、列出 SharePoint 项目以及获取每个项目的资源计数——只需几行 Java 代码即可完成。

## 快速解答
- **aspose tasks java 能做什么？** 它可以以编程方式读取和操作 Microsoft Project 文件以及 Project Online 数据。  
- **试用是否需要许可证？** 提供免费试用；生产环境使用需购买许可证。  
- **需要哪些凭据？** SharePoint 域、用户名和密码（或 Azure AD 令牌）。  
- **可以列出 SharePoint 项目吗？** 可以——使用 `ProjectServerManager.getProjectList()` 获取。  
- **如何获取资源计数？** 加载每个 `Project` 对象并调用 `project.getResources().size()`。

## aspose tasks java 是什么？
**aspose tasks java** 是面向开发者的库，抽象了 Microsoft Project 文件格式和 Project Server REST API 的复杂性。它使您能够直接在 Java 应用程序中读取、创建和修改项目数据，轻松与现有企业系统集成。

## 为什么在读取 MS Project Online 时使用 aspose tasks java？
- **无需手动处理 HTTP** —— 库会自动完成身份验证和 REST 调用。  
- **强类型安全** —— 使用 `Project`、`ProjectInfo` 等 POJO，而非原始 JSON。  
- **跨平台** —— 可在任何兼容 JVM 的环境中运行。  
- **功能丰富** —— 除了读取，还可以更新任务、资源和时间线。

## 前提条件
在开始之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** —— 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java 库** —— 从 [此处](https://releases.aspose.com/tasks/java/) 下载。  
3. **Microsoft Project Online 账户** —— 具备读取项目的权限。  
4. **SharePoint 域地址** —— 您的 Project Online 实例所在的域。  
5. **用户名和密码** —— 或相应的 Azure AD 凭据用于身份验证。

## 导入包
首先，导入本教程中将使用的核心 Aspose.Tasks 类：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 步骤 1：设置 SharePoint 域、用户名和密码
为您的 Project Online 环境定义连接细节。将占位符值替换为您自己的凭据。

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## 步骤 2：使用 Project Server 凭据进行身份验证
创建 `ProjectServerCredentials` 对象并初始化 `ProjectServerManager`。该管理器将处理后续对 Project Online 的所有调用。

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## 步骤 3：检索项目列表并显示信息
使用管理器 **检索项目列表**（列出 SharePoint 项目），并打印名称、创建日期和最近保存日期等基本信息。

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## 步骤 4：加载单个项目并输出资源计数
针对上一步返回的每个项目，加载完整的 `Project` 对象并显示 **资源计数**。

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **Authentication failed** | 域、用户名或密码不正确。 | 核实凭据并确保账户拥有 Project Online 读取权限。 |
| **SSLHandshakeException** | Java 运行时缺少所需的 TLS 版本。 | 将 JDK 更新至最新版本或启用 TLS 1.2 以上。 |
| **`reader.getProjectList()` returns empty** | 账户没有任何项目的访问权限。 | 检查 Project Online 权限或使用管理员账户。 |
| **Large projects cause OutOfMemoryError** | 同时加载大量项目会消耗过多内存。 | 一次加载一个项目，使用后释放引用。 |

## 常见问答
### 问：我可以使用 aspose tasks java 修改 MS Project Online 数据吗？
**答：** 可以，Aspose.Tasks 提供了丰富的功能，既可以读取也可以以编程方式修改 Project Online 数据。

### 问：Aspose.Tasks 支持其他项目管理文件格式吗？
**答：** 当然。它支持 MPP、XML、Primavera 等多种格式，确保在不同项目生态系统中的兼容性。

### 问：是否有 Aspose.Tasks for Java 的免费试用？
**答：** 有，您可以从 [此处](https://releases.aspose.com/) 获取免费试用，以探索 Aspose.Tasks 的功能和特性。

### 问：在哪里可以找到 Aspose.Tasks for Java 的完整文档？
**答：** 请参阅详细文档 [此处](https://reference.aspose.com/tasks/java/)，获取关于在 Java 项目中使用 Aspose.Tasks 的全面指南。

### 问：Aspose.Tasks for Java 提供哪些支持选项？
**答：** 如有问题或疑问，可在 Aspose.Tasks 社区论坛 [此处](https://forum.aspose.com/c/tasks/15) 寻求帮助。

**最后更新：** 2025-12-15  
**测试环境：** Aspose.Tasks for Java 24.11（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}