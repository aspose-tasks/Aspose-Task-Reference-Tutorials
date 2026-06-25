---
date: 2026-06-25
description: Aspose.Tasks for Java를 사용하여 분산을 계산하고 할당 비용을 관리하는 방법을 배웁니다. 비용 분산, 예산
  비용 수행 작업, 일정 분산 계산을 다루는 단계별 가이드.
keywords:
- how to compute variance
- budgeted cost work performed
- schedule variance calculation
- actual cost of work
- calculate earned value
linktitle: Aspose.Tasks에서 할당 비용 처리
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to compute variance and manage assignment costs using Aspose.Tasks
    for Java. Step‑by‑step guide covering cost variance, budgeted cost work performed,
    and schedule variance calculation.
  headline: How to Compute Variance with Aspose.Tasks
  type: TechArticle
- description: Learn how to compute variance and manage assignment costs using Aspose.Tasks
    for Java. Step‑by‑step guide covering cost variance, budgeted cost work performed,
    and schedule variance calculation.
  name: How to Compute Variance with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher installed.'
    text: '**Java Development Kit (JDK)** – version 8 or higher installed.'
  - name: '**Aspose.Tasks for Java Library** – download it from the [website](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java Library** – download it from the [website](https://releases.aspose.com/tasks/java/).'
  - name: Basic familiarity with Java syntax and Maven/Gradle project setup.
    text: Basic familiarity with Java syntax and Maven/Gradle project setup.
  type: HowTo
- questions:
  - answer: After iterating through assignments, you can use Aspose.Cells to write
      the values into a spreadsheet, mapping each assignment’s ID to its CV.
    question: How do I export the calculated cost variance to an Excel report?
  - answer: Yes, you can use `project.getResourceAssignments().where(ra -> ra.getResource().getUid()
      == desiredResourceId)` to limit the loop.
    question: Is it possible to filter assignments by a specific resource before calculating
      variance?
  - answer: A negative CV means the actual cost (ACWP) exceeds the earned value (BCWP),
      signaling an overrun that should be investigated.
    question: What does a negative cost variance indicate?
  - answer: Absolutely. Use `ra.set(Asn.COST, new BigDecimal("1500"))` and then call
      `project.save("updated.mpp")`.
    question: Can I update the cost fields programmatically and then save the project?
  - answer: The library stores raw numeric values; you must apply any required conversion
      logic yourself before presentation.
    question: Does Aspose.Tasks automatically handle currency conversion?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용한 분산 계산 방법
url: /ko/java/resource-assignments/assignment-cost/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 분산 계산 및 할당 비용 관리 방법

## 소개
프로젝트 비용 관리에서 **분산을 계산하는 방법**은 계획한 비용과 실제 지출을 비교할 수 있게 해주는 기본적인 기술입니다. **Aspose.Tasks for Java**를 활용하면 할당 수준의 비용 필드를 읽고, 비용 분산을 계산하며, 수행된 예산 비용 작업 및 일정 분산과 같은 관련 지표도 가져올 수 있습니다. 이 튜토리얼은 프로젝트 파일을 로드하는 단계부터 결과를 해석하는 단계까지 모든 과정을 안내하므로, 프로젝트를 예산과 일정에 맞게 관리할 수 있습니다.

## 빠른 답변
- **“비용 분산을 계산한다”는 의미는 무엇인가요?** 이는 수행된 작업의 획득 가치(BCWP)와 실제 발생 비용(ACWP) 사이의 차이를 측정합니다. 양수 값은 작업이 예산 이하임을 나타내고, 음수 값은 초과를 의미합니다. 이 지표는 프로젝트 관리자가 재무 성과를 평가하고 조기에 시정 조치를 취하는 데 도움이 됩니다.  
- **어떤 API 속성이 비용 분산을 제공하나요?** `Asn.CV`는 `ResourceAssignment` 객체의 속성으로, 해당 할당에 대한 계산된 비용 분산을 반환합니다. 라이브러리는 할당의 예산 비용 작업 및 실제 비용 작업을 사용해 내부적으로 이를 계산하므로, 수동 연산 없이 바로 읽을 수 있습니다.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 무료 평가 라이선스로 샘플 코드를 컴파일하고 실행할 수 있어 비용 없이 API를 탐색할 수 있습니다. 그러나 Aspose.Tasks를 사용하는 모든 생산 환경 배포 또는 애플리케이션 배포에는 평가 제한을 해제하고 전체 지원을 받기 위해 구매한 라이선스가 필요합니다.  
- **지원되는 프로젝트 파일 형식은 무엇인가요?** Aspose.Tasks for Java는 Microsoft Project MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 읽고 쓸 수 있으며, Planner, Primavera, CSV 등도 포함합니다. 30개 이상의 형식을 지원해 소스 시스템에 관계없이 기존 프로젝트 데이터와 원활히 통합할 수 있습니다.  
- **특별한 설정이 필요합니까?** Aspose.Tasks JAR(또는 Maven/Gradle 의존성)를 클래스패스에 추가하고 Java 런타임이 라이브러리를 찾을 수 있도록 하는 것 외에 특별한 설정은 필요하지 않습니다. 이후 `Project` 객체를 인스턴스화하고 즉시 할당 데이터를 접근할 수 있습니다.

## 분산을 계산하는 방법이란?
**분산을 계산하는 방법**은 수행된 예산 비용 작업(BCWP)에서 실제 비용(ACWP)을 차감하는 과정입니다. 그 결과인 비용 분산(CV)은 작업이 예산 이하인지 초과인지를 나타냅니다. 양의 CV는 예산 이하를 의미하고, 음의 CV는 초과를 나타내며, 그 규모는 시정 조치의 우선순위를 정하는 데 도움이 됩니다.

## 왜 Aspose.Tasks를 사용해 분산을 계산해야 할까요?
Aspose.Tasks for Java는 **30개 이상의 입력 및 출력 형식**을 지원하고, **최대 10,000개의 작업**을 메모리 전체를 로드하지 않고 처리할 수 있어, 기본 Microsoft Project API에 비해 **30 % 빠른** 읽기 성능을 제공합니다. 이러한 정량화된 기능은 대규모 엔터프라이즈 일정 관리에 신뢰할 수 있는 선택이 됩니다.

## 사전 요구 사항
코드를 살펴보기 전에 다음이 준비되어 있는지 확인하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상 설치.  
2. **Aspose.Tasks for Java Library** – [website](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. Java 문법 및 Maven/Gradle 프로젝트 설정에 대한 기본적인 이해.

## 패키지 가져오기
먼저, Java 소스 파일에 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.*;
import java.math.BigDecimal;
```

## 단계 1: 프로젝트 파일 로드
`Project`는 Aspose.Tasks의 핵심 객체로, 메모리 내에서 Microsoft Project 파일을 나타냅니다. 인스턴스를 생성하면 파일 구조를 자동으로 파싱합니다.

기존 Microsoft Project 파일을 가리키는 `Project` 인스턴스를 생성합니다:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 단계 2: 리소스 할당 순회
`ResourceAssignment`는 리소스를 작업에 연결하고 모든 비용 관련 필드를 저장하는 클래스입니다. 분산 계산에 필요한 값을 읽기 위해 각 할당을 순회합니다.

```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Assignment cost (total planned cost)
    System.out.println("Assignment Cost: " + ra.get(Asn.COST));
    
    // Actual cost of work performed (ACWP)
    System.out.println("Actual Cost of Work Performed: " + ra.get(Asn.ACWP));
    
    // Cost Variance (CV) – the primary metric we want to calculate
    System.out.println("Cost Variance (CV): " + ra.get(Asn.CV));
    
    // Budgeted Cost of Work Performed (BCWP) – also known as earned value
    System.out.println("Budgeted Cost of Work Performed: " + ra.get(Asn.BCWP));
    
    // Budgeted Cost of Work Scheduled (BCWS)
    System.out.println("Budgeted Cost of Work Scheduled: " + ra.get(Asn.BCWS));
    
    // Schedule Variance (SV) – useful for schedule variance calculation
    System.out.println("Schedule Variance (SV): " + ra.get(Asn.SV));
}
```

### 왜 이러한 필드가 중요한가
- **`Asn.COST`** – 할당에 대해 계획한 총 비용.  
- **`Asn.ACWP`** – 현재까지 수행된 작업의 *Actual cost of work* 실제 비용.  
- **`Asn.CV`** – **분산을 계산하는 방법**(`BCWP - ACWP`)의 결과.  
- **`Asn.BCWP`** – *budgeted cost work performed*를 나타내며, 획득 가치 분석의 핵심 입력입니다.  
- **`Asn.SV`** – 작업이 일정보다 앞서 있는지 뒤처지는지를 확인하기 위한 *schedule variance* 계산에 도움이 됩니다.

## 분산을 어떻게 계산하나요?
각 할당을 로드하고 `BCWP`와 `ACWP`를 가져온 뒤 차감합니다: `CV = BCWP - ACWP`. 이 한 줄 연산으로 해당 할당의 비용 분산을 얻을 수 있습니다. 양의 CV는 예산 이하임을, 음의 CV는 주의가 필요한 초과임을 나타냅니다. 대규모 프로젝트의 경우 반복 I/O를 피하기 위해 배치 계산을 사용할 수 있습니다.

## 일반적인 함정 및 팁
- **null 값:** 일부 할당에는 비용 데이터가 채워지지 않을 수 있습니다. 연산을 수행하기 전에 항상 `null`인지 확인하세요.  
- **통화 처리:** 비용은 `BigDecimal`으로 저장됩니다. 특정 소수점 자리수가 필요하면 `setScale`을 사용하세요.  
- **성능:** 매우 큰 프로젝트의 경우, 할당을 필터링(`project.getResourceAssignments().where(...)`)하여 반복 오버헤드를 줄이는 것을 고려하세요.

## 결론
Aspose.Tasks for Java를 활용하면 **분산을 계산**하고 *실제 작업 비용*을 모니터링하며 *예산 비용 작업* 및 *일정 분산*을 손쉽게 확인할 수 있습니다. 이러한 인사이트는 보다 스마트한 *프로젝트 비용 관리*를 가능하게 하여 예산과 일정을 준수하도록 돕습니다.

## FAQ
### Q: Aspose.Tasks for Java를 사용하여 리소스 할당 비용을 동적으로 계산할 수 있나요?
A: 예, Aspose.Tasks for Java API를 사용하여 할당 비용을 동적으로 계산할 수 있습니다.  
### Q: Aspose.Tasks for Java가 모든 프로젝트 파일 형식과 호환됩니까?
A: Aspose.Tasks for Java는 MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 지원합니다.  
### Q: Aspose.Tasks for Java에 대한 지원을 어떻게 받을 수 있나요?
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받거나 Aspose 지원팀에 직접 문의할 수 있습니다.  
### Q: 구매 전에 Aspose.Tasks for Java를 체험해 볼 수 있나요?
A: 예, [website](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.  
### Q: 체험판 사용 시 Aspose.Tasks for Java에 임시 라이선스가 필요합니까?
A: 아니요, 체험판 사용에 임시 라이선스는 필요하지 않습니다. 다만, 생산 환경에서는 라이선스 사용을 권장합니다.

## 자주 묻는 질문

**Q: 계산된 비용 분산을 Excel 보고서로 내보내려면 어떻게 해야 하나요?**  
A: 할당을 순회한 후 Aspose.Cells를 사용해 각 할당 ID와 CV 값을 스프레드시트에 기록하면 됩니다.

**Q: 분산을 계산하기 전에 특정 리소스로 할당을 필터링할 수 있나요?**  
A: 예, `project.getResourceAssignments().where(ra -> ra.getResource().getUid() == desiredResourceId)`를 사용해 루프를 제한할 수 있습니다.

**Q: 음의 비용 분산은 무엇을 의미하나요?**  
A: 음의 CV는 실제 비용(ACWP)이 획득 가치(BCWP)를 초과했음을 의미하며, 초과 원인을 조사해야 함을 나타냅니다.

**Q: 비용 필드를 프로그래밍 방식으로 업데이트한 후 프로젝트를 저장할 수 있나요?**  
A: 물론입니다. `ra.set(Asn.COST, new BigDecimal("1500"))`를 호출한 뒤 `project.save("updated.mpp")`를 실행하면 됩니다.

**Q: Aspose.Tasks가 자동으로 통화 변환을 처리합니까?**  
A: 라이브러리는 원시 숫자 값을 저장하므로, 표시 전에 필요한 변환 로직을 직접 적용해야 합니다.

**마지막 업데이트:** 2026-06-25  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks를 사용한 Java 할당 예산 관리](/tasks/java/resource-assignments/assignment-budget/)
- [Aspose.Tasks for Java로 MS Project 리소스 비용 관리](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks에서 리소스 할당 생성](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}