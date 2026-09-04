---
date: 2026-07-05
description: Aspose.Tasks for .NET를 사용하여 프로젝트 예산을 추적하고 프로젝트 비용을 관리하는 방법을 배웁니다. 정확한
  비용 추적을 위해 Cost Accrual Types를 정의합니다.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks의 Cost Accrual Types
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 Cost Accrual Types를 사용하여 프로젝트 예산 추적
url: /ko/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 비용 발생 유형으로 프로젝트 예산 추적

## 소개

정확하게 **프로젝트 예산 추적**은 성공적인 프로젝트 전달의 핵심입니다. 비용 정보가 적절한 시점에 캡처되면 초과 지출을 예측하고, 리소스를 조정하며, 이해관계자에게 정보를 제공할 수 있습니다. Aspose.Tasks for .NET은 개발자에게 비용 발생을 세밀하게 제어할 수 있는 기능을 제공하여, 작업 시작 시점, 지속적으로, 혹은 작업이 완료될 때만 비용을 기록할지 결정할 수 있게 합니다. 이 튜토리얼에서는 개념을 설명하고, 발생 유형을 설정하는 방법을 보여주며, 신뢰할 수 있는 예산 추적을 위한 모범 사례를 시연합니다.

## 빠른 답변
- **비용 발생 유형의 주요 목적은 무엇인가요?** 작업 수명 주기에서 비용이 인식되는 시점을 결정하여 정확한 예산 추적을 가능하게 합니다.  
- **작업이 완료될 때까지 비용을 지연시키는 열거값은 무엇인가요?** `CostAccrualType.End`.  
- **코드를 실행하려면 라이선스가 필요합니까?** 예, 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **여러 리소스의 발생 유형을 한 번에 변경할 수 있나요?** 예—`Resources` 컬렉션을 순회하면서 원하는 유형을 할당하면 됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 비용 발생 유형이란?
**비용 발생 유형**은 Aspose.Tasks가 리소스 비용을 프로젝트 예산에 적용하는 시점을 알려줍니다. 이는 `CostAccrualType` 열거형으로 표현되며 리소스별 또는 작업별로 설정할 수 있습니다. 올바른 유형을 선택하면 비용 데이터가 조직의 청구 정책에 맞게 정렬되어, 작업 시작 시점, 기간에 걸쳐 비례 배분, 혹은 완료 후에만 비용이 기록되는지를 제어할 수 있습니다.

## 비용 발생 유형을 사용하여 프로젝트 예산을 추적하는 이유
Aspose.Tasks는 **네 가지** 발생 옵션—`Start`, `Prorated`, `Duration`, `End`—을 지원하여 일반적인 프로젝트 회계 시나리오를 모두 포괄합니다. 적절한 옵션을 선택하면 계약 청구 주기에 맞춰 비용 인식을 맞출 수 있어 재무 보고서의 편차를 줄이고, ERP 시스템과 원활히 통합되는 비용 명세서를 생성할 수 있으며, 대규모 프로젝트에서도 메모리 사용량을 최소화할 수 있습니다.

## 전제 조건

시작하기 전에 다음 전제 조건을 확인하십시오:

### 1. Aspose.Tasks for .NET 설치
시작하려면 개발 환경에 Aspose.Tasks for .NET이 설치되어 있어야 합니다. 라이브러리는 [download page](https://releases.aspose.com/tasks/net/)에서 다운로드할 수 있으며 제공된 설치 지침을 따르세요.

### 2. .NET Framework에 대한 친숙도
예제 코드를 따라가기 위해서는 .NET 프레임워크와 C# 프로그래밍 언어에 대한 기본 지식이 필요합니다.

## 리소스에 대한 비용 발생 유형 설정 방법?

프로젝트를 로드하고 대상 리소스를 찾은 다음 원하는 `CostAccrualType`을 할당합니다. 아래의 두 줄 패턴이 표준 접근 방식이며, `Project` 인스턴스를 생성하고 ID로 리소스를 검색한 뒤 `CostAccrualType`을 설정합니다. 이 간결한 순서는 리소스가 추가되는 순간부터 **프로젝트 예산을 정확히 추적**할 수 있게 합니다.

### 단계 1: 네임스페이스 가져오기
Aspose.Tasks 기능에 접근하기 위해 필요한 네임스페이스를 가져옵니다:

```csharp

```

네임스페이스를 준비했으니 이제 프로젝트 파일을 로드할 차례입니다.

### 단계 2: 프로젝트 파일 로드
`Project` 클래스는 Microsoft Project 파일을 나타내며 작업, 리소스 및 기타 데이터를 접근할 수 있게 합니다.

```csharp
var project = new Project("Project2.mpp");
```

먼저 프로젝트 파일을 애플리케이션에 로드해야 합니다. 새 `Project` 객체를 생성하고 프로젝트 파일 경로를 전달합니다.

### 단계 3: 리소스 접근
`Resources` 컬렉션은 프로젝트에 정의된 모든 리소스를 보유합니다. `GetById` 메서드는 고유 식별자로 리소스를 검색합니다.

```csharp
var resource = project.Resources.GetById(1);
```

다음으로 비용 발생 유형을 적용하려는 리소스에 접근합니다. `Resources` 컬렉션의 `GetById` 메서드에 리소스 ID를 전달하면 됩니다. 이는 **ID로 리소스 접근**이라는 일반적인 요구 사항을 보여줍니다.

### 단계 4: 비용 발생 유형 설정
`Set` 메서드는 리소스 필드에 값을 할당합니다.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

여기서는 리소스의 비용 발생 유형을 설정합니다. 예제에서는 `CostAccrualType.End`로 설정하고 있으며, 이는 남은 작업이 0이 될 때까지 비용이 발생되지 않음을 의미합니다. 작업이 완전히 완료된 후에만 **프로젝트 예산을 추적**하려는 경우 `End`가 이상적입니다.

### 단계 5: 프로젝트 작업 계속하기
비용 발생 유형을 설정한 후에는 필요에 따라 프로젝트에서 추가 작업을 수행할 수 있습니다. 예를 들어 비용 보고서를 생성하거나 할당을 업데이트하거나 파일을 내보내는 등의 작업을 진행할 수 있습니다.

## 일반적인 함정 및 전문가 팁
- **전문가 팁:** 발생 유형을 수정한 후에는 반드시 `project.Save`를 호출하여 변경 사항을 영구 저장하십시오.  
- **함정:** `CostAccrualType.Start`를 작업이 시작되지 않을 리소스에 설정하면 예산 보고서가 부풀어 오를 수 있으니 작업 일정을 먼저 확인하십시오.  
- **전문가 팁:** 많은 리소스를 일괄 업데이트해야 할 경우 `project.Resources.ToList()`를 사용하면 컬렉션 조회를 반복하지 않아 대규모 프로젝트에서 성능이 향상됩니다.

## 자주 묻는 질문

**Q: 여러 리소스의 비용 발생 유형을 동시에 변경할 수 있나요?**  
A: 예, `project.Resources`를 순회하면서 `foreach` 루프 내에서 원하는 `CostAccrualType`을 각 리소스에 할당하면 됩니다.

**Q: `End` 외에 사용할 수 있는 다른 비용 발생 유형은 무엇인가요?**  
A: Aspose.Tasks는 `Start`, `Prorated`, `Duration`을 제공하며, 각각은 다른 청구 전략에 맞춰 사용됩니다.

**Q: 특정 리소스의 현재 비용 발생 유형을 어떻게 확인할 수 있나요?**  
A: `resource.Get(TskResource.CostAccrualType)`을 호출하면 현재 설정을 나타내는 열거형 값을 반환합니다.

**Q: 동일 프로젝트 내에서 작업마다 다른 비용 발생 유형을 적용할 수 있나요?**  
A: 물론 가능합니다. 작업과 리소스 모두 `CostAccrualType` 속성을 노출하므로 엔터티별로 독립적인 구성이 가능합니다.

**Q: Aspose.Tasks가 사용자 정의 비용 발생 유형을 지원하나요?**  
A: 아니요, 현재 라이브러리는 네 가지 내장 유형만 지원합니다. 사용자 정의 로직이 필요하면 외부에서 구현해야 합니다.

---

**마지막 업데이트:** 2026-07-05  
**테스트 환경:** Aspose.Tasks 24.8 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks 캘린더 및 일정 관리](/tasks/net/calendar-scheduling/)
- [Aspose.Tasks for .NET을 사용한 MS Project 요금 처리](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Aspose.Tasks로 MS Project 리소스를 손쉽게 관리](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}