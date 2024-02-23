---
title: Aspose.Tasks에서 캘린더 컬렉션 관리
linktitle: Aspose.Tasks에서 캘린더 컬렉션 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 캘린더 컬렉션을 효율적으로 관리하는 방법을 알아보세요. 캘린더를 쉽게 생성, 수정, 조작할 수 있습니다.
type: docs
weight: 11
url: /ko/net/calendar-scheduling/calendar-collection/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 캘린더 컬렉션을 관리하는 방법을 살펴보겠습니다. 달력은 근무일, 공휴일 및 예외를 정의하여 프로젝트 관리에서 중요한 역할을 합니다. Aspose.Tasks는 프로젝트 내에서 달력을 조작할 수 있는 강력한 기능을 제공합니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. Visual Studio: Visual Studio 또는 .NET 개발을 위한 기타 호환 IDE를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

먼저 Aspose.Tasks 작업에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## 새 달력 만들기

###  1단계: 새 초기화`Project` object.
```csharp
var project = new Project();
```

### 2단계: 프로젝트의 달력 컬렉션에 달력을 추가합니다.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 3단계: 달력을 반복하고 이름을 표시합니다.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 달력을 새 달력으로 바꾸기

### 1단계: 기존 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2단계: 기존 캘린더를 제거합니다(있는 경우).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 3단계: 새 캘린더를 추가합니다.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 이름 또는 ID로 캘린더 가져오기

### 1단계: 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2단계: 이름이나 UID로 캘린더를 검색합니다.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 3단계: 캘린더 세부정보를 표시합니다.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## 달력 반복

### 1단계: 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2단계: 달력 개수를 검색합니다.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 3단계: 캘린더 컬렉션과 표시 이름을 반복합니다.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 표준 달력 만들기

### 1단계: 새 프로젝트를 초기화합니다.
```csharp
var project = new Project();
```

### 2단계: 새 달력을 정의하고 표준으로 만듭니다.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 3단계: 프로젝트를 저장합니다.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 결론

효과적인 프로젝트 관리를 위해서는 Aspose.Tasks for .NET에서 캘린더 컬렉션을 관리하는 것이 필수적입니다. 제공된 기능을 사용하면 프로젝트 요구 사항에 따라 달력을 효율적으로 생성, 수정 및 조작할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks에서 사용자 정의 근무일을 만들 수 있나요?

A1: 예, 달력에 예외를 추가하여 맞춤형 근무일을 생성할 수 있습니다.

### Q2: Microsoft Project 파일에서 달력을 가져올 수 있습니까?

A2: 물론 Aspose.Tasks는 Microsoft Project 파일에서 달력 가져오기를 지원합니다.

### Q3: 프로젝트에서 특정 달력을 제거하려면 어떻게 해야 합니까?

A3: 컬렉션에서 달력을 가져온 다음`Remove` 방법.

### Q4: Aspose.Tasks는 달력을 다른 형식으로 내보내기를 지원합니까?

A4: 예, Aspose.Tasks를 사용하면 달력을 XML, MPP 등과 같은 다양한 형식으로 내보낼 수 있습니다.

### Q5: 달력에서 특정 날짜의 근무 시간을 맞춤 설정할 수 있나요?

A5: 물론 달력의 예외를 사용하여 개별 날짜의 근무 시간을 정의할 수 있습니다.