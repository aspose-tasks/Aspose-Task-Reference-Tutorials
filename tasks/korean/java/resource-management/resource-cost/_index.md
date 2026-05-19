---
date: 2026-01-15
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에 예정된 예산 비용 작업을 처리하는
  방법을 배워보세요. 단계별 가이드를 따라가세요.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용한 예산 비용 작업 일정
url: /ko/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java와 함께 예산 비용 작업 일정

## 소개

**예산 비용 작업 일정**(BCWS)을 관리하는 것은 프로젝트를 정상 궤도에 유지하고 재무 예측이 계획된 작업과 일치하도록 하는 데 필수적입니다. Microsoft Project에서 BCWS는 특정 날짜까지 일정된 작업에 대해 지출되었어야 할 금액을 나타냅니다. Aspose.Tasks for Java는 이러한 값을 완전하게 프로그래밍 방식으로 제어할 수 있게 해 주며, .mpp 파일을 수동으로 열지 않고도 리소스 비용을 읽고, 수정하고, 보고할 수 있습니다. 이 튜토리얼에서는 프로젝트를 로드하고, 리소스를 순회하며, 다른 주요 비용 지표와 함께 예산 비용 작업 일정을 표시하는 전체 예제를 단계별로 살펴보겠습니다.

## 빠른 답변
- **BCWS는 무엇을 의미하나요?** Budgeted Cost Work Scheduled – 현재까지 일정된 작업에 대한 계획 비용.  
- **어떤 API 속성이 BCWS를 반환하나요?** `Rsc.BCWS` (Resource 객체).  
- **샘플을 실행하려면 라이선스가 필요하나요?** 평가용 무료 라이선스로 테스트가 가능하지만, 실제 운영에는 정식 라이선스가 필요합니다.  
- **BCWS 값을 수정할 수 있나요?** 예, 다른 숫자 필드와 마찬가지로 `Rsc.BCWS`를 설정할 수 있습니다.  
- **지원되는 Project 버전은?** 2000부터 최신 .mpp 형식까지 모든 Microsoft Project 버전.

## 예산 비용 작업 일정이란?

**Budgeted Cost Work Scheduled (BCWS)** 은 특정 시점까지 계획된 작업에 대해 발생했어야 할 비용을 나타내는 성과 측정 지표입니다. 이는 Earned Value Management (EVM)의 핵심 요소이며, 프로젝트 관리자가 계획 대비 실제 지출을 비교하는 데 도움을 줍니다.

## 사전 요구 사항

코드에 들어가기 전에 다음을 준비하십시오:

1. Java 기본 지식이 탄탄함.  
2. 프로젝트에 Aspose.Tasks for Java가 추가되어 있음 (Maven/Gradle 또는 JAR).  
3. 비용 데이터가 포함된 Microsoft Project 파일(`.mpp`)이 있음 (예: *ResourceCosts.mpp*).

## 패키지 가져오기

프로젝트와 리소스를 처리하는 데 필요한 Aspose.Tasks 클래스를 먼저 가져옵니다:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 단계 1: 데이터 디렉터리 정의

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 *ResourceCosts.mpp* 파일이 위치한 절대 경로나 상대 경로로 교체하십시오.

## 단계 2: MS Project 파일 로드

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

`Project` 생성자는 .mpp 파일을 읽어 메모리 내 표현을 구축합니다. 이를 통해 쿼리가 가능합니다.

## 단계 3: 리소스 순회

```java
for (Resource res : prj.getResources()) {
```

이 루프는 프로젝트에 정의된 모든 리소스를 순회하면서 비용 필드에 접근할 수 있게 해 줍니다.

## 단계 4: 리소스 이름 및 비용 확인

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

`if` 블록 내부에서 수행하는 작업:

* **총 비용** (`Rsc.COST`) 출력.  
* **실제 수행 작업 비용** (`Rsc.ACWP`) 출력.  
* **예산 비용 작업 일정** (`Rsc.BCWS`) – 이번 튜토리얼의 핵심 지표.  
* **예산 비용 수행 작업** (`Rsc.BCWP`) 출력.

이 네 가지 값으로 프로젝트의 재무 현황을 빠르게 파악할 수 있습니다.

## 예산 비용 작업 일정을 모니터링해야 하는 이유

* **조기 경고:** BCWS가 실제 비용보다 크게 높으면 리소스 과다 할당 가능성이 있습니다.  
* **Earned Value 분석:** BCWS는 Cost Variance (CV)와 Schedule Variance (SV)를 계산하는 핵심 입력값입니다.  
* **예측:** 정확한 BCWS 데이터는 향후 현금 흐름 필요성을 예측하고 이해관계자 보고에 활용됩니다.

## 일반적인 문제 및 해결 방법

| 증상 | 가능 원인 | 해결 방법 |
|------|----------|-----------|
| BCWS가 `null` 로 출력됨 | 리소스에 비용 요율 표가 정의되지 않음 | Microsoft Project에서 해당 리소스에 비용 요율 표를 지정하거나 `Rsc.COST_RATE_TABLE`을 통해 프로그래밍 방식으로 설정 |
| 리소스 순회 시 `ArrayIndexOutOfBoundsException` 발생 | 프로젝트 파일이 손상되었거나 빈 리소스 항목이 포함됨 | Microsoft Project에서 .mpp 파일을 검증하고 빈 리소스를 제거 |
| 예상치 못한 값(예: 음수 BCWS) | 사용자 정의 필드가 표준 비용 필드를 덮어씀 | 표준 `Rsc.BCWS`에 접근하고 동일한 이름의 사용자 정의 필드가 없는지 확인 |

## 자주 묻는 질문

**Q: BCWS 값을 프로그래밍 방식으로 업데이트할 수 있나요?**  
A: 예. `res.set(Rsc.BCWS, newValue)`를 사용하고 `prj.save("Updated.mpp")`로 프로젝트를 저장하면 됩니다.

**Q: Aspose.Tasks가 다중 통화 프로젝트를 지원하나요?**  
A: 물론입니다. 비용 필드는 프로젝트 파일에 정의된 통화 설정을 따릅니다.

**Q: 이러한 비용 지표를 CSV로 내보낼 방법이 있나요?**  
A: 리소스를 순회하면서 값을 `StringBuilder`에 기록하거나 CSV 라이브러리를 사용해 파일을 생성하면 됩니다.

**Q: BCWS와 BCWP는 어떻게 다른가요?**  
A: BCWS는 일정된 작업에 대한 계획 비용이며, BCWP(예산 비용 수행 작업)는 실제 완료된 작업에 대한 계획 비용을 나타냅니다.

**Q: 비용 데이터를 읽기 위해 특별한 라이선스가 필요합니까?**  
A: 평가 라이선스로도 전체 읽기/쓰기 접근이 가능하지만, 실제 운영 환경에서는 상용 라이선스가 필요합니다.

## 결론

Aspose.Tasks for Java를 활용하면 **예산 비용 작업 일정** 및 기타 핵심 비용 지표에 대한 정확하고 프로그래밍 가능한 접근이 가능합니다. 이를 통해 맞춤형 대시보드를 구축하고 Earned Value 보고서를 자동화하며, Microsoft Project와 수동으로 상호 작용하지 않고도 프로젝트 재무를 체계적으로 관리할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-15  
**테스트 환경:** Aspose.Tasks for Java 24.12 (최신)  
**작성자:** Aspose