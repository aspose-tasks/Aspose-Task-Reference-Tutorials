---
date: 2026-07-29
description: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더를 만들고, 평일 예외를 정의하고, 휴일 일정을 관리함으로써
  비근무일을 일정에 포함하는 방법을 배웁니다.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: 비근무일 일정 잡기 – 프로젝트 캘린더 만들기 Aspose
og_description: Aspose.Tasks for Java를 사용하여 비근무일을 일정에 포함합니다. 평일을 정의하고, 캘린더 예외를 추가하며,
  휴일 일정을 효율적으로 관리하는 방법을 배웁니다.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: 비근무일 일정 잡기 – 프로젝트 캘린더 만들기 Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: 비근무일 일정 잡기 – 프로젝트 캘린더 만들기 Aspose
url: /ko/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 비근무일 일정 – Aspose 프로젝트 캘린더 만들기

### 소개
프로젝트에서 **비근무일을 일정에 포함**해야 할 때, 휴일, 특수 근무조, 또는 일시적인 폐쇄를 프로젝트 계획에 직접 모델링할 수 있어야 합니다. Aspose.Tasks for Java는 캘린더 정의에 대한 완전한 제어를 제공하여 실제 일정과 일치하는 예외를 추가할 수 있게 합니다. 이 튜토리얼에서는 캘린더 예외에 대한 평일을 정의하는 정확한 단계를 안내하므로 프로젝트 일정이 정확하고 신뢰할 수 있게 유지됩니다. 마지막까지 읽으면 이러한 방법이 모든 기업 프로젝트의 포괄적인 **비근무일 일정** 전략에 어떻게 적용되는지도 확인할 수 있습니다.

## 빠른 답변
- **“비근무일 일정”이란 무엇을 의미합니까?**  
  Aspose.Tasks를 사용하여 특정 날짜를 비근무일로 표시하는 캘린더를 생성하고, 이를 통해 작업 날짜가 자동으로 영향을 받게 하는 것을 의미합니다.  
- **샘플을 실행하려면 라이선스가 필요합니까?**  
  개발용으로는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 IDE는 무엇입니까?**  
  IntelliJ IDEA, Eclipse, NetBeans 또는 Java 8+를 지원하는 모든 IDE.  
- **같은 캘린더에 여러 예외를 추가할 수 있습니까?**  
  예 – 필요에 따라 원하는 만큼 `CalendarException` 객체를 추가할 수 있습니다.  
- **프로젝트를 저장할 수 있는 파일 형식은 무엇입니까?**  
  XML, MPP 및 Aspose.Tasks에서 지원하는 여러 다른 형식.

## Aspose.Tasks에서 프로젝트 캘린더란?
**프로젝트 캘린더**는 Aspose.Tasks의 최상위 객체로, 프로젝트의 작업 일과 시간을 정의합니다. 이는 작업 시작/종료 날짜, 리소스 할당 및 전체 일정 계산에 직접적인 영향을 미칩니다. 캘린더를 사용자 정의하면 회사 휴일이나 주말 근무 정책과 같은 실제 제약 조건을 일정이 준수하도록 할 수 있습니다.

## 캘린더 예외에 대한 평일을 정의하는 이유는?
평일 예외를 정의하면 프로젝트 엔진이 해당 일자를 비근무일로 처리하도록 보장되어, 작업이 자동으로 그날에 배정되는 것을 방지하고 일정이 휴일, 유지보수 창 또는 조직 전체의 특수 근무 패턴과 같은 실제 제약 조건에 맞게 정렬됩니다.

- **정확한 일정:** 작업이 휴일이나 차단 기간에 배정되지 않습니다.  
- **리소스 계획:** 리소스가 유효한 작업일에만 할당되어 과다 할당을 방지합니다.  
- **규정 준수:** 일정이 조직 정책이나 법정 휴일 캘린더를 자동으로 따릅니다.  

## 캘린더 예외를 이용한 비근무일 일정
**비근무일 일정**을 관리할 때 일반적으로 휴일, 유지보수 창 또는 기타 차단 기간의 마스터 리스트가 있습니다. 이러한 날짜를 `CalendarException` 객체로 추가하면, 크리티컬 경로 분석이든 리소스 레벨링이든 모든 계산이 자동으로 해당 제약을 존중합니다. 이 접근 방식은 수동 날짜 조정을 없애고 일정 변동 위험을 줄여줍니다.

## 전제 조건
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 공식 [Aspose.Tasks Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans 또는 Java와 호환되는 모든 편집기.  

## 캘린더 예외를 사용하여 비근무일을 일정에 포함하는 방법

프로젝트를 로드하고, 사용자 정의 캘린더를 만든 뒤, 원하는 평일을 비근무일로 표시하는 `CalendarException` 객체를 추가합니다. 이 전체 과정은 몇 단계만으로 완료할 수 있으며, 결과 캘린더는 모든 작업 일정 로직에 자동으로 영향을 미칩니다.

### 단계별 가이드

### 단계 1: 필요한 패키지 가져오기
프로젝트에 필요한 핵심 Aspose.Tasks 클래스와 날짜 처리를 위한 Java의 `GregorianCalendar`가 필요합니다.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### 단계 2: 데이터 디렉터리 정의
생성된 프로젝트 파일이 저장될 위치를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 3: 프로젝트 인스턴스 생성
`Project`는 작업, 리소스 및 캘린더를 포함한 모든 프로젝트 데이터를 보유하는 주요 객체입니다.

```java
Project project = new Project();
```

### 단계 4: 캘린더 정의
`Calendar`는 프로젝트 내 작업 및 비작업 시간의 일정을 나타냅니다.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 단계 5: 평일 예외 정의
`CalendarException`은 캘린더에서 비근무일로 표시되는 기간을 나타냅니다.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### 단계 6: 프로젝트 저장
사용자 정의 캘린더와 그 예외를 포함한 프로젝트를 XML 파일로 영구 저장합니다.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **예외 날짜가 적용되지 않음** | `setEnteredByOccurrences(false)`와 올바른 `FromDate/ToDate` 값을 확인하십시오. |
| **저장된 파일이 비어 있음** | `dataDir`이 쓰기 가능한 폴더를 가리키는지, 파일 이름이 `.xml`로 끝나는지 확인하십시오. |
| **캘린더가 작업 일정에 반영되지 않음** | `task.setCalendar(cal)` 또는 `resource.setCalendar(cal)`을 사용하여 작업이나 리소스에 캘린더를 할당하십시오. |

## 자주 묻는 질문

**Q: 같은 캘린더에 다른 평일에 대한 여러 예외를 정의할 수 있습니까?**  
A: 예. 각기 다른 기간이나 규칙에 대해 `cal.getExceptions()`에 추가 `CalendarException` 객체를 추가하면 됩니다.

**Q: Aspose.Tasks for Java는 다양한 Java IDE와 호환됩니까?**  
A: 물론입니다. 이 라이브러리는 IntelliJ IDEA, Eclipse, NetBeans 및 표준 Java 프로젝트를 지원하는 모든 IDE에서 작동합니다.

**Q: 일일 예외 외에 다른 유형의 예외를 사용자 정의할 수 있습니까?**  
A: 예. `CalendarExceptionType.Weekly`, `Monthly` 또는 `Yearly`를 사용하여 필요에 맞는 일정 유형을 지정할 수 있습니다.

**Q: 프로젝트 요구 사항에 따라 예외를 동적으로 처리하려면 어떻게 해야 합니까?**  
A: 예외 객체를 프로그래밍 방식으로 생성하십시오—예를 들어 데이터베이스나 설정 파일에서 휴일 날짜를 읽어와 루프에서 `CalendarException` 인스턴스를 만들 수 있습니다.

**Q: Aspose.Tasks for Java용 체험 버전이 제공됩니까?**  
A: 예, 무료 체험판을 [Aspose.Tasks Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 결론
이 단계를 따라 하면 **비근무일을 일정에 포함**하는 방법을 알게 되며, 프로젝트 캘린더를 만들고 평일 예외를 정의하여 휴일이나 특수 비근무 기간을 정확히 반영할 수 있습니다. 적절한 캘린더 구성은 현실적인 일정, 리소스 할당 및 전체 프로젝트 성공에 필수적입니다. 사용자 정의 캘린더를 작업이나 리소스에 연결하고 다른 예외 유형을 실험하여 모든 프로젝트에 대한 포괄적인 **비근무일 일정**을 구축해 보세요.

---

**마지막 업데이트:** 2026-07-29  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose for Java에서 캘린더 예외 만들기](/tasks/java/calendar-exceptions/add-remove/)
- [Aspose.Tasks를 사용하여 MS Project에서 캘린더 설정 및 평일 정의 방법](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}