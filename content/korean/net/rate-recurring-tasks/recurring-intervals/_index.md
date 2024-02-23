---
title: Aspose.Tasks의 간편한 MS 프로젝트 반복 간격
linktitle: Aspose.Tasks에서 반복 간격 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 반복 간격을 손쉽게 관리하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/net/rate-recurring-tasks/recurring-intervals/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일에서 반복 간격을 효율적으로 관리하고 싶으십니까? 이 포괄적인 튜토리얼은 프로젝트에서 반복되는 간격을 쉽게 처리할 수 있도록 프로세스를 단계별로 안내합니다. 튜토리얼을 시작하기 전에 시작할 준비가 되었는지 확인하기 위해 몇 가지 전제 조건을 살펴보겠습니다.
## 전제조건
이 튜토리얼을 진행하기 전에 다음 사항이 있는지 확인하세요.
1. C# 프로그래밍 지식: C# 프로그래밍 언어 및 구문에 대한 기본적인 이해가 필요합니다.
2. Visual Studio 설치: .NET 애플리케이션 코딩 및 컴파일을 위해 시스템에 Visual Studio가 설치되어 있는지 확인하십시오.
3. .NET 라이브러리용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치합니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기
Aspose.Tasks for .NET 라이브러리에서 제공하는 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
이제 각 예를 여러 단계로 나누어 자세히 설명하겠습니다.
## 1단계: 프로젝트 개체 초기화:
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
여기서는 새 인스턴스를 초기화합니다.`Project` Microsoft Project 파일의 경로를 제공하여 클래스를 생성합니다.
## 2단계: 상황 보고 날짜 설정:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
이 단계에서는 프로젝트 상황 보고 날짜를 시작 날짜로 설정합니다.
## 3단계: 간트 차트 보기에 액세스합니다.
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
프로젝트의 Gantt Chart 보기에 액세스합니다.
## 4단계: 진행 라인 읽기:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
이 단계는 간트 차트 보기에서 진행 라인의 반복 간격을 검색합니다.
## 5단계: 간격 정보 표시:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
여기에는 간격, 주간 주 번호 및 주간 요일에 대한 정보가 표시됩니다.
## 6단계: 반복 간격 재정의:
```csharp
var newInterval = new RecurringInterval();
```
 우리는 새로운 인스턴스를 생성합니다`RecurringInterval` 반복 간격을 재정의합니다.
## 7단계: 월별 진행 라인 설정:
```csharp
// 월별 진행 상황을 날짜별로 설정하세요.
interval.MonthlyDay = true;
// 월별 진행 라인의 일 수를 설정합니다.
interval.MonthlyDayDayNumber = 1;
// 월별 진행 라인의 월 수를 설정합니다.
interval.MonthlyDayMonthNumber = 1;
// 사전 정의된 첫 번째 또는 마지막 날을 기준으로 진행 라인을 설정합니다.
interval.MonthlyFirstLast = true;
// 월별 진행 라인의 첫날 또는 마지막 날 유형을 설정합니다.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// 진행 라인의 월 수를 설정합니다.
interval.MonthlyFirstLastMonthNumber = 1;
```
이 단계에서는 지정된 매개변수에 따라 월별 진행률을 구성합니다.
## 8단계: 진행 라인 업데이트:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
새로 정의된 반복 간격으로 간트 차트 보기의 진행 라인을 업데이트합니다.
## 9단계: 프로젝트를 PDF로 저장:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
마지막으로 업데이트된 반복 간격이 포함된 프로젝트를 PDF 파일로 저장합니다.

## 결론
결론적으로, .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일에서 반복 간격을 관리하는 것은 라이브러리에서 제공하는 포괄적인 기능을 통해 간단해집니다. 이 튜토리얼에 설명된 단계별 가이드를 따르면 프로젝트에서 반복되는 간격을 효율적으로 처리하여 생산성과 구성을 향상할 수 있습니다.
### FAQ
### 다른 프로그래밍 언어와 함께 .NET용 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks for .NET은 C# 및 VB.NET과 같은 .NET 지원 언어와 함께 사용할 수 있습니다.
### .NET용 Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 Aspose.Tasks 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### .NET용 Aspose.Tasks의 임시 라이선스를 구입할 수 있나요?
 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### .NET용 Aspose.Tasks에 대한 전체 문서는 어디에서 찾을 수 있나요?
 전체 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/tasks/net/).