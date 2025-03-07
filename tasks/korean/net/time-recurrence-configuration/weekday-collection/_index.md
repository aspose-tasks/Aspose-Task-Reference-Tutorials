---
title: Aspose.Tasks에서 평일 마스터하기
linktitle: Aspose.Tasks의 평일 컬렉션
second_title: Aspose.태스크 .NET API
description: 평일을 쉽게 관리할 수 있는 Aspose.Tasks for .NET의 강력한 기능을 알아보세요. 근무일을 사용자 정의하고, 주말을 제거하고, 특별한 달력을 쉽게 만드세요.
weight: 11
url: /ko/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 평일 마스터하기

## 소개
Aspose.Tasks for .NET은 프로젝트 관리 데이터의 효율적인 조작을 용이하게 하는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks의 평일 컬렉션을 탐색하여 작업일을 사용자 정의하고, 주말을 제거하고, 프로젝트 요구 사항에 맞는 특수 달력을 만들 수 있습니다. 숙련된 개발자이든 초보자이든 관계없이 이 단계별 가이드는 Aspose.Tasks for .NET에서 평일 작업 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET 라이브러리용 Aspose.Tasks를 설치합니다. 다음에서 다운로드할 수 있습니다.[.NET 다운로드 페이지용 Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- C# 프로그래밍 언어에 익숙합니다.
- Visual Studio와 같은 통합 개발 환경(IDE)입니다.
## 네임스페이스 가져오기
필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: 프로젝트 인스턴스 생성
새 Aspose.Tasks 프로젝트를 초기화합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2단계: 캘린더에 액세스
프로젝트 달력을 검색합니다.
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## 3단계: 평일 맞춤설정
기존 평일을 지우고 기본 근무일을 설정합니다.
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// 다른 평일도 비슷하게 추가하세요...
```
## 4단계: 근무 시간 추가
특정 평일의 근무 시간을 추가하세요.
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## 5단계: 캘린더 정보 표시
달력 세부정보를 콘솔에 출력합니다.
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// 각 평일과 근무시간을 표시합니다...
```
## 6단계: 주말 제거
평일에서 토요일과 일요일을 삭제합니다.
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## 7단계: 업데이트된 근무 시간 표시
주말을 제거한 후 업데이트된 작업 시간을 출력합니다.
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// 업데이트된 각 주중 및 근무 시간을 표시합니다...
```
## 8단계: 24시간 달력 만들기
24시간 달력을 만들고 평일을 복사합니다.
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## 결론
이 튜토리얼에서는 프로젝트 달력 내에서 평일을 관리하는 데 있어 Aspose.Tasks for .NET의 강력한 기능을 살펴보았습니다. 근무일 사용자 정의부터 전문적인 24시간 달력 생성에 이르기까지 Aspose.Tasks는 프로세스를 단순화하고 프로젝트 관리에 유연성과 제어 기능을 제공합니다.
## 자주 묻는 질문
### Q: Aspose.Tasks for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있습니까?
A: Aspose.Tasks는 주로 .NET 언어를 지원하지만 Java용 버전도 제공합니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음 사이트에서 무료 평가판을 다운로드할 수 있습니다.[Aspose.Tasks 릴리스 페이지](https://releases.aspose.com/).
### Q: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역 사회 지원을 원하거나 지원 계획 구입을 고려하십시오.
### Q: .NET용 Aspose.Tasks에 대한 포괄적인 문서는 어디에서 찾을 수 있습니까?
 답: 다음을 참조하세요.[.NET 문서용 Aspose.Tasks](https://reference.aspose.com/tasks/net/) 자세한 정보를 보려면.
### Q: .NET용 Aspose.Tasks의 임시 라이선스를 어떻게 얻나요?
 A: 임시 라이센스는 다음 사이트에서 취득할 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
