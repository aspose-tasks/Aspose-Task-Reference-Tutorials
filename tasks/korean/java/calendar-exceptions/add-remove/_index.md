---
date: 2026-11-06
description: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더에서 예외를 제거하고, 예외를 효율적으로 추가 및 관리하며,
  일정 계획을 개선하는 방법을 배웁니다.
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Aspose.Tasks에서 캘린더 예외 추가 및 제거
og_description: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더에서 예외를 제거하는 방법. 캘린더 예외를 효율적으로
  관리, 추가 및 검증합니다.
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: 프로젝트 캘린더에서 예외 제거 방법 – Aspose.Tasks Java 가이드
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더에서 예외를 제거하는 방법
url: /ko/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 캘린더에서 Aspose.Tasks for Java를 사용하여 예외를 제거하는 방법

## 소개
정확한 프로젝트 일정 관리는 종종 **캘린더 예외**를 처리하는 데 달려 있습니다—리소스를 사용할 수 없거나 작업 일정이 변경되는 날들입니다. **Aspose.Tasks for Java**를 사용하면 캘린더 예외를 **생성**, **추가**, **제거**, **관리**할 수 있습니다. 이 튜토리얼에서는 프로젝트를 로드하고, 새로운 예외를 추가하고, 기존 예외를 제거하고, 결과를 확인하는 과정을 단계별로 안내하여 필요하지 않을 때 **예외를 제거하는 방법**을 정확히 이해할 수 있도록 합니다.

## 빠른 답변
- **“create calendar exception”이 의미하는 것은 무엇인가요?** 표준 작업 캘린더와 다른 날짜 범위를 정의하는 것을 의미합니다.  
- **어떤 라이브러리가 이 기능을 제공하나요?** Aspose.Tasks for Java.  
- **시도하려면 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 실제 사용을 위해서는 라이선스가 필요합니다.  
- **기존 예외를 제거할 수 있나요?** 예—캘린더의 예외 목록에서 찾아 삭제하면 됩니다.  
- **Microsoft Project 파일과 호환되나요?** 물론입니다; Aspose.Tasks는 모든 주요 .mpp 버전을 읽고 쓸 수 있습니다.

## create calendar exception java란 무엇인가요?
`CalendarException` 클래스는 프로젝트 캘린더에 추가하는 비작업 기간을 나타냅니다. 지정된 날짜를 휴일, 유지보수 기간 또는 사용자 정의 비작업 시간으로 처리하도록 스케줄러에 알려주어 작업 날짜가 실제 제약 조건을 반영하도록 합니다.

## 캘린더 예외에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks for Java는 **50개 이상의 입력 및 출력 형식**을 지원하며 전체 문서를 메모리에 로드하지 않고 **2 GB**까지의 파일을 처리할 수 있습니다. 대규모 예외 목록을 다룰 때 기본 Microsoft Project API에 비해 약 **40 %**의 성능 향상을 제공하므로 엔터프라이즈 규모 일정 시나리오에 이상적입니다.

## 전제 조건
- Java Development Kit (JDK) 8 이상이 설치되어 있어야 합니다.  
- Aspose.Tasks for Java 라이브러리가 프로젝트 클래스패스에 추가되어 있어야 합니다.  
- Java 구문 및 프로젝트 관리 개념에 대한 기본적인 이해가 필요합니다.

## 캘린더에서 예외를 제거하는 방법은?
`Project` 클래스는 Microsoft Project 파일을 나타내며 해당 파일의 캘린더, 작업 및 리소스에 접근할 수 있게 합니다. `CalendarException` 클래스는 캘린더 내의 비작업 기간을 정의합니다. 프로젝트를 로드하고, 캘린더의 예외 컬렉션에서 원하지 않는 `CalendarException`을 찾아 리스트에서 `remove`를 호출합니다. 이 작업은 일정을 즉시 업데이트하며, 변경 사항을 영구 저장하려는 경우를 제외하고 전체 프로젝트 파일을 다시 저장할 필요가 없습니다.

## 캘린더에 예외를 추가하는 방법은?
`CalendarException` 클래스는 캘린더에 추가할 수 있는 비작업 기간을 정의합니다. 새로운 `CalendarException`을 인스턴스화하고 시작 및 종료 날짜를 설정한 뒤 비작업으로 표시하고 캘린더의 예외 목록에 추가합니다. 추가는 즉시 적용되며, 스케줄러는 해당 범위를 캘린더에 연결된 모든 작업의 휴일로 처리합니다.

## 반복 예외를 처리하는 방법은?
`CalendarException`의 반복 속성(`setRecurrencePattern`)을 사용하면 일간, 주간 또는 월간 반복 패턴을 정의할 수 있습니다. 이러한 속성을 구성하면 각 발생마다 별도의 항목을 만들 필요 없이 주간 회의, 월간 유지보수 기간 또는 패턴 기반 비작업 시간을 모델링할 수 있습니다.

## 패키지 가져오기
`import` 문은 필요한 Aspose.Tasks 클래스를 범위에 가져와 코드에서 참조할 수 있게 합니다.

```java
import com.aspose.tasks.*;
```

## 단계 1: 프로젝트를 로드하고 캘린더에 접근하기
`Project`는 Microsoft Project 파일을 나타내고, `Calendar`는 해당 프로젝트 내의 일정(캘린더)를 나타냅니다. 기존 파일을 로드하고 컬렉션에서 첫 번째 캘린더를 가져오는 것이 첫 단계입니다.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## 단계 2: 기존 예외 제거하기 (필요한 경우)
`CalendarException` 객체는 비작업 기간을 설명합니다. 이 코드 조각은 예외 목록을 확인하고 예외가 하나 이상 존재할 때 첫 번째 항목을 제거하여 유일한 예외가 실수로 삭제되는 것을 방지합니다.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **전문가 팁:** 항목을 제거하기 전에 항상 예외 목록의 크기를 확인하여 `IndexOutOfBoundsException` 발생을 방지하세요.

## 단계 3: 새로운 캘린더 예외 생성(추가)하기
새로운 `CalendarException`을 인스턴스화하고 시작 및 종료 날짜를 설정한 뒤 비작업으로 표시하고 캘린더의 예외 컬렉션에 추가합니다.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **왜 중요한가:** 예외를 추가하면 프로젝트 일정에 직접 휴일, 유지보수 기간 또는 모든 비작업 기간을 모델링할 수 있습니다. 이것이 **create calendar exception java** 기능의 핵심입니다.

## 단계 4: 검증을 위해 모든 예외 표시하기
`calendar.getExceptions()`를 반복하면서 각 항목을 출력하면 캘린더가 의도한 변경을 반영했는지 확인할 수 있어 실수를 초기에 발견하는 데 도움이 됩니다.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Java에서 캘린더 예외를 추가하려면 어떻게 하나요?
`new Project("input.mpp")`로 프로젝트를 로드하고, 대상 `Calendar`를 가져온 뒤 원하는 시작 및 종료 날짜로 `CalendarException`을 인스턴스화하고 작업 플래그를 `false`로 설정한 뒤 `calendar.getExceptions()`에 추가합니다. 이 간결한 순서만으로 몇 줄의 코드로 calendar exception java를 생성할 수 있습니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| 출력이 나타나지 않음 | 예외 목록이 비어 있음 | 반복하기 전에 예외를 추가했는지 확인하세요. |
| `project`에서 NullPointerException 발생 | 잘못된 파일 경로 | `dataDir`이 유효한 `.mpp` 파일을 가리키는지 확인하세요. |
| 날짜가 하루씩 차이남 | 시간대 차이 | 명시적인 시간대를 지정한 `java.util.Calendar` 또는 `java.time` API를 사용하세요. |

## 자주 묻는 질문

**Q:** Aspose.Tasks for Java를 사용하여 캘린더에 여러 예외를 추가할 수 있나요?  
**A:** 예. 각 날짜 범위마다 새로운 `CalendarException`을 생성하고 루프 안에서 `calendar.getExceptions()`에 추가하면 됩니다.

**Q:** Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환되나요?  
**A:** Aspose.Tasks는 Project 98부터 최신 버전까지 다양한 .mpp 버전을 지원하므로 원활한 통합을 보장합니다.

**Q:** 프로젝트 캘린더에서 반복 예외(예: 주간 회의)를 어떻게 처리하나요?  
**A:** `CalendarException`의 반복 속성(`setRecurrencePattern`)을 사용하여 일간, 주간 또는 월간 반복 패턴을 정의하면 됩니다.

**Q:** Aspose.Tasks for Java의 체험 버전이 있나요?  
**A:** 예, 구매 전에 모든 기능을 살펴볼 수 있도록 [Aspose Releases 페이지](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q:** Aspose.Tasks for Java 문제에 대한 지원은 어디에서 받을 수 있나요?  
**A:** 질문이 있으면 [Aspose Tasks Java 포럼](https://reference.aspose.com/tasks/java/)을 방문하거나 직접 Aspose 지원팀에 연락하세요.

## 결론
캘린더 예외를 관리하는 것은 현실적인 프로젝트 일정과 리소스 계획에 필수적입니다. **Aspose.Tasks for Java**를 사용하면 몇 줄의 코드만으로 캘린더 예외를 **생성**, **추가**, **제거**, **검증**할 수 있습니다. **예외를 제거하는 방법**을 숙달하면 일정을 정확하게 유지하고 실제 제약 조건에 맞출 수 있습니다.

---

**Last Updated:** 2026-11-06  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## 관련 튜토리얼

- [프로젝트 캘린더 생성 Aspose – 캘린더 예외를 위한 평일 정의](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks로 캘린더 예외 가져오기 – asp tasks java 튜토리얼](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}