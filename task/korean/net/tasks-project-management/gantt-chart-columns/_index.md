---
title: Aspose.Tasks를 사용하여 간트 차트 열 사용자 정의
linktitle: Aspose.Tasks의 간트 차트 열
second_title: Aspose.태스크 .NET API
description: 특정 작업 정보를 효율적으로 표시하기 위해 .NET용 Aspose.Tasks에서 Gantt 차트 열을 조정하는 방법을 알아보세요.
type: docs
weight: 21
url: /ko/net/tasks-project-management/gantt-chart-columns/
---
## 소개
간트 차트는 프로젝트 관리의 기본 도구로 작업, 일정 및 리소스를 시각적으로 표현합니다. Aspose.Tasks for .NET은 특정 작업 정보를 표시하기 위한 열 사용자 정의를 포함하여 Gantt 차트를 조작할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Gantt 차트 열로 작업하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  설치: 시스템에 설치된 .NET용 Aspose.Tasks. 그렇지 않은 경우 다음에서 다운로드하여 설치하십시오.[여기](https://releases.aspose.com/tasks/net/).
2. .NET 개발 환경: C# 및 .NET 프레임워크에 대한 실무 지식입니다.
3. 샘플 프로젝트 파일: 샘플 Microsoft Project 파일(`.mpp`) 실험하기에 편리합니다. 없으시면 MS Project에서 간단한 프로젝트를 만들어 저장하시면 됩니다.

## 네임스페이스 가져오기
먼저 .NET용 Aspose.Tasks를 사용하려면 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1단계: 프로젝트 파일 로드
 다음을 사용하여 프로젝트 파일을 로드합니다.`Project` Aspose.Tasks에서 제공하는 클래스:
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## 2단계: 간트 차트 열 정의
간트 차트에 표시할 열을 정의합니다. 기본 제공 필드를 지정하거나 사용자 정의 필드를 생성할 수 있습니다.
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## 3단계: 열 반복
정의된 열을 반복하여 해당 속성에 액세스하고 정보를 표시합니다.
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## 4단계: 간트 차트를 CSV로 저장
정의된 열이 포함된 간트 차트를 CSV 파일에 저장합니다.
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
다음 단계를 수행하면 Aspose.Tasks for .NET에서 Gantt 차트 열을 효과적으로 작업하여 필요에 따라 작업 정보를 사용자 정의하고 표시할 수 있습니다.

## 결론
.NET용 Aspose.Tasks에서 간트 차트 열 조작을 마스터하면 특정 요구 사항에 맞게 프로젝트 관리 시각적 개체를 맞춤화할 수 있는 무한한 가능성이 열립니다. 이 튜토리얼에 설명된 단계를 따르면 작업 정보를 효율적으로 처리하고 프로젝트 명확성과 구성을 향상할 수 있습니다.
## FAQ
### Q: .NET용 Aspose.Tasks에서 사용자 지정 열을 만들 수 있나요?
A: 예, 프로젝트 요구 사항에 따라 특정 작업 속성을 표시하도록 사용자 정의 열을 정의할 수 있습니다.
### Q: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project 파일과 호환됩니까?
A: Aspose.Tasks for .NET은 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 프로젝트 환경 간의 호환성을 보장합니다.
### Q: Aspose.Tasks for .NET으로 복잡한 프로젝트 구조를 어떻게 처리할 수 있나요?
A: Aspose.Tasks for .NET은 복잡한 프로젝트 구조를 관리할 수 있는 포괄적인 API와 기능을 제공하여 유연성과 확장성을 제공합니다.
### Q: 간트 차트에 추가할 수 있는 열 수에 제한이 있습니까?
A: Aspose.Tasks for .NET은 광범위한 사용자 정의 옵션을 제공하므로 제한 없이 Gantt 차트에 상당한 수의 열을 추가할 수 있습니다.
### Q: .NET용 Aspose.Tasks에 대한 추가 지원과 리소스는 어디서 찾을 수 있나요?
A: Aspose.Tasks for .NET에서 제공하는 문서, 커뮤니티 포럼 및 지원 채널을 탐색하여 포괄적인 리소스 및 지원에 액세스할 수 있습니다.