---
title: Aspose.Tasks에서 작업 시간 마스터하기
linktitle: Aspose.Tasks의 작업 시간 수집
second_title: Aspose.태스크 .NET API
description: 프로젝트 일정을 효율적으로 관리하는 데 있어 Aspose.Tasks for .NET의 강력한 기능을 살펴보세요. 달력을 사용자 정의하고, 작업 시간을 설정하고, 프로젝트를 쉽게 간소화하세요.
type: docs
weight: 14
url: /ko/net/time-recurrence-configuration/working-time-collection/
---
## 소개
.NET용 Aspose.Tasks에서 작업 시간 관리 기술을 익히고 싶으십니까? 더 이상 보지 마세요! 이 단계별 가이드에서는 Aspose.Tasks를 사용하여 작업 시간 수집의 복잡성을 자세히 살펴보고 사용자 지정 달력을 효율적으로 처리하고 프로젝트 일정을 간소화할 수 있도록 지원합니다.
## 전제조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 갖추어져 있는지 확인하세요.
-  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[Aspose.Tasks 릴리스 페이지](https://releases.aspose.com/tasks/net/).
- 작업 환경: 가급적이면 .NET 호환 IDE를 사용하여 적합한 개발 환경을 설정합니다.
## 네임스페이스 가져오기
프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
이제 튜토리얼을 여러 단계로 나누어 원활한 학습 경험을 보장해 보겠습니다.
## 1단계: 사용자 정의 달력 만들기
새 프로젝트를 만들고 여기에 사용자 정의 달력을 추가하는 것으로 시작하세요.
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## 2단계: 근무일 정의
월요일부터 금요일까지 기본 근무일을 설정합니다.
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## 3단계: 토요일 근무 시간 구성
토요일 근무 시간 지정:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## 4단계: 토요일 근무 기간 인쇄
토요일에 대해 구성된 근무 시간을 인쇄합니다.
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 5단계: 일요일 근무 시간 구성
일요일 근무 시간을 정의합니다.
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## 6단계: 일요일 근무 기간 인쇄
일요일에 대해 구성된 근무 시간을 인쇄합니다.
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 7단계: 달력에 사용자 정의 날짜 추가
구성된 토요일과 일요일을 달력에 포함합니다.
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## 8단계: 작업 시간 순회
근무 시간을 살펴보고 달력에 매일 표시합니다.
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
이제 단계를 성공적으로 탐색했으므로 작업 시간을 효과적으로 관리하는 데 Aspose.Tasks for .NET의 기능을 활용할 수 있습니다.
## 결론
Aspose.Tasks에서 작업 시간 모음을 마스터하면 프로젝트 달력을 사용자 정의하여 정확한 일정과 효율적인 리소스 활용을 보장할 수 있습니다. 이 종합 가이드에서 얻은 지식을 바탕으로 자신감을 갖고 프로젝트에 뛰어들어 보세요.
## 자주 묻는 질문
### Aspose.Tasks는 대규모 프로젝트 관리에 적합합니까?
예, Aspose.Tasks는 다양한 규모의 프로젝트를 처리하도록 설계되어 효율적인 프로젝트 관리를 위한 강력한 기능을 제공합니다.
### Aspose.Tasks를 다른 .NET 라이브러리와 통합할 수 있나요?
틀림없이! Aspose.Tasks는 다른 .NET 라이브러리와 원활하게 통합되어 다양성과 호환성을 향상시킵니다.
### Aspose.Tasks는 얼마나 자주 업데이트되나요?
 Aspose.Tasks는 정기적으로 업데이트되어 새로운 기능, 개선 사항 및 호환성 개선 사항을 통합합니다. 을 체크 해봐[릴리스 페이지](https://releases.aspose.com/tasks/net/) 최신 업데이트를 확인하세요.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, 다음 사이트를 방문하여 무료 평가판으로 Aspose.Tasks를 탐색할 수 있습니다.[이 링크](https://releases.aspose.com/).
### Aspose.Tasks에 대한 지원은 어디서 구할 수 있나요?
 질문이나 도움이 필요하면 다음을 방문하세요.[Aspose.Tasks 지원 포럼](https://forum.aspose.com/c/tasks/15).