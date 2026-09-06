---
date: 2026-08-18
description: Aspose.Tasks와 함께 Java 프로젝트에서 맞춤형 Calendar Exceptions를 손쉽게 생성하고, MS Project
  캘린더를 통합하며, Calendar Exceptions를 관리·정의·처리·검색합니다. 효율적인 프로젝트 관리를 위해 프로젝트 워크플로를 간소화합니다.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Calendar Exceptions
og_description: Aspose.Tasks를 사용하여 Java에서 Calendar Exceptions를 생성하고, 프로젝트 캘린더를 관리하며,
  비작업일을 설정하는 방법을 배웁니다. 개발자를 위한 빠른 가이드.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java를 사용하여 Calendar Exceptions를 만드는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java를 사용하여 Calendar Exceptions를 만드는 방법
url: /ko/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 캘린더 예외 만들기

## 소개

`Aspose.Tasks`는 Microsoft Project 파일의 프로그래밍 방식 생성, 조작 및 변환을 가능하게 하는 Java 라이브러리입니다. 이 튜토리얼에서는 **캘린더 예외 만들기**—프로젝트의 기본 캘린더를 대체하는 사용자 정의 비작업 기간—에 대해 배웁니다. 작업일 및 비작업일에 대한 정밀한 제어는 정확한 일정 예측, 자원 할당 및 지역 공휴일 준수를 위해 필수적입니다. 이 가이드를 마치면 **MS Project 캘린더를 Java 애플리케이션에 통합**하고 해당 예외를 검색하거나 수정하는 방법도 알게 됩니다.

## 빠른 답변
- **무엇을 달성할 수 있나요?** Java 프로젝트에서 사용자 정의 캘린더 예외를 생성, 수정 및 검색합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 안정 버전).  
- **라이선스가 필요합니까?** 예, 프로덕션 사용을 위해 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **MS Project 파일을 작업할 수 있나요?** 물론입니다 – MS Project 캘린더 데이터를 가져오고, 편집하고, 내보낼 수 있습니다.  
- **특별한 설정이 필요합니까?** Aspose.Tasks JAR 파일을 클래스패스에 추가하고 관련 클래스를 임포트하기만 하면 됩니다.

## Aspose.Tasks for Java에서 사용자 정의 캘린더 예외를 만드는 방법?

`Project` 클래스는 Microsoft Project 파일을 나타내며 해당 내용에 접근할 수 있게 합니다. `Calendar` 객체는 프로젝트의 작업 및 비작업 시간을 정의합니다. `addException()` 메서드는 캘린더에 새로운 캘린더 예외를 추가합니다.

`Project project = new Project("example.mpp")`와 같이 대상 프로젝트를 로드하고, 해당 `Calendar` 객체를 얻은 뒤, 원하는 날짜 범위와 작업 시간 설정을 사용하여 `addException()`을 호출합니다. 이 두 단계 패턴은 새로운 예외를 즉시 생성하고 프로젝트를 저장할 때 지속됩니다. 반복되는 공휴일의 경우, 저장하기 전에 예외에 `RecurrencePattern`을 설정하십시오.

이와 같이 캘린더 예외를 생성하면 **비작업일을 정확히 설정**할 수 있으며, 일회성 중단이나 연간 공휴일 모두에 적용할 수 있습니다. 예외가 추가된 후에는 `project.save("updated.mpp")`를 호출하여 변경 사항을 디스크에 기록할 수 있습니다.

### 단계 개요
1. 프로젝트 파일을 로드합니다.  
2. `Calendar` 인스턴스를 검색하거나 생성합니다.  
3. 예외의 날짜 범위와 작업 시간을 정의합니다.  
4. (선택 사항) 연간 공휴일에 대한 반복을 설정합니다.  
5. 프로젝트를 저장합니다.

## Aspose.Tasks에서 캘린더 예외 관리

[Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently](./add-remove/). 프로젝트 관리에서 유연성은 핵심입니다. Aspose.Tasks는 캘린더 예외를 손쉽게 관리할 수 있게 하여 프로젝트 일정에 동적인 조정을 가능하게 합니다. 이 튜토리얼은 단계별 가이드를 제공하여 과정을 효율적으로 이해하도록 돕습니다. 손쉽게 프로젝트 관리 워크플로를 향상시키는 방법을 알아보세요.

## Aspose.Tasks를 사용하여 캘린더 예외의 평일 정의

[Master the art of defining weekdays for calendar exceptions in Java projects](./define-weekdays/) using Aspose.Tasks. 정확한 프로젝트 일정 수립에는 세심한 주의가 필요합니다. Aspose.Tasks를 사용하면 캘린더 예외의 평일을 정확히 정의할 수 있어 프로젝트가 특정 일정에 원활히 맞춰지도록 할 수 있습니다. 이 튜토리얼은 일정 최적화를 위한 지식을 제공하여 프로젝트 일정에 대한 제어력을 부여합니다.

## Aspose.Tasks를 사용하여 캘린더 예외 발생 처리

[Effectively handle calendar exceptions in Java projects](./handle-occurrences/) with Aspose.Tasks for Java. 프로젝트 관리는 동적인 프로세스로, 예기치 않은 상황에 대한 조정이 자주 필요합니다. Aspose.Tasks는 캘린더 예외를 효과적으로 처리할 수 있게 하여 프로젝트 관리에 효율적인 접근 방식을 제공합니다. 이 상세 튜토리얼을 통해 프로젝트 불확실성을 손쉽게 관리하는 방법을 배워보세요.

## Aspose.Tasks를 사용하여 캘린더 예외 검색

[Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java](./retrieve/). Aspose.Tasks를 사용하면 캘린더 예외를 프로젝트 관리 프로세스에 원활히 통합할 수 있습니다. 이 튜토리얼은 캘린더 예외를 검색하는 단계별 과정을 안내하여 프로젝트에 부드럽고 효율적으로 통합할 수 있도록 합니다. Aspose.Tasks의 강력함을 활용하여 프로젝트 관리 역량을 강화하세요.

## Aspose.Tasks와 MS Project 캘린더를 통합하는 방법?

`Project` 클래스는 Microsoft Project 파일을 로드하여 해당 캘린더와 기타 프로젝트 데이터를 노출합니다. `new Project("source.mpp")`를 사용해 기존 MS Project 파일을 가져오면 라이브러리가 자동으로 기본 캘린더와 모든 사용자 정의 예외를 로드합니다. 그런 다음 예외를 읽고, 수정하거나 병합한 뒤 프로젝트를 디스크에 저장할 수 있습니다. 이 방법을 사용하면 **MS Project 캘린더** 데이터를 프로그래밍 방식으로 수정할 수 있어 MS Project UI에서 수동으로 편집할 필요가 없습니다.

## 일반적인 사용 사례
- **Holiday scheduling** – 여러 프로젝트에 걸쳐 국가 공휴일을 비작업일로 정의합니다.  
- **Shift work** – 비표준 일정으로 운영되는 팀을 위해 사용자 정의 작업 주를 설정합니다.  
- **Project phase gating** – 유지 보수 창과 같이 작업이 예약되지 않아야 하는 기간을 차단합니다.  
- **Legacy migration** – 오래된 MS Project 파일에서 캘린더를 가져와 프로그래밍 방식으로 조정합니다.

## 팁 및 모범 사례
- **Pro tip:** 새 예외를 추가하기 전에 항상 기존 캘린더를 검색하여 중복을 방지하십시오.  
- **Warning:** 이미 작업에 할당된 캘린더를 변경하면 작업 날짜가 이동할 수 있으므로 수정 후 일정을 다시 계산하십시오.  
- **Performance:** 파일 I/O 오버헤드를 줄이기 위해 여러 예외 업데이트를 하나의 트랜잭션으로 배치하십시오. Aspose.Tasks는 전체 문서를 메모리에 로드하지 않고도 500 MB까지의 파일을 처리하며, 일반 서버 하드웨어에서 초당 50개 이상의 캘린더 관련 API 호출을 처리합니다.

## 캘린더 예외 튜토리얼
### [Aspose.Tasks에서 캘린더 예외 관리](./add-remove/)
Aspose.Tasks for Java에서 캘린더 예외를 효율적으로 추가하고 제거하는 방법을 배우세요. 프로젝트 관리 워크플로를 손쉽게 향상시킵니다.
### [Aspose.Tasks를 사용하여 캘린더 예외의 평일 정의](./define-weekdays/)
Aspose.Tasks를 사용해 Java 프로젝트에서 캘린더 예외의 평일을 정의하는 방법을 배우고 정확한 프로젝트 일정을 수립하세요.
### [Aspose.Tasks를 사용하여 캘린더 예외 발생 처리](./handle-occurrences/)
Aspose.Tasks for Java를 사용해 Java 프로젝트에서 캘린더 예외를 효과적으로 처리하는 방법을 배우고 프로젝트 관리 프로세스를 지금 바로 간소화하세요.
### [Aspose.Tasks를 사용하여 캘린더 예외 검색](./retrieve/)
Aspose.Tasks for Java를 사용해 MS Project에서 캘린더 예외를 검색하는 방법을 배우고 원활한 통합을 위한 단계별 튜토리얼을 확인하세요.

## 자주 묻는 질문

**Q: 프로젝트가 이미 배포된 후에도 캘린더 예외를 수정할 수 있나요?**  
A: 예. add‑remove 및 define‑weekdays API를 사용해 캘린더를 업데이트한 뒤 프로젝트 파일을 다시 저장하면 됩니다.

**Q: Aspose.Tasks가 반복 예외(예: 매월 첫 번째 월요일)를 지원하나요?**  
A: 물론입니다. “handle occurrences” 튜토리얼에서 반복 패턴 설정 방법을 다룹니다.

**Q: 내 사용자 정의 캘린더가 프로젝트의 모든 작업에 사용되도록 하려면 어떻게 해야 하나요?**  
A: 캘린더를 프로젝트의 기본 캘린더에 할당하거나 각 작업의 `Calendar` 속성에 명시적으로 설정하면 됩니다.

**Q: 여러 MS Project 파일의 캘린더를 병합할 수 있나요?**  
A: 예. 각 캘린더를 검색하고 예외를 프로그래밍 방식으로 결합한 뒤, 병합된 캘린더를 대상 프로젝트에 할당하면 됩니다.

**Q: 이러한 기능을 사용하려면 어떤 버전의 Aspose.Tasks가 필요합니까?**  
A: 모든 기능은 현재 안정 버전인 Aspose.Tasks for Java (2025.x)에서 제공됩니다.

---

**마지막 업데이트:** 2026-08-18  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose

## 관련 튜토리얼

- [프로젝트 캘린더 생성 Aspose – 캘린더 예외를 위한 평일 정의](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks로 캘린더 예외 검색 – asp tasks java 튜토리얼](/tasks/java/calendar-exceptions/retrieve/)
- [Java용 Aspose 캘린더 예외 생성](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}