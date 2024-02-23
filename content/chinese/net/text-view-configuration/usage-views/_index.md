---
title: 在 Aspose.Tasks 中配置使用情况视图
linktitle: 在 Aspose.Tasks 中配置使用情况视图
second_title: Aspose.Tasks .NET API
description: 了解在 Aspose.Tasks for .NET 中配置任务使用情况视图。通过详细步骤增强项目可视化。立即下载库！
type: docs
weight: 17
url: /zh/net/text-view-configuration/usage-views/
---
## 介绍
如果您是一名希望增强项目管理能力的 .NET 开发人员，Aspose.Tasks 是一款功能强大的工具，可让您轻松操作 Microsoft Project 文件。在本教程中，我们将重点介绍使用 Aspose.Tasks for .NET 配置使用视图。请继续深入了解渲染任务使用情况视图以及更好的项目可视化的详细信息。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Aspose.Tasks 库：确保您已将 Aspose.Tasks 库集成到您的 .NET 项目中。如果没有的话可以下载[这里](https://releases.aspose.com/tasks/net/)并按照安装说明进行操作。
- 文档目录：设置存储项目文档的目录。将代码片段中的“您的文档目录”替换为文档目录的实际路径。
## 导入命名空间
在提供的代码片段中，您会注意到某些命名空间的使用。确保将这些包含在您的项目中以实现无缝集成：
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## 第 1 步：渲染任务使用情况视图及详细信息
让我们首先渲染包含详细信息的任务使用情况视图。按着这些次序：
## 步骤1.1：加载项目
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## 步骤1.2：获取视图
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## 步骤1.3：自定义视图设置
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## 步骤 1.4：将项目另存为 PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## 第2步：显示详细信息标题栏
在此步骤中，我们将修改视图设置以显示详细信息标题列并将项目另存为 PDF：
## 步骤2.1：显示详细信息标题栏
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## 步骤 2.2：在所有行上重复详细信息标题
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## 步骤 2.3：将项目另存为 PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## 结论
恭喜！您已成功在 Aspose.Tasks 中配置使用视图。本教程为使用 Aspose.Tasks 库进行高效项目管理和可视化奠定了基础。

### 常见问题解答
### 问：在哪里可以找到 Aspose.Tasks 文档？
提供全面的文档[这里](https://reference.aspose.com/tasks/net/).
### 问：如何下载 Aspose.Tasks for .NET？
下载库[这里](https://releases.aspose.com/tasks/net/).
### 问：哪里可以购买 Aspose.Tasks？
你可以购买Aspose.Tasks[这里](https://purchase.aspose.com/buy).
### 问：有免费试用吗？
是的，探索免费试用版[这里](https://releases.aspose.com/).
### 问：需要支持或有疑问吗？
访问支持论坛[这里](https://forum.aspose.com/c/tasks/15).