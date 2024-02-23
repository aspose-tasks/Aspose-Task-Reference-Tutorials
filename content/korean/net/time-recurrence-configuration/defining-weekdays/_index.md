---
title: .NET용 Aspose.Tasks에서 평일 마스터하기
linktitle: Aspose.Tasks에서 평일 정의
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks .NET에서 평일을 정의하는 기능을 살펴보세요. 자세한 튜토리얼을 따라 프로젝트 일정을 효율적으로 관리하고 작업 시간을 맞춤화하는 등의 작업을 수행하세요.
type: docs
weight: 10
url: /ko/net/time-recurrence-configuration/defining-weekdays/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 프로젝트 관리의 세계에 뛰어들고 있다면 평일을 이해하고 조작하는 것이 중요한 측면입니다. 프로젝트 일정 내에서 평일을 효율적으로 관리하고 사용자 정의하면 프로젝트 일정에 큰 영향을 미칠 수 있습니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 평일을 정의하는 과정을 안내하고 더 명확하게 설명하기 위한 단계별 지침과 예제를 제공합니다.
## 전제조건
이 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
-  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드하십시오.[여기](https://releases.aspose.com/tasks/net/).
## 네임스페이스 가져오기
필요한 네임스페이스를 프로젝트로 가져오는 것부터 시작하세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 평일 평등을 확인하세요
```csharp
// 귀하의 문서 디렉토리
String DataDir = "Your Document Directory";
// 프로젝트 파일 로드
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// 평일 이용
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// 다양한 속성을 기반으로 동등성을 확인합니다.
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. 평일 복제
```csharp
// 프로젝트 파일 로드
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// 평일의 전체 복사본 만들기
var weekDay2 = weekDay1.Clone();
// 두 평일의 출력 속성
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. 평일의 해시 코드 얻기
```csharp
// 프로젝트 파일 로드
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// 두 평일의 출력 속성
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. 평일이 정의된 새 달력 만들기
```csharp
// 새 프로젝트 만들기
var project = new Project();
// 달력 정의
var calendar = project.Calendars.Add("Calendar1");
// 영업일 및 예외일 추가
// FromDate 및 ToDate에 대해 유사한 출력 문을 추가합니다.
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// 금요일 근무 시간 설정
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. 하루 기본 근무 시간 설정
```csharp
// 새 프로젝트 만들기
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// 월요일부터 금요일까지 기본 근무 시간 추가
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// 화요일, 수요일, 목요일, 금요일에 반복하세요.
// 토요일, 일요일 휴무일 설정
// DayWorking, FromDate, ToDate 및 WorkingTimes에 대한 유사한 출력 문을 추가합니다.
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET에서 평일을 정의하는 데 필요한 필수 측면을 다루었습니다. 평일을 조정하는 것은 효과적인 프로젝트 관리를 위한 핵심 기술입니다. 제공된 예제를 실험하고 프로젝트 요구 사항에 맞게 조정하여 Aspose.Tasks의 잠재력을 최대한 활용하세요.
## 자주 묻는 질문
### 매일 근무 시간을 맞춤 설정할 수 있나요?
예, 제공된 예를 사용하여 특정 평일에 대한 맞춤형 근무 시간을 설정할 수 있습니다.
### 달력에 여러 예외일을 추가할 수 있나요?
전적으로. 추가 예외일을 포함하도록 네 번째 예제의 코드를 수정합니다.
### 달력에서 특정 요일을 어떻게 제거하나요?
Aspose.Tasks 라이브러리에서 제공하는 적절한 방법을 활용하여 필요에 따라 평일을 제거하세요.
### 평일에 대한 변경 사항이 프로젝트 파일에 유지됩니까?
예, 평일에 대한 모든 수정 사항은 저장 시 프로젝트 파일에 반영됩니다.
### Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Tasks는 다양한 프로그래밍 언어를 지원하지만 여기에 있는 예제는 특히 .NET용입니다.