---
date: 2026-11-19
description: Aspose.Tasks를 사용하여 custom calendar Java를 만드는 방법을 배우세요. 이 가이드는 작업일(working
  days)을 정의하고, 작업시간(working hours)을 설정하며, MS Project 캘린더(calendars)를 프로그래밍 방식으로 수정하는
  방법을 보여줍니다.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: 캘린더
og_description: Aspose.Tasks와 함께 custom calendar Java를 만드는 방법을 배우세요. 작업일(working days)
  정의, 작업시간(working hours) 설정, MS Project 캘린더(calendars) 효율적인 수정 방법을 마스터하세요.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Aspose.Tasks를 사용하여 custom calendar Java 만들기 방법
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Aspose.Tasks를 사용하여 custom calendar Java 만들기 방법
url: /ko/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 캘린더

## 소개

Java 개발자로서 **custom calendar Java** 솔루션을 **만들고** 싶다면, 올바른 곳에 오셨습니다. 이 허브는 Aspose.Tasks for Java 튜토리얼을 모두 모아 **define working days MS Project**, **set working hours MS Project**, 그리고 프로그래밍 방식으로 캘린더 설정을 조정하는 방법을 보여줍니다. 새로운 스케줄링 엔진을 구축하든 기존 계획을 확장하든, 이러한 API를 마스터하면 작업일 패턴, 휴일, 사용자 정의 교대 근무를 정확히 제어할 수 있으며 MS Project UI를 전혀 열 필요가 없습니다.

## 빠른 답변
- **주중을 정의하는 주요 목적은 무엇인가요?**  
  MS Project에 어떤 요일이 작업일이며 작업 시간이 어떻게 되는지를 알려주기 위함입니다.  
- **Java에서 주중 정의를 처리하는 라이브러리는 무엇인가요?**  
  Aspose.Tasks for Java가 캘린더 조작을 위한 유창한 API를 제공합니다.  
- **라이선스가 필요합니까?**  
  평가용 무료 라이선스로 테스트가 가능하며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **팀마다 여러 캘린더를 정의할 수 있나요?**  
  예 – 각 프로젝트는 자체 주중 설정을 가진 여러 캘린더를 포함할 수 있습니다.  
- **시작할 수 있는 샘플 프로젝트가 있나요?**  
  아래 링크된 “Define Weekdays in Calendar” 튜토리얼에 바로 실행 가능한 예제가 포함되어 있습니다.

## Java에서 사용자 정의 캘린더를 만드는 방법?

프로젝트를 로드하고, 캘린더를 생성하거나 가져온 뒤, 주중 정의를 추가하고 파일을 저장합니다—모두 몇 번의 API 호출만으로 가능합니다. 이 방법은 수동 UI 작업을 없애고 수십 개 프로젝트에 걸쳐 캘린더 생성을 자동화하며 조직 전체에 일관된 작업일 패턴을 보장합니다.

## Project 클래스란?

`Project` 클래스는 MS Project 파일을 로드, 편집 및 저장하기 위한 중심 객체입니다. 작업, 리소스, 캘린더 컬렉션을 보유하고 있으며, 프로젝트의 모든 측면을 프로그래밍 방식으로 읽고 수정할 수 있는 메서드를 제공합니다. 이 클래스를 사용하면 프로젝트의 캘린더 컬렉션에 접근하고 작업 시간을 조정한 뒤, 변경 사항을 MPP 또는 XML 파일에 다시 저장할 수 있습니다.

## MS Project 캘린더에서 주중을 정의하려면 어떻게 하나요?

`Project` 클래스는 MS Project 파일을 나타내며 데이터 구조에 접근할 수 있게 해줍니다. `Calendar` 객체는 작업 시간 정의와 예외를 저장합니다. `new Project("myproject.mpp")` 로 프로젝트를 로드하고, (또는 생성하고) `Calendar` 객체를 가져온 뒤, 다음과 같이 호출합니다: `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. 이 한 줄은 월요일에 8시간 근무를 설정합니다. 다른 요일에 대해 반복하고, 마지막에 `project.save("updated.mpp")` 로 저장합니다. 이 간결한 패턴을 통해 몇 번의 API 호출만으로 주중을 정의, 수정 또는 삭제할 수 있어 수동 UI 작업이 필요 없습니다.

## WeekDay 객체란?

`WeekDay` 객체는 캘린더 내의 요일별 항목을 나타냅니다. 해당 요일이 작업일인지 여부, 작업 시간 구간, 기본 동작 플래그 등을 저장합니다. 하나 이상의 `WorkingTime` 구간을 연결해 교대 근무를 모델링하거나, 요일을 비작업으로 설정하거나, 상위 캘린더의 기본값을 상속받을 수 있습니다.

## MS Project에서 작업일을 정의하려면?

`WeekDay` 객체를 캘린더의 `WeekDays` 컬렉션에 추가하면 작업일을 정의할 수 있습니다. 각 `WeekDay`는 해당 요일이 작업일인지와 작업 시간 범위를 지정합니다. 예를 들어 토요일을 반나절로 만들려면 `WeekDay`에 `WorkingTime`을 10:00~14:00 로 하나 추가하면 됩니다. API가 자동으로 프로젝트 일정 계산을 업데이트합니다.

## MS Project에서 작업 시간을 설정하려면?

각 `WeekDay`에 하나 이상의 `WorkingTime` 구간을 생성합니다. `WorkingTime`은 시작 시, 시작 분, 종료 시, 종료 분 값을 받습니다. 하루에 여러 구간을 할당해 교대 근무(예: 08:00‑12:00 및 13:00‑17:00)를 모델링할 수 있습니다. 모든 요일을 구성한 뒤 `project.save(...)` 로 변경 사항을 영구 저장합니다.

## Aspose.Tasks for Java로 주중을 정의하는 이유는?

- **전체 API 제어** – UI 제한이 없으며, 프로그래밍 방식으로 주중 항목을 생성, 수정, 삭제할 수 있습니다.  
- **크로스‑플랫폼** – 데스크톱 앱부터 클라우드 서비스까지 JVM 호환 환경 어디서든 작동합니다.  
- **정밀도** – 요일별로 다른 작업 시간을 설정하고, 휴일 예외를 추가하며, 여러 프로젝트에 걸쳐 캘린더를 동기화합니다.  
- **성능** – 전체 UI를 로드하지 않고도 500 + 작업 및 100 + 주를 포함한 캘린더를 처리하며, 표준 2.5 GHz 서버에서 변환 시간을 2 초 이하로 달성합니다( Aspose 벤치마크 기반 수치).  
- **광범위한 포맷 지원** – Aspose.Tasks는 30 + 캘린더 관련 API를 지원하고 20 개 이상의 파일 포맷으로 입출력할 수 있어 기존 프로젝트 데이터 파이프라인과 원활히 통합됩니다.

## 사전 요구 사항
- Java 8 이상 설치  
- Aspose.Tasks for Java 라이브러리 (Aspose 웹사이트에서 다운로드하거나 Maven/Gradle을 통해 추가)  
- 유효한 Aspose.Tasks 라이선스 (평가 라이선스로 학습 가능)  

## Aspose.Tasks에서 MS Project 캘린더 속성 관리

Java에서 Aspose.Tasks를 사용해 MS Project 캘린더 속성을 관리하는 전체 잠재력을 활용하세요. 이 튜토리얼은 캘린더 관리의 복잡성을 단계별로 안내하며, 작업 시간 조정부터 특수 날짜 정의까지 모든 것을 마스터하도록 돕습니다.

프로젝트 일정에 대한 제어를 시작하시겠습니까? [여기서 튜토리얼을 확인하세요](./properties/).

## Aspose.Tasks로 MS Project 캘린더 만들기

Aspose.Tasks for Java를 사용해 MS Project 캘린더를 만드는 과정을 간편하게 진행하세요. 이 튜토리얼은 프로젝트 고유의 요구에 맞춘 캘린더 설정을 손쉽게 할 수 있도록 도와줍니다. 효율적인 프로젝트 계획 및 조직을 위한 첫 걸음을 내디뎌 보세요.

쉽게 캘린더를 만들 준비가 되셨나요? [튜토리얼을 확인하세요](./create/).

## Aspose.Tasks로 캘린더에서 주중 정의하기

Aspose.Tasks for Java를 사용해 MS Project 캘린더의 주중을 정의하세요. 이 튜토리얼은 작업일 및 시간대를 맞춤 설정하는 과정을 안내하며, 성공적인 프로젝트 관리를 위한 유연성을 제공합니다. 캘린더를 여러분에게 맞게 만드세요.

주중을 손쉽게 정의하고 싶으신가요? [여기서 시작하세요](./define-weekdays/).

이 튜토리얼들을 탐색하면서 작업 시간 추출, 표준 캘린더 생성, 작업 주 읽기, 캘린더를 MPP 형식으로 업데이트하는 추가 주제도 발견하게 될 것입니다. 각 튜토리얼은 실용적인 지식을 제공하도록 설계되어, 배운 내용을 바로 Java 프로젝트에 적용할 수 있습니다.

## Aspose.Tasks로 캘린더에서 작업 시간 가져오기

Aspose.Tasks for Java를 사용해 MS Project 캘린더에서 작업 시간을 추출함으로써 프로젝트 관리 작업을 간소화하세요. 이 튜토리얼은 효율적인 프로젝트 일정 최적화를 위한 기술을 제공합니다.

작업 시간을 손쉽게 추출하고 싶으신가요? [튜토리얼을 탐색하세요](./working-hours/).

## Aspose.Tasks에서 표준 캘린더 만들기

Aspose.Tasks와 함께 Java에서 표준 MS Project 캘린더를 만드는 방법을 배워 프로젝트 관리 역량을 강화하세요. 단계별 튜토리얼을 통해 표준화된 일정 접근 방식을 구현할 수 있습니다.

표준 캘린더를 만들 준비가 되셨나요? [튜토리얼을 확인하세요](./make-standard/).

## Aspose.Tasks로 MS Project 캘린더에서 작업 주 읽기

Aspose.Tasks for Java를 사용해 MS Project 캘린더에서 작업 주를 읽는 방법을 포괄적으로 학습하세요. 이 튜토리얼은 상세한 지침을 제공하여 프로젝트 일정을 효과적으로 관리할 수 있게 합니다.

작업 주를 손쉽게 읽고 싶으신가요? [여기서 시작하세요](./read-work-weeks/).

## Aspose.Tasks로 MS Project 캘린더를 MPP 형식으로 업데이트하기

Aspose.Tasks for Java를 사용해 MS Project 캘린더를 MPP 형식으로 손쉽게 업데이트하세요. 이 튜토리얼은 프로젝트 데이터를 최적의 호환성을 위해 올바른 형식으로 유지하는 원활한 접근 방식을 제공합니다.

캘린더를 MPP 형식으로 업데이트할 준비가 되셨나요? [튜토리얼을 탐색하세요](./update-to-mpp/).

Aspose.Tasks for Java의 전체 잠재력을 활용해 프로젝트 관리 기술을 한 단계 끌어올리세요. 각 튜토리얼은 모든 수준의 개발자를 위해 설계되어 원활한 학습 경험을 보장합니다. 지금 바로 시작해 Java 프로젝트 관리 여정을 혁신하세요!

## 캘린더 튜토리얼
### [Aspose.Tasks에서 MS Project 캘린더 속성 관리](./properties/)
Java에서 Aspose.Tasks를 사용해 MS Project 캘린더 속성을 관리하는 방법을 배우세요. Java 애플리케이션 내 캘린더에 대한 단계별 가이드를 제공합니다.
### [Aspose.Tasks로 MS Project 캘린더 만들기](./create/)
Aspose.Tasks for Java를 사용해 MS Project 캘린더를 만드는 방법을 배우세요. 손쉽게 프로젝트 관리를 간소화합니다.
### [Aspose.Tasks로 캘린더에서 주중 정의하기](./define-weekdays/)
Aspose.Tasks for Java를 사용해 MS Project 캘린더에서 주중을 정의하는 방법을 배우세요. 작업일 및 시간을 손쉽게 맞춤 설정합니다.
### [Aspose.Tasks로 캘린더에서 작업 시간 가져오기](./working-hours/)
Aspose.Tasks for Java를 사용해 MS Project 캘린더에서 작업 시간을 쉽게 추출하세요. 프로젝트 관리 작업을 단순화합니다.
### [Aspose.Tasks에서 표준 캘린더 만들기](./make-standard/)
Aspose.Tasks를 사용해 Java에서 표준 MS Project 캘린더를 만드는 방법을 배우세요. 단계별 튜토리얼로 프로젝트 관리 역량을 강화합니다.
### [Aspose.Tasks로 MS Project 캘린더에서 작업 주 읽기](./read-work-weeks/)
Aspose.Tasks for Java를 사용해 MS Project 캘린더에서 작업 주를 읽는 방법을 배우세요. 포괄적인 튜토리얼에서 단계별 지침을 제공합니다.
### [Aspose.Tasks for Java로 MS Project 캘린더를 MPP 형식으로 손쉽게 업데이트하기](./update-to-mpp/)
Aspose.Tasks for Java를 사용해 MS Project 캘린더를 MPP 형식으로 손쉽게 업데이트하는 방법을 배우세요.

## 자주 묻는 질문

**Q: 각 요일마다 다른 작업 시간을 정의할 수 있나요?**  
A: 예. Aspose.Tasks를 사용하면 월요일부터 일요일까지 각각 시작 및 종료 시간을 개별적으로 설정할 수 있습니다.

**Q: 휴일이나 비작업일은 어떻게 처리하나요?**  
A: 주중 정의 후 예외(날짜)를 추가해 휴일이나 사용자 정의 비작업 기간을 표시할 수 있습니다.

**Q: 한 캘린더에서 정의한 주중을 다른 캘린더로 복사할 수 있나요?**  
A: 물론입니다. 기존 캘린더에서 `WeekDay` 객체를 가져와 다른 캘린더 인스턴스에 추가하면 됩니다.

**Q: 주중을 업데이트한 후 프로젝트를 다시 로드해야 하나요?**  
A: 필요 없습니다. 변경 사항은 메모리상의 `Project` 객체에 바로 적용되며, 완료 후 프로젝트를 저장하기만 하면 됩니다.

**Q: 주중 조작을 위해 필요한 Aspose.Tasks 버전은 어느 것인가요?**  
A: 최신 버전(20.10 이상) 모두 전체 주중 API를 지원합니다. 최상의 성능을 위해 최신 안정 버전을 사용하는 것을 권장합니다.

---

**마지막 업데이트:** 2026-11-19  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose.Tasks로 작업일 및 작업 시간 결정](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks for Java로 사용자 정의 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}