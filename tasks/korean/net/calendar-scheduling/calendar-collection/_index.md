---
date: 2026-04-13
description: Aspose.Tasks for .NET에서 작업 시간을 설정하고 캘린더 컬렉션을 관리하는 방법을 배워보세요. Microsoft
  Project의 캘린더를 가져오고, 캘린더 프로젝트를 제거하며, 이름으로 캘린더를 쉽게 가져올 수 있습니다.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Aspose.Tasks에서 캘린더 컬렉션 관리
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks 캘린더 컬렉션에서 작업 시간 설정
url: /ko/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 캘린더 컬렉션에서 작업 시간 설정

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 **작업 시간 설정**하고 캘린더 컬렉션을 관리하는 방법을 배웁니다. 캘린더는 작업일, 휴일 및 예외를 정의하므로 이를 마스터하면 프로젝트 일정을 정확하게 제어할 수 있습니다. 또한 Microsoft Project에서 캘린더를 가져오고, 프로젝트에서 캘린더를 제거하고, 이름으로 캘린더를 가져오는 방법도 보여줍니다.

## 빠른 답변
- **캘린더의 기본 클래스는 무엇입니까?** `Project.Calendars` collection.
- **작업 시간을 어떻게 설정합니까?** Create or modify a `Calendar` object and define its `WorkingTime`.
- **Microsoft Project에서 캘린더를 가져올 수 있습니까?** Yes – load an MPP file and access its calendars.
- **프로젝트에서 캘린더를 제거하려면 어떻게 합니까?** Use `Project.Calendars.Remove(calendar)`.
- **이름으로 캘린더를 검색하려면 어떻게 합니까?** Call `Project.Calendars.GetByName("YourCalendar")`.

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. Visual Studio: .NET 개발을 위한 Visual Studio 또는 기타 호환 IDE를 설치하십시오.  
2. Aspose.Tasks for .NET: [here](https://releases.aspose.com/tasks/net/)에서 Aspose.Tasks for .NET을 다운로드하고 설치하십시오.  
3. C# 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

먼저, Aspose.Tasks와 작업하기 위해 필요한 네임스페이스를 가져오겠습니다:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## 새 캘린더 만들기

### 단계 1: 새 `Project` 객체를 초기화합니다.
```csharp
var project = new Project();
```

### 단계 2: 프로젝트의 캘린더 컬렉션에 캘린더를 추가합니다.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 단계 3: 캘린더를 반복하고 이름을 표시합니다.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 캘린더의 작업 시간을 설정하는 방법은?

**작업 시간을** 설정하려면 `Calendar`의 `WorkingTime` 컬렉션을 수정합니다.  
예를 들어, 표준 9시부터 17시까지의 작업일을 정의하거나 사용자 지정 예외를 추가할 수 있습니다.  
이 코드는 나중에 표준 캘린더를 만들 때 보여지는 예제와 동일합니다.

## 새 캘린더로 기존 캘린더 교체

### 단계 1: 기존 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 단계 2: 기존 캘린더를 제거합니다 (존재하는 경우).  
이는 **캘린더 제거 프로젝트** 시나리오를 보여줍니다.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 단계 3: 새 캘린더를 추가합니다.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 이름 또는 ID로 캘린더 가져오기

### 단계 1: 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 단계 2: 이름 또는 UID로 캘린더를 검색합니다.  
이는 **이름으로 캘린더 가져오기** 작업을 보여줍니다.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 단계 3: 캘린더 세부 정보를 표시합니다.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## 캘린더 반복

### 단계 1: 프로젝트를 로드합니다.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 단계 2: 캘린더 수를 가져옵니다.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 단계 3: 캘린더 컬렉션을 반복하고 이름을 표시합니다.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 표준 캘린더 만들기

### 단계 1: 새 프로젝트를 초기화합니다.
```csharp
var project = new Project();
```

### 단계 2: 새 캘린더를 정의하고 표준으로 설정합니다.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 단계 3: 프로젝트를 저장합니다.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책

- **`GetByName` 사용 시 캘린더를 찾을 수 없음** – 캘린더를 추가할 때 사용한 정확한 이름과 대소문자가 일치하는지 확인하십시오.  
- **작업 시간이 적용되지 않음** – `WorkingTime`을 설정한 후 프로젝트를 저장해야 합니다; 그렇지 않으면 변경 사항이 메모리 내에만 남습니다.  
- **MPP 파일에서 캘린더 가져오기 실패** – 소스 파일이 유효한 Microsoft Project 파일인지 및 읽기 권한이 있는지 확인하십시오.

## FAQ

### Q1: Aspose.Tasks에서 사용자 지정 작업일을 만들 수 있습니까?
A1: 예, 캘린더에 예외를 추가하여 사용자 지정 작업일을 만들 수 있습니다.

### Q2: Microsoft Project 파일에서 캘린더를 가져올 수 있습니까?
A2: 물론입니다. Aspose.Tasks는 Microsoft Project 파일에서 캘린더 가져오기를 지원합니다.

### Q3: 프로젝트에서 특정 캘린더를 어떻게 제거할 수 있습니까?
A3: 컬렉션에서 캘린더를 가져온 다음 `Remove` 메서드를 호출하여 캘린더를 제거할 수 있습니다.

### Q4: Aspose.Tasks가 캘린더를 다양한 형식으로 내보내는 것을 지원합니까?
A4: 예, Aspose.Tasks는 XML, MPP 등 다양한 형식으로 캘린더를 내보낼 수 있습니다.

### Q5: 캘린더의 특정 날짜에 대한 작업 시간을 사용자 지정할 수 있습니까?
A5: 물론입니다. 캘린더의 예외를 사용하여 개별 날짜에 대한 작업 시간을 정의할 수 있습니다.

## 자주 묻는 질문

**Q: 24시간 교대 캘린더를 설정하는 가장 좋은 방법은 무엇입니까?**  
A: 새 캘린더를 만들고 기존 `WorkingTime` 항목을 지운 다음 각 평일에 대해 00:00부터 24:00까지의 단일 `WorkingTime` 범위를 추가합니다.

**Q: 캘린더를 한 프로젝트에서 다른 프로젝트로 복사할 수 있습니까?**  
A: 예—`project.Save`를 사용하여 캘린더를 XML로 내보낸 다음 `new Project(xmlPath)`로 다른 프로젝트에 가져옵니다.

**Q: Microsoft Project에서 프로그래밍 방식으로 캘린더를 가져오려면 어떻게 해야 합니까?**  
A: `new Project("source.mpp")`로 MPP 파일을 로드하면 캘린더가 `project.Calendars`를 통해 사용 가능해집니다.

**Q: 프로젝트의 캘린더 수에 제한이 있습니까?**  
A: 실질적으로 제한은 없습니다; 컬렉션은 메모리가 허용하는 만큼 많은 캘린더를 보유할 수 있지만 성능을 위해 목록을 관리 가능한 수준으로 유지하십시오.

**Q: 캘린더에 대한 변경 사항이 해당 캘린더를 사용하는 작업에 자동으로 업데이트됩니까?**  
A: 예—프로젝트를 저장한 후 캘린더에 연결된 작업은 업데이트된 작업 시간을 반영합니다.

---

**마지막 업데이트:** 2026-04-13  
**테스트 대상:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}