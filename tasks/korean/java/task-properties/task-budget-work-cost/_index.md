---
title: Aspose.Tasks의 작업에 대한 예산, 작업 및 비용 관리
linktitle: Aspose.Tasks의 작업에 대한 예산, 작업 및 비용 관리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java 프로젝트에서 효율적인 예산 및 비용 관리를 활용하세요. 원활한 통합을 위한 단계별 지침을 살펴보세요.
weight: 31
url: /ko/java/task-properties/task-budget-work-cost/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 작업에 대한 예산, 작업 및 비용 관리

## 소개
성공적인 프로젝트 실행을 위해서는 예산, 업무, 비용을 효율적으로 관리하는 것이 중요합니다. Aspose.Tasks for Java는 예산 책정 및 비용 관리를 포함한 프로젝트 관련 작업을 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 활용하여 프로젝트에서 효과적인 예산, 작업 및 비용 관리를 달성하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 자세히 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 개발 환경: 시스템에 Java 개발 환경이 설정되어 있는지 확인하십시오.
-  Aspose.Tasks for Java 라이브러리: Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져오는 것부터 시작하세요. 이렇게 하면 Aspose.Tasks 기능에 액세스할 수 있습니다. Java 파일 시작 부분에 다음 줄을 포함합니다.
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
## 1. 문서 디렉토리 설정
문서 디렉토리의 경로를 설정하여 시작하십시오. 여기에 프로젝트 파일이 저장됩니다. 다음 코드 조각을 사용하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2. 프로젝트 로드
Aspose.Tasks 라이브러리를 사용하여 프로젝트 파일을 로드합니다. "BudgetWorkAndCost.mpp"를 프로젝트 파일 이름으로 바꿉니다.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```
## 3. 프로젝트 및 자원 예산 검색
다음 코드를 사용하여 프로젝트 및 자원 예산을 가져오고 표시합니다.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```
## 4. 할당 예산 표시
프로젝트 할당을 반복하고 예산 정보를 표시합니다.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```
Aspose.Tasks for Java 프로젝트에 예산, 작업 및 비용 관리 기능을 통합하려면 필요에 따라 이러한 단계를 반복하세요.
## 결론
예산, 작업, 비용을 효과적으로 관리하는 것은 프로젝트 성공의 핵심입니다. Aspose.Tasks for Java는 이 프로세스를 단순화하여 프로젝트 관리 요구 사항에 맞는 포괄적인 솔루션을 제공합니다. 이 단계별 가이드를 따르면 예산 및 비용 관리를 Java 프로젝트에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### 다른 Java 프레임워크와 함께 Java용 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks for Java는 다양한 Java 프레임워크와 호환되어 통합의 유연성을 보장합니다.
### Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 예, Aspose.Tasks for Java의 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Tasks에 대한 추가 지원은 어디서 찾을 수 있나요?
 Aspose.Tasks 커뮤니티 포럼 살펴보기[여기](https://forum.aspose.com/c/tasks/15) 지원과 토론을 위해.
### Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로.
### Aspose.Tasks for Java에 대한 추가 리소스가 있습니까?
 문서를 참조하세요[여기](https://reference.aspose.com/tasks/java/) 자세한 정보와 예시를 확인하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
