---
title: 使用 Aspose.Tasks for .NET 计量 MS 项目使用情况
linktitle: 计量 Aspose.Tasks 中的使用情况
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效监控和优化 MS Project 使用情况。高效项目管理的分步指南。
weight: 17
url: /zh/net/license-management/metering-usage/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for .NET 计量 MS 项目使用情况

## 介绍
您是否希望通过 Aspose.Tasks 有效管理和监控您的 MS Project 使用情况？借助计量功能，您可以跟踪您的使用情况并优化您的项目管理工作。在本教程中，我们将指导您使用 Aspose.Tasks for .NET 逐步完成计量 MS Project 使用情况的过程。
## 先决条件
在我们深入了解 MS Project 使用情况之前，请确保您满足以下先决条件：
1.  Aspose.Tasks for .NET 库：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载页面](https://releases.aspose.com/tasks/net/)。按照安装说明在您的开发环境中设置库。
2. 公钥和私钥：从 Aspose 获取您的公钥和私钥。这些键对于计量使用至关重要。如果您还没有密钥，您可以通过 Aspose 请求密钥[临时执照](https://purchase.aspose.com/temporary-license/)页。

## 导入命名空间
在继续之前，将必要的命名空间导入到您的项目中：
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## 第 1 步：设置计量
要开始计量 MS Project 使用情况，请通过提供您的公钥和私钥来设置计量环境：
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
代替`"Your Document Directory"`替换为文档目录的路径`<public key>`和`<private key>`使用从 Aspose 获得的实际密钥。
## 第 2 步：加载 MS 项目文件
接下来，使用 Aspose.Tasks 加载 MS Project 文件：
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
此步骤从指定目录加载名为“Project2.mpp”的 MS Project 文件。您可以将文件名替换为您自己的 MS Project 文件。
## 第 3 步：处理项目
现在项目已加载，您可以根据项目管理任务的需要对其执行各种操作。
```csharp
//在此执行项目管理任务
```
## 第 4 步：检查积分和字节消耗
您可以查看您在使用期间花费的积分和消耗的字节数：
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    //在这里处理异常
}
```
此步骤检索并显示您的操作花费的积分和消耗的字节。处理此过程中可能出现的任何异常。
## 第 5 步：重置计量密钥
或者，您可以重置计量键以停止计数字节：
```csharp
metered.ResetMeteredKey();
```
此步骤停止计量过程并重置计量键。

## 结论
在本教程中，您学习了如何使用 Aspose.Tasks for .NET 计量 MS Project 使用情况。通过执行这些步骤，您可以有效地监控和优化项目管理工作，同时确保高效的资源利用。
### 常见问题解答
### 问：我可以计量多个 MS Project 文件的使用情况吗？
答：是的，您可以通过单独加载每个文件并相应地监控使用情况来计量多个 MS Project 文件的使用情况。
### 问：计量 MS Project 使用情况是否与所有版本的 Aspose.Tasks for .NET 兼容？
答：是的，Aspose.Tasks for .NET 的所有版本都支持计量 MS Project 使用情况。
### 问：我需要互联网连接才能计量使用吗？
答：是的，需要互联网连接才能与 Aspose 的服务器进行通信以计量使用情况。
### 问：我可以实时跟踪使用情况吗？
答：是的，您可以通过定期检查消耗的积分和消耗的字节来实时跟踪使用情况。
### 问：试用版中是否可以计量 MS Project 使用情况？
答：是的，Aspose.Tasks for .NET 的试用版和许可版均提供计量 MS Project 使用情况。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
