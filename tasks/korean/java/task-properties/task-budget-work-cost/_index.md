---
date: 2026-02-28
description: Aspose.Tasks를 사용하여 Java 프로젝트의 작업에 대한 예산, 작업량 및 비용을 관리하는 방법을 배웁니다. 이 가이드는
  작업 비용을 효율적으로 계산하는 방법도 보여줍니다.
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java에서 예산, 작업 및 비용 관리 방법
url: /ko/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Java에서 예산, 작업 및 비용 관리 방법

프로젝트의 재무를 관리하는 것은 모든 프로젝트 매니저의 핵심 책임입니다. 이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 작업, 작업량 및 리소스에 대한 **예산 관리 방법**을 배우고, 정확한 재무 보고가 필요할 때 **작업 비용을 계산하는 방법**도 확인할 수 있습니다. 가이드를 끝까지 읽으면 Microsoft Project 파일에서 예산 관련 필드를 직접 읽고, 표시하고, 조작할 수 있게 됩니다.

## 빠른 답변
- **예산 작업(budget work)** 은 무엇을 의미하나요? 작업 또는 리소스에 할당된 작업량(시간)입니다.  
- **예산 비용을 프로그래밍 방식으로 가져올 수 있나요?** 예, 작업, 리소스 또는 할당에 대한 `BUDGET_COST` 필드를 사용하면 됩니다.  
- **Aspose.Tasks에 라이선스가 필요합니까?** 프로덕션에서는 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Java 버전은 무엇인가요?** Aspose.Tasks는 Java 8 이상에서 작동합니다.  
- **할당에서 작업 비용을 계산할 수 있나요?** 물론입니다 – 할당의 `BUDGET_COST` 값을 합산하면 됩니다.  

## Aspose.Tasks에서 예산 관리란?
Aspose.Tasks는 작업, 리소스 및 할당에 대해 전용 필드(`BUDGET_WORK`, `BUDGET_COST`)에 예산 정보를 저장합니다. 이러한 필드를 사용하면 실제 작업이 수행되기 전에 예상 작업량과 금전적 비용을 계획할 수 있어 정확한 예측 및 차이 분석이 가능합니다.

## 작업 비용을 계산해야 하는 이유
- 원래 추정치 대비 재무 성과를 추적합니다.  
- 이해관계자를 위한 비용 기반 보고서를 생성합니다.  
- 예산을 초과하는 작업을 조기에 식별합니다.  

## 사전 요구 사항
코드 작성을 시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- Java 개발 환경 (JDK 8 이상).  
- Aspose.Tasks for Java 라이브러리 – **[here](https://releases.aspose.com/tasks/java/)** 에서 다운로드하십시오.  
- 예시 Microsoft Project 파일(예: `BudgetWorkAndCost.mpp`)을 알려진 디렉터리에 배치합니다.  

## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져오는 것으로 시작합니다. 이렇게 하면 Aspose.Tasks 기능에 접근할 수 있습니다. Java 파일의 시작 부분에 다음 코드를 포함하십시오:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 단계 1: 문서 디렉터리 설정
먼저 문서 디렉터리 경로를 설정합니다. 여기에는 프로젝트 파일이 저장됩니다.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 단계 2: 프로젝트 로드
Aspose.Tasks 라이브러리를 사용하여 프로젝트 파일을 로드합니다. `"BudgetWorkAndCost.mpp"`를 실제 프로젝트 파일 이름으로 교체하십시오.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## 단계 3: 프로젝트 및 리소스 예산 가져오기
프로젝트 수준 및 리소스 수준의 예산을 가져와 표시합니다. 이 단계에서는 저장된 값을 읽어 **작업 비용을 계산하는 방법**을 보여줍니다.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## 단계 4: 할당 예산 표시
요약 작업(또는 任意 작업)의 할당을 반복하면서 각 할당의 예산 정보를 표시합니다. 이를 통해 리소스당 할당된 비용을 확인할 수 있습니다.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## 일반적인 문제 및 전문가 팁
- **Null 값:** 예산 필드가 `null`을 반환하면 프로젝트 파일에 해당 데이터가 없을 수 있습니다. 출력하기 전에 `project.getRootTask().get(Tsk.BUDGET_WORK) != null` 검사를 사용하십시오.  
- **Incorrect UID:** 조회하려는 리소스 UID(`getByUid(2)`)가 존재하는지 확인하십시오; 그렇지 않으면 `NullPointerException`이 발생합니다.  
- **Currency formatting:** `BUDGET_COST`는 원시 double 값을 반환합니다. 사용자 친화적인 출력을 위해 `NumberFormat.getCurrencyInstance()`를 사용해 포맷하십시오.  

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 다른 Java 프레임워크와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다양한 Java 프레임워크와 호환되어 통합 시 유연성을 제공합니다.

**Q: Aspose.Tasks for Java의 체험 버전을 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java의 무료 체험판을 **[here](https://releases.aspose.com/)** 에서 이용할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 추가 지원을 어디서 찾을 수 있나요?**  
A: 지원 및 토론을 위해 Aspose.Tasks 커뮤니티 포럼을 **[here](https://forum.aspose.com/c/tasks/15)** 에서 확인하십시오.

**Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 테스트 및 평가를 위해 임시 라이선스를 **[here](https://purchase.aspose.com/temporary-license/)** 에서 얻을 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 추가 자료가 있나요?**  
A: 자세한 정보와 예제를 위해 문서를 **[here](https://reference.aspose.com/tasks/java/)** 에서 참고하십시오.

---

**마지막 업데이트:** 2026-02-28  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}