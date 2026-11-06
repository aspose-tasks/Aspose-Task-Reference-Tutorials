---
date: 2026-11-06
description: Aspose.Tasks를 사용하여 Java 프로젝트에서 맞춤형 캘린더 예외를 손쉽게 만들고, MS Project 캘린더를 통합하며,
  캘린더 예외를 관리, 정의, 처리 및 검색합니다. 효율적인 프로젝트 관리를 위해 프로젝트 워크플로를 간소화합니다.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: 캘린더 예외
og_description: Aspose.Tasks를 사용하여 Java에서 캘린더 예외를 만드는 방법을 배웁니다. 프로젝트 캘린더를 관리하고, 비작업일을
  설정하며, MS Project 캘린더를 효율적으로 수정합니다.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Aspose.Tasks for Java와 함께 캘린더 예외 만들기
schemas:
- author: Aspose
  dateModified: '2026-11-06'
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
title: Aspose.Tasks for Java와 함께 캘린더 예외 만들기
url: /ko/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 캘린더 예외 만들기

## 소개

`Aspose.Tasks`는 Microsoft Project 파일을 프로그래밍 방식으로 생성, 조작 및 변환할 수 있게 해주는 Java 라이브러리입니다. 이 튜토리얼에서는 **캘린더 예외**—프로젝트 기본 캘린더를 무시하는 사용자 정의 비작업 기간—를 만드는 방법을 배웁니다. 작업일과 비작업일을 정확히 제어하는 것은 일정 예측, 리소스 할당 및 지역 공휴일 준수에 필수적입니다. 이 가이드를 마치면 **MS Project 캘린더**를 Java 애플리케이션에 통합하고 예외를 검색하거나 수정하는 방법도 알게 됩니다.

## 빠른 답변
- **무엇을 할 수 있나요?** Java 프로젝트에서 사용자 정의 캘린더 예외를 생성, 수정 및 검색합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 안정 버전).  
- **라이선스가 필요합니까?** 예, 프로덕션 사용을 위해 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **MS Project 파일을 다룰 수 있나요?** 물론입니다 – MS Project 캘린더 데이터를 가져오고, 편집하고, 내보낼 수 있습니다.  
- **특별한 설정이 필요합니까?** Aspose.Tasks JAR를 클래스패스에 추가하고 관련 클래스를 임포트하면 됩니다.

## Aspose.Tasks for Java에서 사용자 정의 캘린더 예외를 만드는 방법?

Aspose.Tasks for Java에서 사용자 정의 캘린더 예외를 만들려면 대상 Project를 로드하고, 해당 Calendar를 가져온 뒤, 예외의 시작 및 종료 날짜와 원하는 작업 시간을 정의하고, 필요하면 반복 패턴을 설정한 다음 프로젝트를 저장합니다. 이 순서는 예외를 즉시 추가하고 .mpp 파일에 영구 저장합니다.

`Project` 클래스는 Aspose.Tasks의 핵심 객체로 전체 Microsoft Project 파일을 모델링합니다. `Project` 클래스는 Microsoft Project 파일을 나타내며 파일 내용에 접근할 수 있게 해줍니다. `Calendar` 객체는 프로젝트의 작업 및 비작업 시간을 정의합니다. `Calendar` 클래스는 예외를 포함한 모든 작업 시간 규칙을 담는 컨테이너입니다. `addException()` 메서드는 캘린더에 새로운 예외를 추가합니다. `addException()`은 지정된 날짜 범위에 대한 비작업 기간을 등록하는 단일 호출 API입니다.

대상 프로젝트를 `Project project = new Project("example.mpp")` 로 로드하고, `Calendar` 객체를 얻은 뒤, 원하는 날짜 범위와 작업 시간 설정으로 `addException()`을 호출합니다. 이 두 단계 패턴은 새로운 예외를 즉시 생성하고 프로젝트 저장 시 영구화합니다. 반복되는 공휴일의 경우, 저장하기 전에 예외에 `RecurrencePattern`을 구성합니다.

이와 같이 캘린더 예외를 만들면 **비작업일**을 정확히 지정할 수 있어 일회성 중단이나 연간 공휴일 모두에 적용할 수 있습니다. 예외를 추가한 후 `project.save("updated.mpp")` 를 호출하면 변경 사항이 디스크에 기록됩니다.

### 단계 개요
1. 프로젝트 파일을 로드합니다.  
2. `Calendar` 인스턴스를 가져오거나 생성합니다.  
3. 예외의 날짜 범위와 작업 시간을 정의합니다.  
4. (선택) 연간 공휴일을 위한 반복을 구성합니다.  
5. 프로젝트를 저장합니다.

## Aspose.Tasks에서 캘린더 예외 관리
[Aspose.Tasks for Java에서 캘린더 예외를 효율적으로 추가 및 제거하는 방법을 알아보세요](./add-remove/). 프로젝트 관리에서는 유연성이 핵심입니다. Aspose.Tasks를 사용하면 캘린더 예외를 손쉽게 관리하여 프로젝트 일정에 동적으로 조정할 수 있습니다. 이 튜토리얼은 단계별 가이드를 제공하므로 과정을 빠르게 습득할 수 있습니다. 캘린더 예외 관리로 프로젝트 관리 워크플로를 손쉽게 향상시키세요.

## Aspose.Tasks를 사용하여 캘린더 예외의 평일 정의
[Java 프로젝트에서 캘린더 예외의 평일을 정의하는 방법을 마스터하세요](./define-weekdays/) Aspose.Tasks와 함께라면 정확한 프로젝트 일정 수립을 위해 평일을 세밀하게 지정할 수 있습니다. 이 튜토리얼을 통해 일정 최적화에 필요한 지식을 얻고 프로젝트 타임라인을 완벽히 제어하세요.

## Aspose.Tasks를 사용하여 캘린더 예외 발생 처리
[Java 프로젝트에서 캘린더 예외를 효과적으로 처리하는 방법](./handle-occurrences/)을 Aspose.Tasks for Java와 함께 배우세요. 프로젝트 관리는 예기치 않은 상황에 대한 조정이 빈번히 요구되는 동적인 프로세스입니다. Aspose.Tasks를 활용하면 캘린더 예외를 체계적으로 관리하여 프로젝트 관리가 한층 수월해집니다. 자세한 튜토리얼을 통해 불확실성을 손쉽게 다루는 방법을 익히세요.

## Aspose.Tasks로 캘린더 예외 검색
[Aspose.Tasks for Java를 사용해 MS Project에서 캘린더 예외를 검색하는 방법을 알아보세요](./retrieve/). 캘린더 예외를 프로젝트 관리 프로세스에 원활히 통합할 수 있습니다. 이 튜토리얼은 캘린더 예외를 단계별로 검색하는 과정을 안내하여 프로젝트에 매끄럽게 적용할 수 있도록 돕습니다. Aspose.Tasks의 강력한 기능으로 프로젝트 관리 역량을 강화하세요.

## Aspose.Tasks와 MS Project 캘린더를 통합하는 방법?

MS Project 캘린더를 Aspose.Tasks와 통합하려면 `Project` 클래스를 사용해 소스 .mpp 파일을 로드하고, 기본 또는 사용자 정의 `Calendar` 객체에 접근한 뒤, 필요에 따라 예외를 수정·병합하고, 업데이트된 프로젝트를 저장합니다. 이를 통해 UI를 직접 조작하지 않고도 프로그래밍 방식으로 MS Project 캘린더를 다룰 수 있습니다.

`Project` 클래스는 Aspose.Tasks의 핵심 객체로 전체 Microsoft Project 파일을 모델링합니다. `new Project("source.mpp")` 로 기존 MS Project 파일을 임포트하면 라이브러리가 자동으로 기본 캘린더와 모든 사용자 정의 예외를 로드합니다. 이후 예외를 읽고, 수정하거나 병합한 뒤 프로젝트를 디스크에 다시 저장하면 됩니다. 이 접근 방식으로 **MS Project 캘린더** 데이터를 수동 UI 편집 없이 프로그래밍적으로 수정할 수 있습니다.

## 일반 사용 사례
- **공휴일 일정 관리** – 여러 프로젝트에 걸쳐 국가 공휴일을 비작업일로 정의합니다.  
- **교대 근무** – 비표준 근무 일정으로 운영되는 팀을 위해 사용자 정의 작업 주를 설정합니다.  
- **프로젝트 단계 차단** – 유지보수 창구와 같이 작업이 없어야 하는 기간을 차단합니다.  
- **레거시 마이그레이션** – 오래된 MS Project 파일에서 캘린더를 가져와 프로그래밍적으로 조정합니다.

## 팁 및 모범 사례
- **프로 팁:** 중복을 방지하려면 새로운 예외를 추가하기 전에 기존 캘린더를 항상 조회하세요.  
- **경고:** 이미 작업에 할당된 캘린더를 변경하면 작업 날짜가 이동할 수 있으니 수정 후 일정을 다시 계산하세요.  
- **성능:** 여러 예외 업데이트를 하나의 트랜잭션으로 배치하면 파일 I/O 오버헤드를 줄일 수 있습니다. Aspose.Tasks는 1 GB까지의 파일을 메모리 사용량 200 MB 이하로 처리하며, 일반 서버 하드웨어에서 초당 30개 이상의 캘린더 관련 API 호출을 처리할 수 있습니다.

## 캘린더 예외 튜토리얼
### [Aspose.Tasks에서 캘린더 예외 관리](./add-remove/)
Aspose.Tasks for Java에서 캘린더 예외를 효율적으로 추가하고 제거하는 방법을 배웁니다. 프로젝트 관리 워크플로를 손쉽게 향상시키세요.
### [Aspose.Tasks를 사용하여 캘린더 예외의 평일 정의](./define-weekdays/)
Aspose.Tasks를 활용해 Java 프로젝트에서 캘린더 예외의 평일을 정의하는 방법을 배워 정확한 프로젝트 일정을 수립하세요.
### [Aspose.Tasks를 사용하여 캘린더 예외 발생 처리](./handle-occurrences/)
Aspose.Tasks for Java와 함께 Java 프로젝트에서 캘린더 예외를 효과적으로 처리하는 방법을 배웁니다. 지금 프로젝트 관리 프로세스를 간소화하세요.
### [Aspose.Tasks로 캘린더 예외 검색](./retrieve/)
Aspose.Tasks for Java를 사용해 MS Project에서 캘린더 예외를 검색하는 방법을 배웁니다. 원활한 통합을 위한 단계별 튜토리얼입니다.

## 자주 묻는 질문

**Q: 프로젝트가 이미 배포된 후에도 캘린더 예외를 수정할 수 있나요?**  
A: 예. add‑remove 및 define‑weekdays API를 사용해 캘린더를 업데이트한 뒤 프로젝트 파일을 다시 저장하면 됩니다.

**Q: Aspose.Tasks가 반복 예외(예: 매월 첫 번째 월요일)를 지원하나요?**  
A: 물론입니다. “캘린더 예외 발생 처리” 튜토리얼에서 반복 패턴 설정 방법을 다룹니다.

**Q: 사용자 정의 캘린더가 프로젝트의 모든 작업에 적용되도록 하려면 어떻게 해야 하나요?**  
A: 프로젝트의 기본 캘린더에 할당하거나 각 작업의 `Calendar` 속성에 명시적으로 설정하면 됩니다.

**Q: 여러 MS Project 파일의 캘린더를 병합할 수 있나요?**  
A: 예. 각 캘린더를 검색한 뒤 예외를 프로그래밍적으로 결합하고, 병합된 캘린더를 대상 프로젝트에 할당하면 됩니다.

**Q: 이러한 기능을 사용하려면 어떤 버전의 Aspose.Tasks가 필요하나요?**  
A: 현재 안정 버전인 Aspose.Tasks for Java (2025.x)에서 모든 기능을 사용할 수 있습니다.

## 관련 튜토리얼

- [Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions](/tasks/java/calendar-exceptions/define-weekdays/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Last Updated:** 2026-11-06  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}