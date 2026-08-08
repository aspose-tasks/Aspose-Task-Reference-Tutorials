---
date: 2026-08-08
description: Aspose.Tasks for Java를 사용하여 캘린더 ms project 설정, 일일 작업 시간 지정, 주말 작업일 추가
  방법을 배웁니다. 몇 줄의 코드만으로 프로젝트를 XML로 저장할 수 있습니다.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: 캘린더 ms project 설정 및 평일 정의 방법
og_description: Aspose.Tasks for Java를 사용하여 캘린더 ms project 설정, 평일 정의 및 주말 작업일 추가.
  단계별 튜토리얼을 따라 XML로 저장하세요.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks로 캘린더 ms project 설정 – Java 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: 캘린더 ms project 설정 및 평일 정의 방법
url: /ko/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 캘린더 설정 및 평일 정의 방법

이 튜토리얼에서는 **how to set calendar ms project** 를 프로그래밍 방식으로 수행하고, 평일을 정의하며, Aspose.Tasks for Java 라이브러리를 사용하여 사용자 정의 근무일을 구성하는 방법을 배웁니다. 일정 엔진을 구축하거나 ERP 시스템과 통합하거나 Microsoft Project를 열지 않고 프로젝트 계획을 생성해야 할 경우, 아래 단계에서는 캘린더를 만들고, 일일 근무 시간을 설정하고, 주말 근무일을 추가하는 방법을 몇 줄의 코드로 보여줍니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Tasks for Java.  
- **주말 근무일을 추가할 수 있나요?** 예 – 토요일과 일요일을 근무일로 표시하면 됩니다.  
- **프로젝트를 어떻게 저장하나요?** `prj.save(..., SaveFileFormat.Xml)` 를 호출합니다.  
- **라이선스가 필요합니까?** 평가용으로는 무료 체험판을 사용할 수 있지만, 실제 운영에서는 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.

## set calendar ms project란 무엇인가요?
MS Project에서 캘린더를 설정하면 어떤 날이 근무일로 간주되는지, 하루의 근무 시간 수, 그리고 휴일이나 전사적 휴무와 같은 특수 예외를 정의합니다. 이러한 정보는 작업 일정, 리소스 할당 및 전체 프로젝트 일정에 영향을 미쳐 계산이 조직의 실제 근무 패턴을 반영하도록 합니다.

## 캘린더 조작에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks는 Microsoft Project UI를 실행하지 않고도 캘린더를 프로그래밍 방식으로 제어할 수 있게 해줍니다. Java를 지원하는 모든 운영 체제에서 실행되며, 50개 이상의 입력 및 출력 형식을 지원하고, 전체 파일을 메모리에 로드하지 않고도 수백 페이지에 달하는 프로젝트를 처리할 수 있어 서버 측 자동화에 이상적입니다.

## 필수 조건
- **Java Development Kit (JDK) 8+** – [Oracle 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드합니다.  
- **Aspose.Tasks for Java** – [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 최신 JAR를 얻습니다.  
- 클래스패스에 Aspose.Tasks JAR를 추가할 수 있는 IDE 또는 빌드 도구(Maven/Gradle).

## 패키지 가져오기
프로젝트, 캘린더 및 작업 시간 객체에 접근할 수 있는 클래스를 가져옵니다.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 단계별 가이드

### Step 1: 프로젝트 인스턴스 생성
`Project` 객체를 인스턴스화합니다. 이 객체는 조작할 MS Project 파일을 나타냅니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: 새 캘린더 정의
`Calendar`는 프로젝트의 작업 시간, 예외 및 휴일 집합을 나타냅니다.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: 표준 근무일 추가 (월요일‑목요일)
`WeekDay`는 특정 요일에 대한 작업 시간을 정의합니다.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: 주말 근무일 추가
프로젝트가 주말에도 진행된다면 토요일과 일요일을 일반 근무일로 추가합니다. 이는 **add weekend working days** 를 보여줍니다.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: 맞춤형 짧은 근무일 설정 (금요일)
금요일을 오전 근무(오전 9시‑오후 12시)와 오후 근무(오후 1시‑오후 4시)로 구성하여 **set daily working hours** 와 맞춤형 짧은 근무일을 예시합니다.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Step 6: 프로젝트를 XML로 저장
`SaveFileFormat`은 프로젝트를 저장할 때 지원되는 파일 형식(예: XML 또는 MPP)을 열거합니다.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **Working times not applied** | `setDayWorking(true)` 가 각 사용자 정의 `WeekDay`에 호출되었는지 확인합니다. |
| **File not found when saving** | `dataDir`이 존재하는 폴더를 가리키고 애플리케이션에 쓰기 권한이 있는지 확인합니다. |
| **Calendar not reflected in tasks** | `task.setCalendar(cal)` 을 사용하여 새로 만든 캘린더를 리소스 또는 작업에 할당합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용하여 사용자 정의 비근무일을 정의할 수 있나요?**  
A: 예. 비근무일로 지정하려는 `WeekDay`에 대해 `DayWorking` 속성을 `false` 로 설정합니다.

**Q: 휴일이나 전사적 예외를 어떻게 추가하나요?**  
A: `CalendarException` 객체를 생성하고 예외 날짜를 지정한 뒤 `cal.getExceptions()`에 추가합니다.

**Q: 라이브러리가 이전 MS Project 버전과 호환되나요?**  
A: 물론입니다. Aspose.Tasks는 여러 Project 버전에서 MPP, MPT 및 XML 형식을 지원합니다.

**Q: 가져온 프로젝트에서 기존 캘린더를 수정할 수 있나요?**  
A: `new Project("existing.mpp")` 로 프로젝트를 로드하고, 원하는 캘린더를 가져와 변경한 뒤 저장합니다.

**Q: Aspose.Tasks가 반복 작업도 처리하나요?**  
A: 예, `RecurringTask` 클래스를 사용하여 반복 작업을 생성하고 편집할 수 있습니다.

## 결론
이제 **how to set calendar ms project** 를 수행하고, 평일을 정의하며, 주말 근무일을 추가하고, 짧은 금요일 일정을 구성하는 방법을 알게 되었습니다—모두 Aspose.Tasks for Java를 사용합니다. 결과를 XML로 저장하고 캘린더 로직을 모든 Java 기반 프로젝트 관리 솔루션에 통합할 수 있습니다.

---

**마지막 업데이트:** 2026-08-08  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용하여 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose.Tasks로 작업일 및 작업시간 결정](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks로 캘린더에 휴일 추가 및 MPP로 저장](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}