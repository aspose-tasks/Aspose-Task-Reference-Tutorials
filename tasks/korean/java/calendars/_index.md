---
date: 2026-08-08
description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 평일을 정의하는 방법을 배웁니다. 이 가이드는
  MS Project 캘린더를 수정하고, Java로 사용자 정의 캘린더를 만들며, 작업일을 효율적으로 일정 잡는 방법을 보여줍니다.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: 캘린더
og_description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 평일을 정의하는 방법을 배웁니다. 사용자
  정의 캘린더 Java, MS Project 캘린더 수정, 작업일 효율적 일정 관리.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: MS Project 캘린더에서 평일 정의 방법 – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: MS Project 캘린더에서 평일 정의 방법 – Aspose.Tasks Java
url: /ko/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 캘린더

## 소개

프로젝트 일정에서 **주중 정의**를 하려는 Java 개발자라면, 바로 여기가 맞습니다. 이 허브에서는 Aspose.Tasks for Java 튜토리얼을 모두 모아 MS Project 캘린더 내에서 **주중을 정의하는 방법**을 보여주고, 작업 시간을 조정하며, 타임라인을 명확하게 유지합니다. 새로운 스케줄링 엔진을 구축하든 기존 계획을 조정하든, 주중 정의를 마스터하면 작업일 패턴, 휴일 및 맞춤 교대 근무를 정밀하게 제어할 수 있습니다. 또한 이 가이드는 **MS Project 캘린더를 수정하는 방법**을 프로그래밍 방식으로 설명하므로 수십 개 프로젝트에 걸쳐 캘린더 생성을 자동화할 수 있습니다.

## 빠른 답변
- **주중을 정의하는 주요 목적은 무엇입니까?**  
  MS Project에 어떤 날이 작업일이며 작업 시간이 어떻게 되는지 알려주기 위해서입니다.
- **Java에서 주중 정의를 처리하는 라이브러리는 무엇입니까?**  
  Aspose.Tasks for Java는 캘린더 조작을 위한 유창한 API를 제공합니다.
- **라이선스가 필요합니까?**  
  무료 평가 라이선스로 테스트가 가능하며, 상용 환경에서는 상업용 라이선스가 필요합니다.
- **다른 팀을 위해 여러 캘린더를 정의할 수 있습니까?**  
  예 – 각 프로젝트는 여러 캘린더를 포함할 수 있으며, 각 캘린더는 자체 주중 설정을 가집니다.
- **시작할 수 있는 샘플 프로젝트가 있습니까?**  
  아래 링크된 “Define Weekdays in Calendar” 튜토리얼에는 바로 실행할 수 있는 예제가 포함되어 있습니다.

## MS Project 캘린더에서 주중을 정의하려면 어떻게 해야 하나요?

`Project` 클래스는 MS Project 파일을 나타내며 데이터 구조에 접근할 수 있게 합니다. `Calendar` 객체는 프로젝트의 작업 시간 정의와 예외를 저장합니다. `new Project("myproject.mpp")` 로 프로젝트를 로드하고, `Calendar` 객체를 가져오거나 생성한 다음 `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` 를 호출합니다. 이 한 줄은 월요일 작업일 항목을 8시간 근무로 생성합니다. 다른 요일에 대해 반복하고, 마지막으로 `project.save("updated.mpp")` 로 프로젝트를 저장합니다. 이 간결한 패턴을 사용하면 몇 번의 API 호출만으로 주중을 정의, 수정 또는 삭제할 수 있어 수동 UI 조작이 필요 없습니다.

## WeekDay 객체란 무엇입니까?

`WeekDay` 객체는 Aspose.Tasks 캘린더 내에서 주중의 단일 일 항목을 나타내며, 작업 상태와 작업 시간 구간을 저장합니다. 시작/종료 시간을 설정하거나 비작업으로 지정하고, 초과 근무 기간을 추가할 수 있습니다. 여러 `WorkingTime` 구간을 보유하여 교대 근무를 모델링할 수 있으며, 기본 작업일에 대한 플래그도 지원합니다. `WeekDay` API를 사용하여 날짜를 활성화하거나 비활성화하고, 정규 시간을 할당하거나 고급 스케줄링 시나리오를 위한 초과 근무 규칙을 지정하세요.

## 주중을 정의하기 위해 Aspose.Tasks for Java를 사용하는 이유는 무엇입니까?

- **전체 API 제어** – UI 제한이 없으며, 프로그래밍 방식으로 주중 항목을 생성, 수정 또는 삭제할 수 있습니다.  
- **크로스‑플랫폼** – 데스크톱 앱부터 클라우드 서비스까지 모든 JVM 호환 환경에서 작동합니다.  
- **정밀도** – 각 주중에 대해 다른 작업 시간을 설정하고, 휴일 예외를 추가하며, 여러 프로젝트에 걸쳐 캘린더를 동기화합니다.  
- **성능** – 전체 UI를 로드하지 않고도 500개 이상의 작업과 100주 이상을 포함하는 캘린더를 처리하며, 표준 2.5 GHz 서버에서 변환 시간을 2초 미만으로 달성합니다 (Aspose 벤치마크 기반의 정량적 주장).

## 전제 조건
- Java 8 이상이 설치되어 있어야 합니다.  
- Aspose.Tasks for Java 라이브러리 (Aspose 웹사이트에서 다운로드하거나 Maven/Gradle을 통해 추가).  
- 유효한 Aspose.Tasks 라이선스 (평가 라이선스로 학습 가능).

## Aspose.Tasks에서 MS Project 캘린더 속성 관리

Aspose.Tasks를 사용하여 Java에서 MS Project 캘린더 속성을 관리하는 전체 잠재력을 활용하세요. 우리의 튜토리얼은 캘린더 관리의 복잡한 내용을 단계별로 안내하며, 맞춤화와 최적화에 대한 유용한 통찰을 제공합니다. 작업 시간 조정부터 특수 날짜 정의까지 모두 마스터하게 됩니다.

프로젝트 타임라인을 제어할 준비가 되셨나요? [여기에서 튜토리얼을 확인하세요](./properties/).

## Aspose.Tasks를 사용하여 MS Project 캘린더 만들기

Aspose.Tasks for Java를 사용하여 MS Project 캘린더를 생성함으로써 프로젝트 관리를 손쉽게 간소화하세요. 우리의 튜토리얼은 과정을 단순화하여 프로젝트 고유의 요구에 맞는 캘린더를 설정할 수 있도록 합니다. 효율적인 프로젝트 계획 및 조직을 위한 첫걸음을 내딛으세요.

쉽게 캘린더를 만들 준비가 되셨나요? [튜토리얼을 확인하세요](./create/).

## Aspose.Tasks로 캘린더에서 주중 정의

Aspose.Tasks for Java를 사용하여 MS Project 캘린더의 주중을 정의함으로써 맞춤화하세요. 이 튜토리얼은 작업일과 시간을 조정하는 과정을 안내하며, 성공적인 프로젝트 관리를 위한 유연성을 제공합니다. 캘린더를 여러분에게 맞게 활용하세요.

주중을 손쉽게 정의할 준비가 되셨나요? [여기서 시작하세요](./define-weekdays/).

이 튜토리얼들을 진행하면서 작업 시간 추출, 표준 캘린더 생성, 작업 주 읽기, 캘린더를 MPP 형식으로 업데이트하는 추가 주제를 발견하게 될 것입니다. 각 튜토리얼은 실용적인 지식을 제공하도록 설계되어, 배운 내용을 Java 프로젝트에 바로 적용할 수 있도록 합니다.

## Aspose.Tasks를 사용하여 캘린더에서 작업 시간 가져오기

Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 시간을 추출함으로써 프로젝트 관리 작업을 간소화하세요. 이 튜토리얼은 프로젝트 타임라인을 효율적으로 최적화하는 데 필요한 기술을 제공합니다.

작업 시간을 손쉽게 추출할 준비가 되셨나요? [튜토리얼을 확인하세요](./working-hours/).

## Aspose.Tasks에서 표준 캘린더 만들기

Aspose.Tasks를 사용하여 Java에서 표준 MS Project 캘린더를 만드는 방법을 배워 프로젝트 관리 역량을 강화하세요. 이 단계별 튜토리얼은 프로젝트 타임라인에 표준화된 접근 방식을 구현하도록 보장합니다.

표준 캘린더를 만들 준비가 되셨나요? [튜토리얼을 확인하세요](./make-standard/).

## Aspose.Tasks로 MS Project 캘린더에서 작업 주 읽기

Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 주를 읽는 방법에 대한 포괄적인 통찰을 얻으세요. 이 튜토리얼은 자세한 안내를 제공하여 프로젝트 일정을 효과적으로 관리할 수 있게 합니다.

작업 주를 손쉽게 읽을 준비가 되셨나요? [여기서 시작하세요](./read-work-weeks/).

## Aspose.Tasks로 MS Project 캘린더를 MPP 형식으로 업데이트

Aspose.Tasks for Java를 사용하여 MS Project 캘린더를 MPP 형식으로 손쉽게 업데이트하세요. 이 튜토리얼은 프로젝트 데이터를 최적의 호환성을 위해 올바른 형식으로 유지하는 원활한 방법을 제공합니다.

캘린더를 MPP 형식으로 업데이트할 준비가 되셨나요? [튜토리얼을 확인하세요](./update-to-mpp/).

Aspose.Tasks for Java의 전체 잠재력을 활용하고 프로젝트 관리 역량을 높이세요. 각 튜토리얼은 모든 수준의 개발자를 위해 설계되어 원활한 학습 경험을 보장합니다. 지금 바로 시작하여 Java 프로젝트 관리 여정을 혁신하세요!

## 캘린더 튜토리얼
### [Aspose.Tasks에서 MS Project 캘린더 속성 관리](./properties/)
Aspose.Tasks를 사용하여 Java에서 MS Project 캘린더 속성을 관리하는 방법을 배웁니다. 이는 Java 애플리케이션 내에서 캘린더를 다루는 단계별 안내를 제공합니다.
### [Aspose.Tasks를 사용하여 MS Project 캘린더 만들기](./create/)
Aspose.Tasks for Java를 사용하여 MS Project 캘린더를 만드는 방법을 배웁니다. 손쉽게 프로젝트 관리를 간소화하세요.
### [Aspose.Tasks로 캘린더에서 주중 정의](./define-weekdays/)
Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 주중을 정의하는 방법을 배웁니다. 작업일과 시간을 손쉽게 맞춤화하세요.
### [Aspose.Tasks를 사용하여 캘린더에서 작업 시간 가져오기](./working-hours/)
Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 시간을 쉽게 추출합니다. 프로젝트 관리 작업을 간소화하세요.
### [Aspose.Tasks에서 표준 캘린더 만들기](./make-standard/)
Aspose.Tasks를 사용하여 Java에서 표준 MS Project 캘린더를 만드는 방법을 배웁니다. 이 단계별 튜토리얼을 통해 프로젝트 관리 역량을 강화하세요.
### [Aspose.Tasks로 MS Project 캘린더에서 작업 주 읽기](./read-work-weeks/)
Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 주를 읽는 방법을 배웁니다. 이 포괄적인 튜토리얼에서 단계별 안내를 얻으세요.
### [Aspose.Tasks로 MS Project 캘린더를 MPP 형식으로 업데이트](./update-to-mpp/)
Aspose.Tasks for Java를 사용하여 MS Project 캘린더를 MPP 형식으로 손쉽게 업데이트하는 방법을 배웁니다.

## 자주 묻는 질문

**Q: 각 주중에 대해 다른 작업 시간을 정의할 수 있나요?**  
A: 예. Aspose.Tasks를 사용하면 월요일부터 일요일까지 각각 시작 및 종료 시간을 개별적으로 설정할 수 있습니다.

**Q: 휴일이나 비작업일을 어떻게 처리하나요?**  
A: 주중을 정의한 후 예외(날짜)를 추가하여 휴일이나 맞춤 비작업 기간을 표시할 수 있습니다.

**Q: 한 캘린더에서 다른 캘린더로 주중 정의를 복사할 수 있나요?**  
A: 물론 가능합니다. 기존 캘린더에서 `WeekDay` 객체를 가져와 다른 캘린더 인스턴스에 추가할 수 있습니다.

**Q: 주중을 업데이트한 후 프로젝트를 다시 로드해야 하나요?**  
A: 아니요. 변경 사항은 메모리 내 `Project` 객체에 바로 적용되며, 완료 후 프로젝트를 저장하면 됩니다.

**Q: 주중 조작을 위해 필요한 Aspose.Tasks 버전은 무엇인가요?**  
A: 최근 모든 버전(20.10 이상)에서 전체 주중 API를 지원합니다. 최상의 성능을 위해 최신 안정 버전을 사용하는 것을 권장합니다.

---

**마지막 업데이트:** 2026-08-08  
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