---
date: 2026-08-08
description: Aspose.Tasks for Java를 사용하여 Java 캘린더 예외를 만드는 방법을 배우고, 예외를 효율적으로 추가 및
  제거하며, 프로젝트 일정 관리를 개선하세요.
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: Aspose.Tasks에서 캘린더 예외 추가 및 제거
og_description: Aspose.Tasks for Java를 사용하여 Java 캘린더 예외를 만드는 방법을 배우세요. Microsoft Project
  파일에서 캘린더 예외를 효율적으로 추가, 제거 및 검증할 수 있습니다.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Aspose.Tasks를 사용한 Java 캘린더 예외 만들기 – 빠른 가이드
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks를 사용한 Java 캘린더 예외 생성
url: /ko/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 Java 캘린더 예외 만들기

## 소개
정확한 프로젝트 일정 관리는 종종 **calendar exceptions**—리소스가 사용 불가능하거나 작업 일정이 변경되는 날들을 처리하는 데 달려 있습니다. **Aspose.Tasks for Java**를 사용하면 **create calendar exception java** 객체를 만들고, 프로젝트 캘린더에 추가하거나 더 이상 필요하지 않을 때 제거할 수 있습니다. 이 튜토리얼에서는 프로젝트 파일을 로드하는 것부터 관리한 예외를 검증하는 전체 과정을 단계별로 안내합니다. Java 환경에서 **create calendar exception java**를 정확히 어떻게 수행하는지와 현실적인 일정에 왜 중요한지 확인할 수 있습니다.

## 빠른 답변
- **What does “create calendar exception” mean?** 표준 작업 캘린더와 다른 날짜 범위를 정의하는 것을 의미합니다.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** 무료 체험판을 사용할 수 있으며, 프로덕션 사용을 위해서는 라이선스가 필요합니다.  
- **Can I remove an existing exception?** 예—캘린더의 예외 목록에서 찾아 삭제하면 됩니다.  
- **Is this compatible with Microsoft Project files?** 물론입니다; Aspose.Tasks는 모든 주요 .mpp 버전을 읽고 쓸 수 있습니다.

## create calendar exception java란 무엇인가요?
calendar exception java는 Aspose.Tasks의 Java API를 사용하여 프로젝트 캘린더에 비작업 기간을 추가합니다. 이는 지정된 날짜를 휴일, 유지보수 기간 또는 기타 사용자 정의 비작업 시간으로 처리하도록 스케줄러에 알려주어 작업 날짜가 실제 제약 조건 및 리소스 가용성을 반영하도록 합니다.

## 캘린더 예외에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks for Java는 30개 이상의 프로젝트 파일 형식을 지원하며 전체 문서를 메모리에 로드하지 않고도 최대 2 GB 파일을 처리할 수 있습니다. 대규모 예외 목록을 처리할 때 기본 Microsoft Project API보다 약 40 %의 성능 향상을 제공하여 빠르고 신뢰할 수 있는 캘린더 조작이 필요한 엔터프라이즈 규모 일정 시나리오에 이상적입니다.

## 전제 조건
- Java Development Kit (JDK) 8 이상이 설치되어 있어야 합니다.  
- Aspose.Tasks for Java 라이브러리를 프로젝트 클래스패스에 추가했습니다.  
- Java 구문 및 프로젝트 관리 개념에 대한 기본적인 이해가 필요합니다.

## Aspose.Tasks로 calendar exception java 만들기
프로젝트를 로드하고, 캘린더를 조작하며, 변경 사항을 검증합니다—명확한 코드와 간결한 설명을 결합한 몇 단계만으로 가능합니다.

## 패키지 가져오기
`import` 문은 필요한 Aspose.Tasks 클래스를 범위에 가져와 코드에서 참조할 수 있게 합니다.

```java
import com.aspose.tasks.*;
```

## 단계 1: 프로젝트를 로드하고 캘린더에 접근하기
`Project` 클래스는 Microsoft Project 파일을 나타내고, `Calendar`는 해당 프로젝트 내의 일정을 나타냅니다. 기존 파일을 로드하고 컬렉션에서 첫 번째 캘린더를 가져옵니다.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## 단계 2: 기존 예외 제거 (필요한 경우)
`CalendarException` 객체는 비작업 기간을 설명합니다. 이 코드 조각은 예외 목록을 확인하고 예외가 하나 이상 있을 때 첫 번째 항목을 제거하여 유일한 예외가 실수로 삭제되는 것을 방지합니다.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** 항목을 제거하기 전에 항상 예외 목록의 크기를 확인하여 `IndexOutOfBoundsException`을 방지하세요.

## 단계 3: 새로운 캘린더 예외 만들기 (추가)
새로운 `CalendarException`을 인스턴스화하고, 시작 및 종료 날짜를 설정한 뒤 비작업으로 표시하고, 캘린더의 예외 컬렉션에 추가합니다.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** 예외를 추가하면 프로젝트 일정에 직접 휴일, 유지보수 기간 또는 기타 비작업 기간을 모델링할 수 있습니다. 이는 **create calendar exception java** 기능의 핵심입니다.

## 단계 4: 검증을 위해 모든 예외 표시
`calendar.getExceptions()`를 반복하면서 각 항목을 출력하면 캘린더가 의도한 변경을 반영했는지 확인할 수 있어 실수를 초기에 발견하는 데 도움이 됩니다.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Java에서 캘린더 예외를 어떻게 추가하나요?
`new Project("input.mpp")`로 프로젝트를 로드하고, 대상 `Calendar`를 가져온 뒤 원하는 시작 및 종료 날짜로 `CalendarException`을 인스턴스화하고, 작업 플래그를 `false`로 설정한 뒤 `calendar.getExceptions()`에 추가합니다. 이 간결한 순서만으로 몇 줄의 코드로 calendar exception java를 생성할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|-------|-------|-----|
| 출력이 나타나지 않음 | 예외 목록이 비어 있음 | 반복하기 전에 예외를 추가했는지 확인하세요. |
| `project`에서 `NullPointerException` | 잘못된 파일 경로 | `dataDir`이 유효한 `.mpp` 파일을 가리키는지 확인하세요. |
| 날짜가 하루씩 차이남 | 시간대 차이 | 명시적인 시간대를 지정한 `java.util.Calendar` 또는 `java.time` API를 사용하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용하여 캘린더에 여러 예외를 추가할 수 있나요?**  
A: 예. 각 날짜 범위마다 새로운 `CalendarException`을 생성하고 루프 내에서 `calendar.getExceptions()`에 추가하면 됩니다.

**Q: Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환되나요?**  
A: Aspose.Tasks는 Project 98부터 최신 릴리스까지 다양한 .mpp 버전을 지원하므로 원활한 통합을 보장합니다.

**Q: 프로젝트 캘린더에서 반복 예외(예: 주간 회의)를 어떻게 처리할 수 있나요?**  
A: `CalendarException`의 반복 속성(`setRecurrencePattern`)을 사용하여 일간, 주간 또는 월간 반복 패턴을 정의합니다.

**Q: Aspose.Tasks for Java의 체험 버전이 있나요?**  
A: 예, 구매 전에 모든 기능을 살펴볼 수 있도록 [website](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java 문제에 대한 지원은 어디서 받을 수 있나요?**  
A: [website](https://reference.aspose.com/tasks/java/)에 있는 Aspose.Tasks Java 포럼을 방문해 질문하거나, 직접 Aspose 지원팀에 연락하세요.

## 결론
캘린더 예외를 관리하는 것은 현실적인 프로젝트 일정 및 리소스 계획에 필수적입니다. **Aspose.Tasks for Java**를 사용하면 **create calendar exception java** 객체를 만들고, 모든 프로젝트 캘린더에 추가하며, 더 이상 필요하지 않을 때 제거할 수 있습니다—몇 줄의 코드만으로 가능합니다. **create calendar exception java** 기능을 통해 실제 제약 조건을 반영한 일정을 구축할 수 있습니다.

---

**마지막 업데이트:** 2026-08-08  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose

## 관련 튜토리얼

- [프로젝트 캘린더 만들기 Aspose – 캘린더 예외를 위한 평일 정의](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks로 캘린더 예외 가져오기 – asp tasks java 튜토리얼](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}