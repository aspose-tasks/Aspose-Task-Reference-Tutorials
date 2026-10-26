---
date: 2026-10-26
description: Aspose.Tasks for Java를 사용하여 그룹 정의 데이터를 읽는 방법. Microsoft Project 파일에서
  작업 그룹화, 기준 및 서식을 추출하여 보고서 작성 및 마이그레이션을 자동화합니다.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Aspose.Tasks에서 그룹 정의 데이터 읽기
og_description: Aspose.Tasks for Java를 사용하여 그룹 정의 데이터를 읽는 방법. Microsoft Project 파일에서
  작업 그룹화, 기준 및 서식을 추출하여 보고서 작성 및 마이그레이션을 자동화합니다.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Aspose.Tasks for Java를 사용하여 그룹 정의 데이터 읽는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Aspose.Tasks for Java를 사용하여 그룹 정의 데이터 읽는 방법
url: /ko/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java에서 그룹 정의 데이터 읽기

## 소개
Aspose.Tasks for Java은 프로그래밍 방식으로 Microsoft Project 파일에 접근, 수정 및 분석할 수 있게 해줍니다. 이 튜토리얼에서는 `.mpp` 파일에서 **그룹 정의 읽는 방법** 데이터를 배우고, 각 그룹의 이름, 기준 및 시각적 스타일을 추출한 다음, 해당 정보를 사용해 맞춤 보고서를 생성하거나 설정을 다른 프로젝트로 마이그레이션하는 방법을 배웁니다. 이 기능을 마스터하면 보고서를 자동화하고, 프로젝트 구조를 검증하며, 데이터 기반 워크플로를 효율화할 수 있습니다.

## 빠른 답변
- **“read group definition”이 무엇을 의미하나요?** Microsoft Project가 작업을 조직하는 데 사용하는 그룹화 규칙(이름, 기준, 색상, 글꼴)을 추출하는 것을 의미합니다.  
- **어떤 라이브러리가 필요합니까?** Aspose.Tasks for Java.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 프로덕션에는 상용 라이선스가 필요합니다.  
- **지원되는 IDE는 무엇입니까?** IntelliJ IDEA 또는 Eclipse와 같은 모든 Java IDE.  
- **필요한 코드 양은 얼마나 됩니까?** 프로젝트를 로드하고 그룹 세부 정보를 표시하기 위해 30줄 미만의 Java 코드가 필요합니다.

## 그룹 정의 데이터 읽는 방법
프로젝트를 로드하고, 그룹을 열거하며, 각 그룹의 기준을 검사합니다. 직접적인 답변은: **`Project` 인스턴스를 생성하고, `project.getTaskGroups()`를 호출한 뒤, 컬렉션을 반복하여 이름, 기준, 글꼴 및 색상을 읽는 것입니다.** 다음 섹션에서는 이 과정을 명확한 단계로 나누고, 각 단계마다 Aspose.Tasks 문서에서 실제 스니펫으로 교체해야 하는 짧은 코드 자리표시자를 제공합니다.

## 그룹 정의 읽기란 무엇인가요?
그룹 정의 읽기는 Microsoft Project가 작업을 정렬하기 위해 적용하는 그룹화 규칙(이름, 기준, 서식)을 추출하는 것을 의미합니다. 이러한 규칙은 상태, 우선순위 또는 사용자 정의 필드별로 작업을 클러스터링하는 방법을 애플리케이션에 알려주며, 글꼴 스타일 및 셀 색상과 같은 시각적 속성을 포함합니다.

## 왜 그룹 정의 데이터를 읽어야 할까요?
그룹 정의 데이터를 읽으면 **보고서 생성 자동화**, **그룹화 로직 마이그레이션**을 다른 프로젝트에 적용하고, **필요한 그룹이 존재하는지 검증**을 대량 업데이트 전에 수행할 수 있습니다. Aspose.Tasks for Java은 전체 파일을 메모리에 로드하지 않고도 **10,000개 이상의 작업**을 처리할 수 있어 고성능 배치 작업이 가능합니다. 또한 글꼴 색상, 패턴 및 정렬 방향을 추출해 맞춤 대시보드에서 정확한 시각 레이아웃을 재현할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

1. **Java Development Kit (JDK) 8+** – 최신 버전이면 모두 작동합니다.  
2. **Aspose.Tasks for Java** – 최신 JAR를 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **Java IDE** – IntelliJ IDEA, Eclipse 또는 원하는 편집기를 사용하십시오.  

> **팁:** Maven 또는 Gradle을 사용해 Aspose.Tasks 의존성을 관리하면 수동으로 JAR를 다루는 번거로움을 피할 수 있습니다.

## 패키지 가져오기
`Project`는 Aspose.Tasks for Java에서 Microsoft Project 파일을 나타내는 기본 클래스입니다.  

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 1단계: 데이터 디렉터리 설정
검사하려는 `.mpp` 파일이 들어 있는 폴더를 정의합니다. `java.nio.file.Paths`를 사용하면 플랫폼에 독립적인 경로 처리를 보장합니다.

```java
String dataDir = "Your Data Directory";
```

### 2단계: 프로젝트 파일 로드
`.mpp` 파일을 가리키는 `Project` 인스턴스를 생성합니다. 생성자는 파일 헤더를 읽고 메모리 내 모델을 구축합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 3단계: 작업 그룹 수 가져오기
프로젝트에 정의된 작업 그룹의 총 수를 출력합니다. 이 간단한 확인을 통해 파일에 실제로 그룹화 정보가 포함되어 있는지 확인할 수 있습니다.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### 4단계: 특정 작업 그룹 정보 가져오기
예시에서 인덱스 1인 특정 그룹을 가져와 이름과 포함된 기준 수를 표시합니다. 각 그룹은 작업을 어떻게 그룹화할지 정의하는 여러 기준을 가질 수 있습니다.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### 5단계: 그룹 기준 정보 가져오기
각 그룹은 하나 이상의 기준을 가질 수 있습니다. 아래 스니펫은 그룹화에 사용된 필드, 그룹화 모드, 셀 색상 및 패턴과 같은 세부 정보를 추출합니다.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### 6단계: 상위 그룹 확인
때때로 기준이 상위 그룹에 속합니다. 이 확인은 계층 구조를 탐색할 때 null‑pointer 문제를 방지하고 관계를 확인합니다.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### 7단계: 기준의 글꼴 정보 가져오기
그룹 기준은 사용자 지정 글꼴 스타일을 가질 수 있습니다. 다음 코드는 글꼴 패밀리, 크기, 스타일 및 정렬 방향을 출력하여 자체 UI에서 정확한 모습을 재현할 수 있게 합니다.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## 일반적인 문제 및 해결책

| 문제 | 발생 원인 | 해결 방법 |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | 해당 기준에 상위 그룹이 없을 수 있습니다. | 상위 그룹에 접근하기 전에 null 검사를 추가하십시오. |
| **File not found** | `dataDir` 경로가 올바르지 않거나 파일 이름이 잘못되었습니다. | `Paths.get(dataDir, "project.mpp").toAbsolutePath()`를 사용하고 파일이 존재하는지 확인하십시오. |
| **License not set** | Aspose가 평가 모드로 실행되어 출력이 잘릴 수 있습니다. | 프로젝트를 로드하기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`를 사용해 라이선스를 등록하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용해 프로젝트 파일을 수정할 수 있나요?**  
A: 네, 이 라이브러리는 Microsoft Project 형식에 대한 완전한 읽기/쓰기 기능을 제공하므로 작업을 추가하고, 리소스를 변경하며, 그룹 정의를 프로그래밍 방식으로 업데이트할 수 있습니다.

**Q: Aspose.Tasks for Java는 모든 버전의 Microsoft Project 파일과 호환되나요?**  
A: MPP, XML, CSV 및 기타 일반적인 Project 형식을 지원하며, Project 2000부터 최신 2024 릴리스까지의 버전을 지원합니다.

**Q: Aspose.Tasks for Java를 사용할 때 오류를 어떻게 처리해야 하나요?**  
A: 파일 작업을 `try‑catch` 블록으로 감싸고 상세 오류 정보를 위해 `TasksException`을 잡으세요; 예외의 `getMessage()`를 확인하면 힌트를 얻을 수 있습니다.

**Q: Aspose.Tasks for Java가 다른 형식으로 내보내기를 제공하나요?**  
A: 물론입니다 – 라이브러리의 전용 내보내기 API를 사용해 PDF, XLSX, HTML 등으로 내보낼 수 있습니다.

**Q: 추가 리소스와 지원은 어디서 찾을 수 있나요?**  
A: API 레퍼런스를 위해 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)을 방문하고, 커뮤니티 지원을 위해 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)을 확인하십시오.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 Microsoft Project 파일에서 **그룹 정의 데이터 읽는 방법**을 단계별로 살펴보았습니다. `Project`를 로드하고 `TaskGroupCollection`을 열거하며 각 그룹의 기준, 글꼴 및 색상을 검사함으로써 자동 보고 파이프라인을 구축하고, 그룹화 규칙을 마이그레이션하거나 프로젝트 구조를 자신 있게 검증할 수 있습니다. 동일한 접근 방식은 수천 개의 작업을 포함한 대규모 프로젝트에도 메모리 사용량을 낮게 유지하면서 확장됩니다.

---

**마지막 업데이트:** 2026-10-26  
**테스트 대상:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용해 Microsoft Project에서 프로젝트 정보 읽는 방법](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks에서 테이블 필드 가져오기 및 테이블 데이터 읽는 방법](/tasks/java/project-data-reading/read-table-data/)
- [read gantt chart java – 특정 간트 데이터 추출](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}