---
date: 2026-01-02
description: Aspose.Tasks for Java를 사용하여 비용 편차를 계산하고 프로젝트 비용 관리를 수행하는 방법을 배우세요. 할당
  비용, 예산 비용 작업 수행 및 일정 편차 계산을 처리하기 위한 단계별 가이드.
linktitle: Handle Assignment Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 비용 편차를 계산하고 할당 비용을 관리하는 방법
url: /ko/java/resource-assignments/assignment-cost/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 비용 편차를 계산하고 할당 비용을 관리하는 방법

## 소개
효과적인 **비용 편차 계산**은 견고한 *프로젝트 비용 관리*의 핵심입니다. 작은 팀이든 대규모 엔터프라이즈 프로그램이든, 계획된 비용과 실제 비용의 차이를 알면 초기 단계에서 정보에 입각한 결정을 내릴 수 있습니다. 이 튜토리얼에서는 **Aspose.Tasks for Java**를 사용하여 할당 비용을 읽고, 비용 편차를 계산하며, 수행된 예산 비용(BCWP) 및 일정 편차 계산과 같은 관련 메트릭을 검사하는 방법을 단계별로 안내합니다.

## 빠른 답변
- **“비용 편차를 계산한다”는 의미는 무엇인가요?** 수행된 작업의 획득 가치와 실제 비용 간의 차이를 측정합니다.  
- **어떤 API 속성이 비용 편차를 제공하나요?** `ResourceAssignment` 객체의 `Asn.CV`입니다.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 평가용 무료 체험판으로 실행할 수 있으며, 프로덕션에서는 라이선스가 필요합니다.  
- **지원되는 프로젝트 파일 형식은 무엇인가요?** MPP, XML, MPX 등 다수의 형식을 지원합니다.  
- **특별한 설정이 필요합니까?** Aspose.Tasks JAR 파일을 클래스패스에 추가하고 프로젝트 파일을 로드하기만 하면 됩니다.

## 사전 요구 사항
코드 작성을 시작하기 전에 다음을 준비하십시오:

1. **Java Development Kit (JDK)** – 버전 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java Library** – [웹사이트](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. Java 문법 및 Maven/Gradle 프로젝트 설정에 대한 기본적인 이해.

## 패키지 가져오기
Java 소스 파일에 필요한 클래스를 먼저 가져옵니다:

```java
import com.aspose.tasks.*;
import java.math.BigDecimal;
```

## 1단계: 프로젝트 파일 로드
기존 Microsoft Project 파일을 가리키는 `Project` 인스턴스를 생성합니다:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 2단계: 리소스 할당 순회
이제 모든 `ResourceAssignment`를 순회하면서 비용 관련 필드를 읽고 **비용 편차를 계산**합니다. 또한 *실제 작업 비용*과 *예산 작업 비용*을 가져오는 방법도 보여줍니다.

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

### 이러한 필드가 중요한 이유
- **`Asn.COST`** – 할당에 대해 계획된 총 비용.  
- **`Asn.ACWP`** – 현재까지 수행된 *실제 작업 비용*.  
- **`Asn.CV`** – **비용 편차 계산** 결과 (`BCWP - ACWP`).  
- **`Asn.BCWP`** – *예산 작업 비용*을 나타내며, 획득 가치 분석의 핵심 입력값입니다.  
- **`Asn.SV`** – 작업이 일정보다 앞서 있는지 뒤처지는지를 확인하기 위한 *일정 편차 계산*에 사용됩니다.

## 일반적인 함정 및 팁
- **Null 값:** 일부 할당에는 비용 데이터가 채워져 있지 않을 수 있습니다. 연산을 수행하기 전에 항상 `null` 여부를 확인하십시오.  
- **통화 처리:** 비용은 `BigDecimal`로 저장됩니다. 특정 소수점 자리수가 필요하면 `setScale`을 사용하십시오.  
- **성능:** 매우 큰 프로젝트의 경우, 할당을 필터링(`project.getResourceAssignments().where(...)`)하여 순회 오버헤드를 줄이는 것을 고려하십시오.

## 결론
Aspose.Tasks for Java를 활용하면 **비용 편차를 손쉽게 계산**하고, *실제 작업 비용*을 모니터링하며, *예산 작업 비용* 및 *일정 편차*를 지속적으로 확인할 수 있습니다. 이러한 인사이트는 보다 스마트한 *프로젝트 비용 관리*를 가능하게 하여 예산과 일정 모두를 준수하도록 돕습니다.

## FAQ
### Q: Aspose.Tasks for Java를 사용해 리소스 할당 비용을 동적으로 계산할 수 있나요?
A: 네, Aspose.Tasks for Java API를 사용해 할당 비용을 동적으로 계산할 수 있습니다.  
### Q: Aspose.Tasks for Java가 모든 프로젝트 파일 형식을 지원하나요?
A: Aspose.Tasks for Java는 MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 지원합니다.  
### Q: Aspose.Tasks for Java에 대한 지원은 어떻게 받을 수 있나요?
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 문의하거나 Aspose 지원팀에 직접 연락하면 됩니다.  
### Q: 구매 전에 Aspose.Tasks for Java를 체험해 볼 수 있나요?
A: 네, [웹사이트](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.  
### Q: 체험판 사용 시 임시 라이선스가 필요합니까?
A: 체험판 사용에는 임시 라이선스가 필요하지 않지만, 프로덕션 환경에서는 라이선스를 권장합니다.

## 자주 묻는 질문

**Q: 계산된 비용 편차를 Excel 보고서로 내보내려면 어떻게 해야 하나요?**  
A: 할당을 순회한 후 Aspose.Cells를 사용해 각 할당의 ID와 CV 값을 스프레드시트에 기록하면 됩니다.

**Q: 편차를 계산하기 전에 특정 리소스별로 할당을 필터링할 수 있나요?**  
A: 네, `project.getResourceAssignments().where(ra -> ra.getResource().getUid() == desiredResourceId)`와 같이 필터링하여 루프를 제한할 수 있습니다.

**Q: 비용 편차가 음수이면 무엇을 의미하나요?**  
A: 음수 CV는 실제 비용(ACWP)이 획득 가치(BCWP)를 초과했음을 의미하며, 초과 원인을 조사해야 합니다.

**Q: 비용 필드를 프로그래밍 방식으로 업데이트하고 프로젝트를 저장할 수 있나요?**  
A: 물론입니다. `ra.set(Asn.COST, new BigDecimal("1500"))`를 호출한 뒤 `project.save("updated.mpp")`를 실행하면 됩니다.

**Q: Aspose.Tasks가 자동으로 통화 변환을 처리하나요?**  
A: 라이브러리는 원시 숫자 값을 저장하므로, 표시 전에 필요한 변환 로직을 직접 구현해야 합니다.

---

**마지막 업데이트:** 2026-01-02  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}