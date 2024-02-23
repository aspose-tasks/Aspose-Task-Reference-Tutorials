---
title: Aspose.Tasks에서 근무 주간 사용자 정의
linktitle: Aspose.Tasks의 근무 주 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 작업 주를 사용자 정의하는 방법을 알아보세요. 개인화된 프로젝트 달력을 만들기 위한 단계별 가이드입니다. 지금 다운로드하세요!
type: docs
weight: 17
url: /ko/net/time-recurrence-configuration/workweek-collection/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 사용자 정의 작업 주를 만드는 방법에 대한 튜토리얼에 오신 것을 환영합니다! 이 단계별 가이드에서는 프로젝트의 달력에 대한 개인화된 작업 주를 정의하는 과정을 안내합니다. Aspose.Tasks는 개발자가 .NET 애플리케이션에서 Microsoft Project 문서를 효율적으로 사용할 수 있도록 지원하는 강력한 라이브러리입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하고 설치하세요. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 지식: C# 프로그래밍 언어 기본 사항을 숙지하세요.
## 네임스페이스 가져오기
C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: 프로젝트 및 달력 만들기
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 2단계: 맞춤형 근무 주간 정의
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 3단계: 근무일 설정
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## 4단계: 근무 주 정보 표시
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
이 포괄적인 가이드를 통해 Aspose.Tasks for .NET을 사용하여 사용자 정의 작업 주간을 효율적으로 생성하고 관리할 수 있습니다.
## 결론
결론적으로 Aspose.Tasks for .NET은 사용자 정의 작업 주간으로 프로젝트 달력을 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼을 따라 프로젝트에서 사용자 정의 작업 주에 대한 정보를 생성하고 표시하는 방법을 배웠습니다.
## 자주 묻는 질문
### 단일 프로젝트에서 여러 사용자 지정 작업 주를 가질 수 있나요?
예, 프로젝트 달력에 여러 개의 맞춤형 작업 주를 추가할 수 있습니다.
### 기존 근무 주간을 어떻게 수정할 수 있나요?
 제공된 것을 사용하십시오`WorkWeek` 기존 작업 주를 수정하는 속성 및 메서드입니다.
### Aspose.Tasks는 .NET Core와 호환됩니까?
예, Aspose.Tasks는 .NET Core를 지원합니다.
### 사용자 지정 작업 주가 포함된 프로젝트를 Microsoft Project 파일 형식으로 내보낼 수 있나요?
물론 Aspose.Tasks를 사용하면 Microsoft Project를 포함한 다양한 형식으로 프로젝트를 저장할 수 있습니다.
### Aspose.Tasks 관련 쿼리에 대한 지원은 어디서 구할 수 있나요?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 어떤 지원이나 지원을 위해.