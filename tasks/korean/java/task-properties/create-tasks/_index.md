---
date: 2026-09-25
description: Aspose.Tasks를 사용하여 Java에서 프로젝트 일정을 만드는 방법을 배웁니다. 이 가이드는 summary tasks를
  추가하고, project hierarchy를 관리하며, document directory를 효율적으로 설정하는 방법을 보여줍니다.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Aspose.Tasks에서 작업 생성
og_description: Aspose.Tasks를 사용하여 Java에서 프로젝트 일정을 만드는 방법을 배웁니다. 이 가이드는 summary tasks를
  추가하고, project hierarchy를 관리하며, document directory를 효율적으로 설정하는 방법을 보여줍니다.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Aspose.Tasks for Java를 사용하여 프로젝트 일정 생성 방법
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java를 사용하여 프로젝트 일정 생성 방법
url: /ko/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 프로젝트 일정 만들기

## 소개
이 튜토리얼에서는 Aspose.Tasks를 사용하여 Java 애플리케이션에서 **프로젝트 일정 만들기** 방법을 배웁니다. 간단한 할 일 목록을 만들든 복잡한 엔터프라이즈 수준의 플래너를 만들든, 아래 단계에서는 요약 작업 추가, 프로젝트 계층 구조 관리, 문서 디렉터리 설정 등을 명확하고 실행 가능한 코드 스니펫과 함께 안내합니다. 끝까지 진행하면 추가 조작이나 내보내기에 사용할 수 있는 완전한 구조의 일정이 준비됩니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 관리합니까?** 작업 계층 구조, 리소스, 캘린더 및 프로젝트 파일 형식(MS‑Project, Primavera 등)을 처리합니다.  
- **개발에 라이선스가 필요합니까?** 평가용으로는 무료 임시 라이선스가 작동하며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇입니까?** Java 8 이후 버전을 완전히 지원합니다.  
- **작업에 사용자 정의 필드를 추가할 수 있습니까?** 네, API를 통해 사용자 정의 필드를 사용해 작업을 확장할 수 있습니다.  
- **Gantt 차트에 대한 기본 지원이 있습니까?** Aspose.Tasks는 Gantt 시각화를 포함한 PDF/HTML로 내보낼 수 있습니다.

## Aspose.Tasks에서 프로젝트 일정이란?
프로젝트 일정은 작업, 종속성 및 타임라인의 전체 집합으로, 작업이 어떻게 수행될지를 정의합니다. Aspose.Tasks는 이 정보를 `Project` 객체에 저장하며, 이를 읽고 수정하고 다양한 형식으로 저장할 수 있습니다. 시작 및 종료 날짜, 제약 조건, 리소스 할당을 포함하여 포괄적인 계획 및 보고가 가능합니다.

## Java 프로젝트 관리에 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 **30개 이상의 입력 및 출력 형식**을 지원하며, 전체 파일을 메모리에 로드하지 않고도 **10,000개 이상의 작업**을 처리할 수 있어 대규모 Java 프로젝트 관리 시 높은 성능을 제공합니다.

## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:
- **Java Development Kit (JDK)** – 머신에 JDK 8 이상 설치되어 있어야 합니다.  
- **Aspose.Tasks for Java 라이브러리** – [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하고 설치하십시오.  
- **통합 개발 환경 (IDE)** – Eclipse, IntelliJ IDEA 또는 선호하는 Java 친화적인 IDE를 사용하십시오.

## 패키지 가져오기
`Project`, `Task` 및 관련 클래스는 `com.aspose.tasks` 네임스페이스에 있습니다. Java 파일 상단에 이를 import하십시오:

`Project` 클래스는 전체 프로젝트 일정을 나타내며 작업 및 리소스를 조작하는 메서드를 제공합니다.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` 클래스는 프로젝트 파일에 대한 모든 작업의 진입점입니다.

## Aspose.Tasks로 프로젝트 일정 만들기
새 `Project` 인스턴스를 로드하고, 문서 디렉터리를 설정한 뒤 작업을 추가합니다. 이 직접적인 설명은 핵심 흐름을 설명합니다: `Project`를 생성하고, `RootFolder`(문서 디렉터리)를 구성한 다음 요약 작업을 추가하고 하위 작업을 추가합니다. 모든 변경 사항은 메모리에 유지되며 `save`를 호출해 일정이 파일에 저장됩니다.

### 1단계: 문서 디렉터리 설정
결과 프로젝트 파일이 기록될 위치를 정의합니다. 디렉터리를 미리 설정하면 이후 모든 저장 작업이 일관된 경로를 사용합니다.

`RootFolder` 속성은 프로젝트 파일을 읽거나 쓸 기본 폴더를 지정합니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### 2단계: 새 프로젝트 생성
일정을 보관할 새로운 `Project` 객체를 인스턴스화합니다. 기존 일정을 수정하려면 사전에 존재하는 파일 경로를 선택적으로 전달할 수 있습니다.

`Project` 생성자는 작업 추가를 위한 빈 일정을 생성합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 3단계: 요약 작업 추가
요약 작업은 관련 하위 작업을 그룹화하며 Gantt 차트에서 접을 수 있는 노드로 표시됩니다. `Task` 클래스를 사용하고 `IsSummary`를 `true`로 설정하십시오.

`addTask` 메서드는 지정된 상위 작업 아래에 새 작업을 생성하고 해당 ID를 반환합니다.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### 4단계: 하위 작업 추가
하위 작업은 별도로 지정하지 않는 한 상위 요약 작업의 시작/종료 날짜를 상속합니다. 하위 작업을 추가하려면 `addTask`를 다시 호출하고 상위 ID를 지정하면 됩니다.

상위 ID와 함께 `addTask`를 호출하면 해당 요약 작업 아래에 하위 작업이 추가됩니다.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

프로젝트에 필요한 만큼 작업과 하위 작업을 계속 추가하십시오. 각 단계는 MS‑Project, PDF 또는 기타 지원 형식으로 내보낼 수 있는 구조화된 프로젝트 계층을 구축하는 데 기여합니다.

## 일반적인 문제와 해결책
- **문제:** “Document directory not found.”  
  **해결책:** `RootFolder`에 지정한 경로가 파일 시스템에 존재하고 Java 프로세스에 쓰기 권한이 있는지 확인하십시오.
- **문제:** 하위 작업이 요약 작업 아래에 표시되지 않음.  
  **해결책:** `addTask` 호출 시 올바른 상위 작업 ID를 전달했는지 확인하십시오. API는 두 번째 인수로 상위 ID를 요구합니다.
- **문제:** 대형 프로젝트에서 OutOfMemoryError 발생.  
  **해결책:** Aspose.Tasks는 스트리밍 모드로 작업을 처리하므로 JVM 힙 크기(`-Xmx2g`)를 늘리거나 일정을 여러 파일로 분할하십시오.

## 자주 묻는 질문
**Q: Aspose.Tasks가 소규모 프로젝트에 적합합니까?**  
A: 물론입니다. 이 라이브러리는 단일 작업 목록부터 수천 개 작업이 포함된 엔터프라이즈 수준 일정까지 확장됩니다.

**Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 문서 [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)를 참조하십시오.

**Q: Aspose.Tasks에 대한 임시 라이선스는 어떻게 얻나요?**  
A: 개발 및 테스트에 사용할 수 있는 기간 제한 라이선스를 위해 [temporary license request page](https://purchase.aspose.com/temporary-license/)를 방문하십시오.

**Q: Aspose.Tasks를 사용해 작업 속성을 사용자 정의할 수 있나요?**  
A: 네, 사용자 정의 필드로 작업을 확장하고, 리소스를 할당하며, 캘린더를 프로그래밍 방식으로 수정할 수 있습니다.

**Q: Aspose.Tasks 사용자를 위한 지원 커뮤니티가 있나요?**  
A: 물론입니다! [the support forum](https://forum.aspose.com/c/tasks/15)에서 Aspose.Tasks 커뮤니티에 참여하십시오.

---

**마지막 업데이트:** 2026-09-25  
**테스트 환경:** Aspose.Tasks 24.12 for Java  
**작성자:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks에서 프로젝트에 리소스 추가 및 리소스 할당 만들기](/tasks/java/resource-assignments/create-resource-assignments/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}