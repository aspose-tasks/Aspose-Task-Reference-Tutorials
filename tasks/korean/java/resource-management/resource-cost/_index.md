---
date: 2026-06-15
description: Aspose.Tasks for Java를 사용하여 MS Project 파일의 비용을 관리하는 방법을 배우세요. 여기에는 MPP
  파일을 로드하고 실제 비용 작업 및 예산 비용 일정을 읽는 방법이 포함됩니다.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Aspose.Tasks에서 리소스 비용 처리
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 MS Project에서 비용 관리하는 방법
url: /ko/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project에서 Aspose.Tasks for Java를 사용하여 비용 관리하는 방법

## 소개

프로젝트 예산을 관리하는 것은 모든 프로젝트 관리자의 핵심 책임이며, **비용을 효과적으로 관리하는 방법**은 프로젝트 성공을 좌우할 수 있습니다. Aspose.Tasks for Java는 Microsoft Project 파일을 프로그래밍 방식으로 제어할 수 있게 해 주어 .mpp 파일을 수동으로 열지 않고도 리소스 비용 데이터를 읽고 업데이트할 수 있습니다. 이 튜토리얼에서는 MPP 파일을 로드하고, 실제 비용 작업을 검사하며, 각 리소스에 대한 예산 비용 일정을 추출하는 과정을 단계별로 보여줍니다.

## 빠른 답변
- **Aspose.Tasks for Java는 무엇을 하나요?** Microsoft Project 파일(.mpp)을 Microsoft Project를 설치하지 않아도 읽고 쓸 수 있습니다.  
- **MPP 파일을 어떻게 로드하나요?** `new Project("path/to/file.mpp")`를 사용합니다 – API가 파일을 메모리에서 파싱합니다.  
- **어떤 비용 필드가 제공되나요?** 실제 비용 작업(ACWP), 예정된 작업의 예산 비용(BCWS), 수행된 작업의 예산 비용(BCWP).  
- **개발에 라이선스가 필요합니까?** 테스트용 무료 임시 라이선스를 사용할 수 있으며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상, Java 17 LTS 포함.

## MS Project에서 비용을 관리하는 방법?

`new Project("yourFile.mpp")`로 프로젝트를 로드한 다음, 각 `Resource` 객체를 반복하면서 ACWP, BCWS, BCWP와 같은 비용 관련 속성을 읽습니다. Aspose.Tasks는 내부 비용 값을 프로젝트의 통화로 자동 변환하므로 바로 표시하거나 저장할 수 있습니다. 이 접근 방식은 수동 스프레드시트 계산을 없애고 모든 프로젝트 보고서에서 데이터 일관성을 보장합니다.

## 전제 조건

1. Java 프로그래밍에 대한 기본 이해.  
2. 프로젝트에 Aspose.Tasks for Java 라이브러리 추가(Maven/Gradle 또는 수동 JAR).  
3. 분석하려는 Microsoft Project 파일(`.mpp`)에 대한 접근 권한.  

## 패키지 가져오기

`Project`와 `Resource` 클래스는 프로젝트 데이터를 작업하기 위한 진입점입니다.

`Project` 클래스는 메모리 내에서 단일 Microsoft Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## 단계 1: 데이터 디렉터리 정의

먼저 `.mpp` 파일이 포함된 폴더를 지정합니다. 이 경로는 절대 경로나 애플리케이션 작업 디렉터리에 대한 상대 경로일 수 있습니다.

```text
```java
String dataDir = "Your Data Directory";
```
```

## 단계 2: MS Project 파일 로드

`Project`는 파일을 로드하고 쿼리할 수 있는 객체 모델을 구축합니다. API는 Microsoft Project를 설치하지 않아도 파일을 파싱하며, 30개 이상의 입력 형식을 지원합니다.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## 단계 3: 리소스 반복

`Resource` 객체는 예산을 소비하는 사람, 장비 또는 자재를 나타냅니다. `project.getResources()` 컬렉션을 순회하여 각 리소스에 접근할 수 있습니다.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## 단계 4: 리소스 이름 및 비용 확인

각 리소스에 대해 이름이 정의되어 있는지 확인한 후 비용 필드를 읽습니다. `getActualCost()` 메서드는 **실제 비용 작업**(ACWP)을 반환하고, `getBudgetedCost()`는 **예산 비용 일정**(BCWS/BCWP)을 제공합니다.

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## 왜 Aspose.Tasks for Java를 사용하여 MPP 파일을 로드합니까?

Aspose.Tasks는 **30개 이상의 파일 형식**(`.mpp`, `.xml`, `.xlsx` 등)을 지원하며 **10,000개 작업**까지 처리하면서 메모리 사용량이 200 MB 미만입니다. 라이선스가 있는 Microsoft Project 복사본이 필요 없이 서버 측에서 모든 계산을 수행합니다.

## 일반적인 문제 및 해결책

- **Null 리소스 이름:** 일부 레거시 파일에는 자리표시자 리소스가 포함될 수 있습니다. 비용 속성에 접근하기 전에 항상 `resource.getName() != null`을 확인하세요.  
- **대용량 파일로 인한 메모리 압박:** `LoadOptions`는 로드할 프로젝트 데이터를 지정할 수 있는 구성 클래스입니다. `project.setLoadOptions(LoadOptions.setLoadResourceData(false))`를 사용하여 필요한 데이터만 로드하고, 필요 시 나중에 활성화하세요.  
- **통화 불일치:** API는 프로젝트의 통화 설정을 따르며, 필요하면 `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)`로 재정의할 수 있습니다. `CostRateTableType`은 작업에 적용할 수 있는 다양한 비용 요율 테이블을 열거합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java는 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, 중첩된 요약 작업, 다중 리소스 캘린더 및 모든 지원되는 Project 버전의 사용자 정의 필드를 완벽히 지원합니다.

**Q: 라이브러리가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. Aspose.Tasks는 Microsoft Project 2000부터 최신 2023 형식까지 파일을 읽고 씁니다.

**Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 통합할 수 있나요?**  
A: 예, API는 표준 Java 객체를 반환하므로 로깅 프레임워크, ORM 도구 또는 보고서 라이브러리와 원활하게 통합할 수 있습니다.

**Q: Aspose.Tasks for Java는 고객 지원을 제공하나요?**  
A: Aspose는 전용 포럼 지원, 상세 문서 및 라이선스 사용자에게 신속한 이메일 지원을 제공합니다.

**Q: Aspose.Tasks for Java의 무료 체험판이 있나요?**  
A: Aspose 웹사이트에서 30일 평가 라이선스를 다운로드하여 모든 기능을 비용 없이 체험할 수 있습니다.

---

**마지막 업데이트:** 2026-06-15  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [How to Calculate Cost Variance and Manage Assignment Costs with Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Budget, Work, and Cost Management for Tasks in Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Add resource to project with Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}