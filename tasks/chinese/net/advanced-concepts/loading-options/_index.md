---
date: 2026-03-08
description: 了解如何使用 Aspose.Tasks for .NET 导入项目文件，包括如何指定文件编码以及高效加载 Microsoft Project
  文件。
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 导入项目文件 – 在 Aspose.Tasks 中的加载选项
url: /zh/net/advanced-concepts/loading-options/
weight: 16
---

".

Now ensure we keep markdown formatting and shortcodes.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 导入项目文件 – Aspose.Tasks 中的加载选项

## 介绍

Aspose.Tasks for .NET 让 **import project file** 数据的导入变得轻松，支持 Microsoft Project、Primavera 等多种格式。无论是读取受密码保护的文件、设置自定义编码，还是处理解析错误，库都通过加载选项提供细粒度的控制。在本教程中，我们将逐步演示最常见的场景，帮助您在 .NET 应用程序中自信地 **load Microsoft Project file** 对象。

## 快速答案
- **导入项目文件的主要方式是什么？** 使用带有 `LoadOptions` 实例的 `Project` 构造函数。  
- **我可以打开受密码保护的文件吗？** 可以——在 `LoadOptions` 上设置 `Password` 属性。  
- **如何指定文件编码？** 将 `Encoding` 对象赋给 `LoadOptions.Encoding`。  
- **错误处理可以自定义吗？** 当然——为 `LoadOptions.ErrorHandler` 提供委托。  
- **这些选项能用于 Primavera 文件吗？** 可以，通过 `LoadOptions` 中的 `PrimaveraReadOptions` 实现。

## 先决条件

在开始之前，请确保您拥有：

1. **Visual Studio**（或任意您喜欢的 .NET IDE）。  
2. **Aspose.Tasks for .NET** – 从[官方网站](https://releases.aspose.com/tasks/net/)下载。  
3. 对 **C#** 语法和项目结构的基本了解。

现在我们已经准备好，导入所需的命名空间。

## 导入命名空间

在您的 C# 项目中，添加以下 `using` 语句，以便使用 API 类：

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## 如何使用加载选项导入项目文件

以下是四个实用示例，涵盖最常见的加载场景。

### 步骤 1：加载受密码保护的项目

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### 步骤 2：使用自定义选项加载 Primavera 项目

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### 步骤 3：在导入 XER 文件时**指定文件编码**

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### 步骤 4：使用自定义错误处理加载 Primavera 项目

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

按照这些步骤，您可以精确**import project file**数据，根据需求定制加载过程，并保持应用程序的健壮性。

## 常见问题与技巧

- **密码错误** – `Password` 属性会抛出异常；加载前请验证凭据。  
- **不支持的编码** – 确保您指定的代码页在目标机器上存在（例如 `Encoding.GetEncoding(1251)` 适用于西里尔文）。  
- **缺少 Primavera 选项** – 若需保留任务 UID，请设置 `PreserveUids = true`；否则可能出现重复 ID。  
- **错误处理程序返回 null** – 返回 `null` 表示解析器跳过有问题的元素；可根据需要自定义。

## 常见问题

**Q: Aspose.Tasks for .NET 是否兼容所有版本的 Microsoft Project？**  
A: 是的，它支持广泛的 Microsoft Project 版本，您可以 **load Microsoft Project file** 从旧的 MPP 文件到最新格式。

**Q: 我可以将 Aspose.Tasks for .NET 与其他第三方库集成吗？**  
A: 完全可以。该库可无缝与其他 .NET 包协同工作，方便您与报表、UI 或数据访问框架结合使用。

**Q: Aspose.Tasks for .NET 是否提供文档和支持资源？**  
A: 是的，您可以查阅完整的[文档](https://reference.aspose.com/tasks/net/)，并通过[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取支持。

**Q: Aspose.Tasks for .NET 有哪些授权选项？**  
A: 有多种授权方式可供选择，包括免费试用和临时授权，详情请访问[Aspose.Tasks 网站](https://purchase.aspose.com/buy)。

**Q: Aspose.Tasks for .NET 的更新和新功能发布频率如何？**  
A: Aspose.Tasks 定期发布更新，新增功能、提升性能，并保持与最新 Microsoft Project 版本的兼容性。

---

**最后更新：** 2026-03-08  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}