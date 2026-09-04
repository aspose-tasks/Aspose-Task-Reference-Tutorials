---
date: 2026-07-05
description: Aspose.Tasks를 사용하여 Java에서 프로젝트 관리 작업 종속성을 만드는 방법을 배웁니다. 코드 스니펫이 포함된 단계별
  가이드를 따라 보세요.
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기
url: /ko/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기

## 소개
프로젝트 관리 작업 종속성은 잘 구성된 일정의 핵심이며, 시작 날짜, 종료 날짜 및 중요 경로를 자동으로 계산할 수 있게 합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 Java에서 **프로젝트 관리 작업 종속성**을 만드는 방법을 배웁니다. Aspose.Tasks는 50개 이상의 파일 형식을 지원하고 전체 파일을 메모리에 로드하지 않고도 수천 개 작업 프로젝트를 처리할 수 있습니다. 아래 단계에 따라 작업을 연결하고, 링크를 확인하며, 솔루션을 실제 애플리케이션에 통합하십시오.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** Aspose.Tasks for Java를 사용하여 작업 링크(종속성)를 생성합니다.  
- **코드 라인은 몇 줄이 필요합니까?** 핵심 연결 로직은 단 두 문장에 들어갑니다.  
- **시도하려면 라이선스가 필요합니까?** 무료 30일 체험판을 사용할 수 있으며, 프로덕션에는 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇입니까?** Java 8부터 17까지 완전히 지원됩니다.  
- **두 개 이상의 작업을 연결할 수 있나요?** 예 — 선행‑후속 쌍의 수에 관계없이 연결 패턴을 반복하면 됩니다.

## 프로젝트 관리 작업 종속성이란?
프로젝트 관리 작업 종속성은 한 작업의 시작 또는 종료가 다른 작업과 어떻게 연결되는지를 정의하며, 작업 수행 순서를 결정합니다. Aspose.Tasks는 이러한 관계를 `TaskLink` 객체로 표현하며, 이를 프로그래밍 방식으로 생성, 수정 또는 삭제할 수 있습니다.

## 작업 연결에 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 **50개 이상의 입력 및 출력 형식**(MPP, XML, CSV 포함)을 지원하며, 일반 서버에서 200 MB 미만의 RAM을 사용하면서 **10,000개 이상의 작업**이 포함된 프로젝트를 처리할 수 있습니다. API를 통해 링크 유형, 지연 시간 및 제약 조건 처리를 세밀하게 제어할 수 있으며 Microsoft Project를 설치할 필요가 없습니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 사전 요구 사항을 확인하십시오:
- Java 개발 환경: 머신에 기능적인 Java 개발 환경을 설정하십시오.  
- Aspose.Tasks 라이브러리: Aspose.Tasks for Java 라이브러리를 다운로드하고 통합하십시오. 사용 가능한 [here](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져오세요. 이는 Aspose.Tasks 기능에 접근하기 위해 중요합니다.

`Project` 클래스는 Aspose.Tasks의 진입점으로, 전체 프로젝트 파일을 메모리에 나타냅니다.  
```text
```java
import com.aspose.tasks.*;
```
```

## Aspose.Tasks for Java를 사용하여 작업 링크를 만드는 방법?
`Project` 인스턴스를 로드하거나 생성하고, 필요한 작업을 추가한 다음 `getTaskLinks().add()`를 호출하여 종속성을 설정합니다. 이 메서드는 선행 작업과 후속 작업을 연결하는 `TaskLink` 객체를 생성하며, 선택적으로 링크 유형 및 지연 시간을 지정할 수 있습니다. 다음 단계에서는 필요한 정확한 코드를 안내합니다—추가 보일러플레이트는 필요 없습니다.

### 단계 1: 문서 디렉터리 설정
Aspose.Tasks가 파일을 올바르게 찾고 처리하도록 문서가 저장된 디렉터리를 정의합니다.

`java.nio.file.Paths` 유틸리티는 플랫폼에 독립적인 파일 경로를 구축하는 데 도움이 됩니다.  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### 단계 2: 프로젝트 및 작업 초기화
새 프로젝트를 생성하고 그 안에 작업을 초기화합니다. 이 예제에서는 "Task 1"과 "Task 2"가 루트 작업에 추가됩니다.

`Task` 클래스는 개별 작업 항목을 나타내며, 각 작업은 고유한 ID, 이름 및 일정을 가질 수 있습니다.  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### 단계 3: 작업 링크 설정
`getTaskLinks()` 메서드를 사용하여 두 작업 사이에 링크를 추가합니다. 이 예제는 "Task 1"을 "Task 2"의 선행 작업으로 연결하는 방법을 보여줍니다.

`TaskLink` 객체는 종속성 유형(Finish‑to‑Start, Start‑to‑Start 등)과 선택적 지연을 정의합니다.  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### 단계 4: 결과 표시
작업 링크 생성 프로세스가 성공적으로 완료되었음을 나타내는 메시지를 출력합니다. 이 단계는 디버깅 및 검증에 중요합니다.

간단한 `System.out.println` 호출로 링크가 오류 없이 추가되었음을 확인할 수 있습니다.  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

보다 복잡한 작업 연결 시나리오에 대해 이 단계를 반복하고, 작업 이름을 사용자 정의하며, 프로젝트 요구 사항에 따라 종속성을 설정하십시오.

자세한 API 정보는 [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/)을 참조하십시오.  
커뮤니티 지원은 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15)에서 확인하십시오.

## 일반적인 문제 및 해결 방법
`save` 메서드는 지정된 파일 경로에 프로젝트를 기록하여 추가된 링크를 포함한 모든 변경 사항을 지속합니다.  
`TaskLinkType` 열거형은 관계 유형을 정의하며, 예를 들어 `FinishToStart`는 종료‑시작 종속성을 나타냅니다.

- **저장된 파일에 링크가 표시되지 않음** – 링크를 추가한 후 `project.save(outputPath)`를 호출했는지 확인하십시오.  
- **잘못된 링크 유형** – `TaskLinkType.FinishToStart`, `StartToStart` 등을 사용하여 일정 논리에 맞게 지정하십시오.  
- **대규모 프로젝트에서 메모리 급증 발생** – 로드하기 전에 `project.setReadOnly(true)`를 활성화하여 스트리밍 모드로 작업하십시오.

## 자주 묻는 질문
**Q: Aspose.Tasks for Java를 다른 Java 프레임워크와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 Spring, Jakarta EE, Android 및 모든 표준 Java 환경과 원활하게 통합됩니다.

**Q: 라이브러리를 구매하기 전에 무료 체험판을 이용할 수 있나요?**  
A: 예, [free trial](https://releases.aspose.com/)을 통해 기능을 살펴보고 결정을 내리기 전에 사용해 보세요.

**Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 테스트 및 평가 목적을 위해 [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 획득하십시오.

**Q: 참고할 수 있는 샘플 프로젝트가 있나요?**  
A: 예, 문서에서 포괄적인 샘플 프로젝트와 코드 스니펫을 확인하십시오.

**Q: Aspose.Tasks for Java를 구매하는 권장 방법은 무엇인가요?**  
A: [purchase page](https://purchase.aspose.com/buy)를 방문하여 복사본을 확보하고 라이선스 옵션을 살펴보십시오.

---

**마지막 업데이트:** 2026-07-05  
**테스트 환경:** Aspose.Tasks 24.12 for Java  
**작성자:** Aspose

## 관련 튜토리얼

- [작업 생성 Aspose Java – 작업 속성](/tasks/java/task-properties/)
- [프로젝트 관리 기준선 – Aspose.Tasks를 사용한 작업 일정](/tasks/java/task-baselines/baseline-task-scheduling/)
- [리소스 생성 방법 – Aspose.Tasks for Java를 사용한 리소스 관리](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}