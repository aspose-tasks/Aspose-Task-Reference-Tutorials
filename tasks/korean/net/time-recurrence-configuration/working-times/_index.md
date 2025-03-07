---
title: Aspose.Tasks에서 작업 시간 구성
linktitle: Aspose.Tasks에서 작업 시간 구성
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET에서 프로젝트 일정을 개선하세요. 정확한 자원 관리를 위해 작업 시간을 손쉽게 구성하세요. 지금 라이브러리를 다운로드하세요!
weight: 13
url: /ko/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 시간 구성

## 소개
프로젝트 관리에서는 정확한 일정 관리와 리소스 할당을 위해 작업 시간을 정밀하게 제어하는 것이 중요합니다. Aspose.Tasks for .NET은 프로젝트 내 작업 시간 정보를 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼은 .NET 환경에서 Aspose.Tasks를 사용하여 작업 시간을 구성하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
-  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- Visual Studio 또는 선호하는 C# 개발 환경 설정.
## 네임스페이스 가져오기
Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## 1단계: 캘린더 만들기
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
여기서는 새 프로젝트를 시작하고 표준 달력을 기반으로 "MyCalendar"라는 이름의 달력을 만듭니다. 이 달력은 특정 근무 시간을 정의하는 데 사용됩니다.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## 2단계: 근무 주 정보 표시
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
이 단계는 지정된 달력의 총 근무일 수를 인쇄합니다.
## 3단계: 근무 시간 세부정보
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
이 부분에서는 각 요일을 반복하여 요일 유형 및 관련 작업 시간을 인쇄합니다. 프로젝트 요구 사항에 따라 각 평일의 작업 시간을 맞춤 설정할 수 있습니다.
## 결론
Aspose.Tasks for .NET에서 작업 시간을 효과적으로 구성하면 정확한 프로젝트 계획 및 리소스 관리가 보장됩니다. 이 단계별 가이드를 따르면 작업 시간 조정을 프로젝트 워크플로우에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 대규모 프로젝트 관리에 적합합니까?
예, Aspose.Tasks는 다양한 규모의 프로젝트를 처리하도록 설계되었으며 효율적인 프로젝트 관리를 위한 강력한 기능을 제공합니다.
### 팀원마다 근무 시간을 다르게 설정할 수 있나요?
전적으로. 리소스별로 작업 시간을 맞춤설정하여 개별화된 일정을 설정할 수 있습니다.
### Aspose.Tasks는 다른 프로젝트 관리 도구와의 통합을 지원합니까?
예, Aspose.Tasks는 다양한 프로젝트 관리 도구와의 통합을 촉진하여 상호 운용성을 향상시킵니다.
### 프로젝트 데이터를 다른 형식으로 가져오거나 내보낼 수 있습니까?
Aspose.Tasks는 다양한 파일 형식을 지원하여 프로젝트 데이터에 대한 원활한 가져오기/내보내기 작업을 가능하게 합니다.
### Aspose.Tasks 업데이트는 얼마나 자주 출시되나요?
최신 기술과의 호환성을 보장하고 사용자 피드백을 해결하기 위해 업데이트가 정기적으로 출시됩니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
