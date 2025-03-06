---
title: Aspose.Tasks에서 Workweek 구성 마스터하기
linktitle: Aspose.Tasks에서 근무 주 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 작업 주간을 쉽게 구성하는 방법을 알아보세요. 단계별 가이드를 통해 프로젝트 일정 관리 및 리소스 관리를 강화하세요.
weight: 16
url: /ko/net/time-recurrence-configuration/configuring-workweeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 Workweek 구성 마스터하기

## 소개
.NET용 Aspose.Tasks의 근무 주 구성에 대한 종합 가이드에 오신 것을 환영합니다. 효율적인 근무 주간 관리는 프로젝트 계획 및 일정 수립에 매우 중요합니다. Aspose.Tasks는 이 프로세스를 단순화하여 프로젝트 요구 사항에 따라 근무 주를 맞춤 설정할 수 있습니다. 이 튜토리얼에서는 근무 주를 원활하게 구성하는 단계를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  Aspose.Tasks 라이브러리: .NET 프로젝트에 Aspose.Tasks 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Tasks 웹사이트](https://releases.aspose.com/tasks/net/).
2. .NET 환경: .NET 환경에서 작업하고 있으며 C# 프로그래밍에 대한 기본적인 이해가 있는지 확인하세요.
## 네임스페이스 가져오기
시작하려면 프로젝트에 필요한 네임스페이스를 포함하세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: 프로젝트 설정
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2단계: 표준 달력 만들기
```csharp
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 3단계: 사용자 정의 근무 주 정의
```csharp
var item = new WorkWeek();
item.Name = "My Work Week";
item.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
item.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 4단계: 근무일 지정
```csharp
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
item.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
item.WeekDays.Add(new WeekDay(DayType.Saturday));
item.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(item);
```
## 5단계: 근무 주 세부 정보 표시
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    // 작업 주 세부 정보 표시
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    Console.WriteLine();
    // 매일 특별 근무 시간 표시
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        // 근무 시간 표시
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
다음 단계를 따르면 Aspose.Tasks에서 근무 주간을 쉽게 구성하여 프로젝트 관리 기능을 향상시킬 수 있습니다.
## 결론
결론적으로 근무주 관리는 프로젝트 계획의 기본 측면이며 Aspose.Tasks는 강력한 기능으로 이 프로세스를 단순화합니다. 프로젝트 요구 사항에 따라 작업 주를 사용자 정의하면 효율적인 리소스 활용과 더 나은 프로젝트 일정을 보장할 수 있습니다.
## 자주 묻는 질문
### 단일 프로젝트에서 여러 근무주를 구성할 수 있나요?
예, Aspose.Tasks를 사용하여 동일한 프로젝트 내에서 여러 근무주를 구성할 수 있습니다.
### 특정 요일에 근무 시간을 다르게 설정할 수 있나요?
전적으로. Aspose.Tasks를 사용하면 근무일 기준으로 매일 고유한 근무 시간을 정의할 수 있습니다.
### 프로젝트 간에 근무 주를 가져오거나 내보낼 수 있나요?
Aspose.Tasks는 강력한 가져오기/내보내기 기능을 제공하지만 근무 주간은 일반적으로 프로젝트별로 다르며 직접 전송이 불가능할 수 있습니다.
### 프로젝트에서 만들 수 있는 근무 주 수에 제한이 있나요?
현재 버전에서는 프로젝트에서 구성할 수 있는 근무 주 수에 대해 사전 정의된 제한이 없습니다.
### 일반적인 근무 주간을 위한 기본 제공 템플릿이 있나요?
예, Aspose.Tasks에는 프로젝트의 시작점으로 사용할 수 있는 표준 달력 템플릿이 포함되어 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
