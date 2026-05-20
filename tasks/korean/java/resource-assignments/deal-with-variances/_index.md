---
date: 2026-05-20
description: Aspose.Tasks for Java를 사용하여 프로젝트 변동을 처리하는 방법을 배우고, 비용 변동, 작업 변동 및 날짜
  변동을 효율적으로 얻는 방법을 포함합니다.
keywords:
- handle project variances
- get cost variance
- Aspose.Tasks Java
linktitle: Aspense.Tasks에서 변동 처리
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  headline: How to Handle Project Variances with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  name: How to Handle Project Variances with Aspose.Tasks for Java
  steps:
  - name: Iterate through Resource Assignments
    text: 'To deal with variances, we need to iterate through resource assignments
      in the project. This is achieved using a simple loop:'
  - name: Retrieve Work Variance
    text: 'Work variance represents the deviation between planned work and actual
      work performed by a resource. To retrieve work variance for each resource assignment,
      use the following code snippet:'
  - name: Retrieve Start Variance
    text: 'Start variance signifies the variance between planned and actual start
      dates for a task. To fetch start variance, utilize the following code:'
  - name: Retrieve Finish Variance
    text: 'Finish variance denotes the difference between planned and actual finish
      dates for a task. To acquire finish variance, employ the following code:'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with libraries such as Jackson
      for JSON, Apache POI for Excel, and JFreeChart for reporting.
    question: Can I integrate Aspose.Tasks with other Java libraries?
  - answer: Absolutely. It efficiently processes projects containing up to 10,000
      tasks and 5,000 resources without loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Certainly. Use the variance values you retrieve to feed custom PDF, Excel,
      or HTML reports via Aspose.Words, Aspose.Cells, or standard Java templating
      engines.
    question: Can I customize reports based on variance analysis?
  - answer: Yes, users can access technical support through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Is technical support available for Aspose.Tasks users?
  - answer: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/)
      to evaluate its features before making a purchase.
    question: Can I try Aspose.Tasks before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용한 프로젝트 변동 처리 방법
url: /ko/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용한 프로젝트 변동 처리 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **프로젝트 변동을 처리하는 방법**을 배웁니다. 변동은 계획된 작업, 비용, 시작 또는 종료 날짜와 실제 값 사이의 차이로, 프로젝트가 정상 궤도에 있는지를 알려주는 중요한 신호입니다. Aspose.Tasks는 이러한 수치를 프로그램matically(프로그래밍 방식)으로 쉽게 가져오고 분석할 수 있는 방법을 제공하여 데이터 기반의 빠른 조정을 가능하게 합니다.

## 빠른 답변
- **변동에 접근하기 위한 주요 클래스는 무엇인가요?** `ResourceAssignment`는 `WorkVariance`, `CostVariance`, `StartVariance`, `FinishVariance`와 같은 속성을 제공합니다.  
- **비용 변동을 반환하는 메서드는 무엇인가요?** `ResourceAssignment` 인스턴스에서 `getCostVariance()`를 사용합니다.  
- **이 기능을 사용하려면 라이선스가 필요합니까?** 예, 유효한 Aspose.Tasks 라이선스를 통해 모든 변동 API를 사용할 수 있습니다.  
- **대규모 프로젝트도 처리할 수 있나요?** Aspose.Tasks는 전체 파일을 메모리에 로드하지 않고도 최대 10,000개의 작업을 가진 프로젝트를 처리합니다.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상을 지원합니다.

## “프로젝트 변동 처리”란 무엇인가요?
프로젝트 변동을 처리한다는 것은 작업, 비용, 시작 날짜 및 종료 날짜에 대한 기준선(계획) 값과 실제 결과 사이의 차이를 추출하는 것을 의미합니다. 이러한 차이를 분석함으로써 프로젝트 관리자는 성과를 평가하고, 일정이나 예산 초과를 식별하며, 재계획이나 자원 조정을 위한 정보에 입각한 결정을 내려 프로젝트가 정상 궤도를 유지하도록 할 수 있습니다.

## 변동 분석에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks는 **30개 이상의 입출력 파일 형식**을 지원하며 일반 서버 하드웨어에서 수백 페이지 규모의 일정도 1초 이하로 처리할 수 있습니다. API가 변동 값을 직접 반환하므로 수동 계산이나 타사 애드인 사용이 필요하지 않습니다.

## 사전 요구 사항
진행하기 전에 다음 사전 요구 사항을 확인하십시오:
1. 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java 라이브러리를 다운로드하여 프로젝트에 추가합니다. 라이브러리는 [여기](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
3. Java 프로그래밍 언어에 대한 기본 지식.

## 패키지 가져오기
`ResourceAssignment` 클래스는 `com.aspose.tasks` 네임스페이스에 있습니다. 코딩을 시작하기 전에 필요한 패키지를 가져오세요:
`ResourceAssignment` 클래스는 리소스와 작업 간의 연결을 나타내며, 조회할 수 있는 변동 속성을 제공합니다.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```

## Aspose.Tasks에서 프로젝트 변동을 처리하는 방법
`new Project("yourfile.mpp")`를 사용하여 프로젝트를 로드한 뒤, 각 `ResourceAssignment`를 반복하여 변동 필드를 읽습니다. 이 한 번의 순회로 모든 할당에 대한 작업, 비용, 시작 및 종료 변동을 얻을 수 있어 즉시 성과 대시보드를 만들 수 있습니다.

### 단계 1: Resource Assignment 반복
변동을 처리하려면 프로젝트 내의 리소스 할당을 반복해야 합니다. 이는 간단한 루프를 사용하여 구현합니다:

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

### 단계 2: 작업 변동 가져오기
작업 변동은 계획된 작업과 리소스가 실제 수행한 작업 사이의 차이를 나타냅니다. 각 리소스 할당에 대한 작업 변동을 가져오려면 다음 코드 조각을 사용하십시오:

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

### 리소스 할당에 대한 비용 변동을 가져오는 방법
특정 할당에 대한 비용 변동을 얻으려면 `ResourceAssignment` 인스턴스에서 `getCostVariance()` 메서드를 호출합니다. 이 메서드는 기준선 비용과 실제 발생 비용 사이의 금전적 차이를 계산하여 프로젝트 기본 통화 기준의 변동을 나타내는 `double` 값을 반환합니다. 이 값을 예산 분석에 활용할 수 있습니다.

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

### 단계 4: 시작 변동 가져오기
시작 변동은 작업의 계획 시작 날짜와 실제 시작 날짜 사이의 차이를 의미합니다. 시작 변동을 가져오려면 다음 코드를 사용하십시오:

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

### 단계 5: 종료 변동 가져오기
종료 변동은 작업의 계획 종료 날짜와 실제 종료 날짜 사이의 차이를 나타냅니다. 종료 변동을 얻으려면 다음 코드를 사용하십시오:

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## 일반적인 문제와 해결책
- **Null 값:** 작업에 기준선이 없으면 변동 속성이 `null`을 반환합니다. 값을 사용하기 전에 항상 `null`인지 확인하십시오.  
- **시간대 불일치:** 날짜는 UTC로 저장됩니다; 사용자에게 표시할 경우 로컬 시간대로 변환하십시오.  
- **대용량 파일:** 수천 개의 할당이 있는 프로젝트의 경우 메모리 사용량을 낮추기 위해 배치 처리하는 것을 고려하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 Java 라이브러리와 통합할 수 있나요?**  
A: 예, Aspose.Tasks는 JSON을 위한 Jackson, Excel을 위한 Apache POI, 보고서를 위한 JFreeChart와 같은 라이브러리와 원활하게 통합됩니다.

**Q: Aspose.Tasks가 대규모 프로젝트에 적합한가요?**  
A: 물론입니다. 전체 파일을 메모리에 로드하지 않고도 최대 10,000개의 작업과 5,000개의 리소스를 포함하는 프로젝트를 효율적으로 처리합니다.

**Q: 변동 분석을 기반으로 보고서를 맞춤화할 수 있나요?**  
A: 네. 가져온 변동 값을 사용하여 Aspose.Words, Aspose.Cells 또는 표준 Java 템플릿 엔진을 통해 맞춤 PDF, Excel, HTML 보고서를 생성할 수 있습니다.

**Q: Aspose.Tasks 사용자를 위한 기술 지원이 제공되나요?**  
A: 예, 사용자는 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 기술 지원을 받을 수 있습니다.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험판을 받아 기능을 평가한 후 구매할 수 있습니다.

---

**마지막 업데이트:** 2026-05-20  
**테스트 환경:** Aspose.Tasks 24.12 for Java  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks를 사용한 프로젝트 비용 모니터링 - 초과 근무 및 작업](/tasks/java/resource-assignments/overtime-remaining-costs-work/)
- [Aspose.Tasks for Java로 MS Project 리소스 비용 관리](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}