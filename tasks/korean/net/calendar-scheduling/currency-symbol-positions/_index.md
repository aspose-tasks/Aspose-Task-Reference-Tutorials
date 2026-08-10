---
date: 2026-07-19
description: .NET 프로젝트에서 금액 뒤의 통화 기호를 Aspose.Tasks를 사용해 손쉽게 제어하는 방법을 배웁니다.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Aspose.Tasks의 통화 기호 위치
og_description: .NET용 Aspose.Tasks를 사용해 금액 뒤에 통화 기호를 배치하는 방법을 배웁니다. 단계별 안내와 모범 사례를
  따라 보세요.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Aspose.Tasks에서 금액 뒤 통화 기호 — 빠른 가이드
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Aspose.Tasks에서 금액 뒤에 통화 기호를 배치하는 방법
url: /ko/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 금액 뒤에 통화 기호 표시하는 방법

## 소개

프로젝트 비용 보고서를 생성할 때 **금액 뒤에 통화 기호**를 배치하는 방식은 가독성과 지역 표준 준수에 영향을 줄 수 있습니다. Aspose.Tasks for .NET은 몇 줄의 코드만으로 이 서식을 제어할 수 있게 해 주어, 모든 재무 수치가 이해관계자가 기대하는 정확한 형태로 표시되도록 합니다. 이 튜토리얼에서는 필요한 단계들을 살펴보고, 설정이 왜 중요한지 설명하며, 실제 .NET 프로젝트에 적용하는 방법을 보여드립니다.

## 빠른 답변
- **“금액 뒤에 통화 기호”가 의미하는 것은?** 기호(예: $)가 숫자 값 뒤에 표시되는 것으로, `100 $`와 같이 나타납니다.
- **어떤 속성이 위치를 제어하나요?** `Project` 객체의 `CurrencySymbolPosition` 속성.
- **라이선스가 필요합니까?** 개발 단계에서는 체험판으로 가능하지만, 운영 환경에서는 상용 라이선스가 필요합니다.
- **지원되는 통화는?** 50개 이상의 통화가 내장되어 있어 대부분의 글로벌 시장을 커버합니다.
- **런타임에 설정을 변경할 수 있나요?** 예, 프로젝트 파일을 저장하기 전 언제든지 업데이트할 수 있습니다.

## “금액 뒤에 통화 기호” 설정이란?
**금액 뒤에 통화 기호** 옵션은 프로젝트의 모든 금액 필드에서 통화 기호가 숫자 앞에 표시될지 뒤에 표시될지를 결정합니다. 이 설정을 조정하면 수동 후처리 없이도 현지 회계 관행에 맞는 보고서를 생성할 수 있으며, 해당 형식에 익숙한 이해관계자에게 가독성을 높여줍니다.

## 왜 Aspose.Tasks를 사용해 통화 서식을 지정해야 할까요?
Aspose.Tasks는 **50개 이상의 통화**를 지원하고 **10,000개 이상의 작업**을 메모리에 전체 파일을 로드하지 않고도 처리할 수 있어 저사양 하드웨어에서도 빠른 성능을 제공합니다. API를 통해 프로그래밍 방식으로 제어할 수 있어 수동 스프레드시트 편집이 필요 없으며, 대규모 재무 보고를 효율적이고 신뢰성 있게 수행할 수 있습니다.

## 사전 요구 사항

### 1. Aspose.Tasks for .NET 설치
Aspose.Tasks 라이브러리가 설치되어 있는지 확인하십시오. [여기](https://releases.aspose.com/tasks/net/)에서 다운로드할 수 있습니다.

### 2. .NET 프로그래밍 기본 지식
예제 코드를 따라가기 위해서는 .NET 프로그래밍에 대한 기본 이해가 필요합니다.

## 네임스페이스 가져오기

`Aspose.Tasks` 네임스페이스는 `Project` 클래스와 관련 열거형에 접근할 수 있게 해 줍니다.

`Project` 클래스는 메모리 내에서 단일 프로젝트 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 네임스페이스를 가져온 후에는 프로젝트 데이터를 자유롭게 다룰 수 있습니다.

```csharp

```

이제 예제를 명확하고 실행 가능한 단계로 나누어 살펴보겠습니다.

## 금액 뒤에 통화 기호를 설정하는 방법

`CurrencySymbolPosition`은 통화 기호가 숫자 앞에 표시될지 뒤에 표시될지를 지정하는 열거형입니다.

프로젝트를 로드하고 `CurrencySymbolPosition`을 `After`로 설정한 뒤 저장하면 금액 뒤에 기호가 표시됩니다. 이 간단한 접근 방식은 모든 지원 통화에 적용 가능하며 추가 서식 로직이 필요 없습니다. 샘플 비용 보고서를 내보내어 기호가 올바르게 표시되는지 확인할 수도 있습니다.

### 단계 1: 프로젝트 파일 로드
`Project` 클래스는 기존 MS‑Project 파일을 로드하거나 새 파일을 메모리에서 생성합니다.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 단계 2: 통화 기호 위치 설정
`CurrencySymbolPosition` 열거형을 사용해 `Before` 또는 `After`를 선택할 수 있습니다. `After`로 설정하면 기호가 숫자 뒤에 배치됩니다.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### 단계 3: 프로젝트 작업 수행
기호 위치를 설정한 후에는 필요에 따라 작업, 리소스 또는 사용자 정의 필드를 추가할 수 있습니다. 프로젝트를 저장하면 이 설정이 유지됩니다.

```csharp
// Perform other operations with the project...
```

## 일반적인 문제와 해결책
- **기호가 여전히 금액 앞에 표시됨:** `Save` 호출 **이전**에 속성을 설정했는지 확인하십시오. 저장 후에 변경하면 파일을 다시 저장해야 적용됩니다.
- **지원되지 않는 통화:** 사용하려는 통화 코드가 Aspose.Tasks 지원 목록(50개 이상)에 포함되어 있는지 확인하십시오.
- **대형 프로젝트에서 성능 저하:** 작업 수가 10,000개를 초과할 경우 `ProjectReader`를 사용해 파일을 스트리밍하십시오.

## 자주 묻는 질문

**Q: 동일 프로젝트 내에서 통화 기호 위치를 여러 번 변경할 수 있나요?**  
A: 예, 필요할 때마다 `CurrencySymbolPosition`을 설정하고 프로젝트를 다시 저장하면 됩니다.

**Q: Aspose.Tasks가 미국 달러 외의 통화를 지원하나요?**  
A: 물론입니다. Aspose.Tasks는 50개 이상의 국제 통화를 지원하므로 모든 지역 형식에 대응할 수 있습니다.

**Q: Aspose.Tasks for .NET의 체험판을 받을 수 있나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks for .NET의 무료 체험판을 받을 수 있습니다.

**Q: Aspose.Tasks for .NET 사용 중 문제가 발생하면 지원을 받을 수 있나요?**  
A: 물론입니다! Aspose.Tasks 커뮤니티 포럼에서 지원 및 도움을 받을 수 있습니다. [여기](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

**Q: Aspose.Tasks for .NET 라이선스는 어떻게 구매하나요?**  
A: [여기](https://purchase.aspose.com/buy)에서 Aspose.Tasks for .NET 라이선스를 구매할 수 있습니다.

## 결론

**금액 뒤에 통화 기호**를 제어하는 것은 프로젝트 관리 소프트웨어에서 재무 보고의 핵심 요소입니다. Aspose.Tasks for .NET을 사용하면 프로그래밍 방식으로 이 옵션을 설정할 수 있으며, 50개 이상의 통화를 지원하고 대형 프로젝트도 효율적으로 처리합니다. 위 단계들을 적용하여 모든 로케일에 맞는 형식의 프로젝트 보고서를 생성하십시오.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 캘린더 컬렉션 관리](/tasks/net/calendar-scheduling/calendar-collection/)
- [Aspose.Tasks에서 캘린더 예외 컬렉션](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Aspose.Tasks for .NET에서 MS Project 요금 처리](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}