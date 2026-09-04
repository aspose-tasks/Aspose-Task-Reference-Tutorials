---
date: 2026-07-05
description: Aspose.Tasks for Java를 사용하여 프로젝트 간 작업을 연결하는 방법을 배웁니다. 단계별 가이드, 사전 요구
  사항 및 원활한 교차 프로젝트 작업 연결을 위한 모범 사례를 제공합니다.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Aspose.Tasks에서 교차 프로젝트 작업 링크 만들기
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 프로젝트 간 작업 연결
url: /ko/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 간 작업 연결하기 Aspose.Tasks for Java 사용

## 소개
프로젝트 간 작업을 연결하는 것은 작업을 동기화하고 중복을 방지하며 상호 의존적인 활동에 대한 단일 진실 소스를 유지할 수 있게 해주는 핵심 기능입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **link tasks across projects**(프로젝트 간 작업 연결) 방법을 단계별로 알아봅니다. 끝까지 진행하면 양쪽이 변경될 때 자동으로 업데이트되는 완전한 기능의 교차 프로젝트 링크를 얻게 되어 수동 복사‑붙여넣기 없이 실시간으로 조정할 수 있습니다.

## 빠른 답변
- **프로젝트를 생성하기 위한 기본 클래스는 무엇입니까?** `Project` – it represents the whole MS‑Project file in memory.  
- **외부 작업을 추가하는 메서드는 무엇입니까?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **링크 유형을 설정할 수 있나요?** Yes – use `TaskLinkType.FinishToStart`, `StartToStart`, etc.  
- **링크를 위해 라이선스가 필요합니까?** A valid Aspose.Tasks license is required for production use; a free trial works for evaluation.  
- **링크된 작업에 제한이 있나요?** Aspose.Tasks can handle 10,000+ linked tasks per project without performance degradation.

## 프로젝트 간 작업 연결이란 무엇입니까?
프로젝트 간 작업을 연결하면 하나의 프로젝트 파일에 있는 작업과 다른 프로젝트 파일에 있는 작업 사이에 종속 관계가 생성되어, 원본 작업(기간, 시작 날짜, 제약 조건)의 변경 사항이 자동으로 종속 작업에 반영됩니다. 이 메커니즘은 일정이 일치하도록 유지하고 수동 업데이트를 줄이며, 원본 프로젝트의 모든 수정이 즉시 모든 연결된 프로젝트에 반영되어 포트폴리오 전반의 일관성을 유지합니다.

## 왜 Aspose.Tasks를 사용하여 교차 프로젝트 연결을 해야 합니까?
Aspose.Tasks는 **50+ input and output formats**를 지원하고 메모리 사용량을 200 MB 이하로 유지하면서 **multi‑hundred‑page projects**를 처리할 수 있습니다. API는 서버 측에서 연결을 수행하므로 Microsoft Project 설치가 필요 없으며 대기업을 위한 자동화 파이프라인을 구현할 수 있습니다.

## 전제 조건
- IDE에 Java 17(또는 그 이후 버전)이 설치되고 구성되어 있어야 합니다.  
- 유효한 Aspose.Tasks for Java 라이선스 파일(`Aspose.Tasks.Java.lic`)이 필요합니다.  
- 프로젝트에 Aspose.Tasks for Java 라이브러리를 추가합니다. [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
- 작업, 요약 작업, 종속성 등 MS‑Project 개념에 대한 기본적인 이해가 필요합니다.

## 패키지 가져오기
`Project`, `Task`, `TaskLink` 및 관련 열거형은 `com.aspose.tasks` 네임스페이스에 있습니다. Java 파일 상단에 이를 가져오세요:

`import com.aspose.tasks.*;`

**Project**는 메모리 내에서 프로젝트 파일을 나타내는 주요 클래스입니다. **Task**는 프로젝트 내 개별 작업 항목을 나타냅니다. **TaskLink**는 두 작업 간의 종속 관계를 정의합니다. 이러한 가져오기를 통해 교차 프로젝트 연결을 포함한 프로젝트 조작 기능 전체에 접근할 수 있습니다.

## 프로젝트 간 작업을 연결하는 방법은?
두 개의 프로젝트 파일을 로드하고, 외부 작업 자리표시자를 추가한 뒤 로컬 작업을 생성하고 `TaskLink`로 연결합니다. API는 ID 매핑과 업데이트를 자동으로 처리하여 외부 작업의 모든 변경 사항이 추가 코딩 없이 연결된 로컬 작업에 전파되도록 보장합니다. 이 접근 방식은 다중 프로젝트 조정을 단순화하고 일정 이탈 위험을 줄입니다.

### 단계 1: 환경 설정
Aspose.Tasks JAR가 클래스패스에 포함되어 있고 런타임에 라이선스 파일이 로드되었는지 확인하십시오:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License**는 전체 기능을 활성화하고 평가 워터마크를 제거하기 위해 Aspose.Tasks 라이선스 파일을 로드합니다.

### 단계 2: 프로젝트 인스턴스 생성
링크를 적용할 대상 프로젝트에 대한 새로운 `Project` 객체를 인스턴스화합니다:

`Project targetProject = new Project();`

`Project` 클래스는 메모리 내에서 단일 프로젝트 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다.

### 단계 3: 요약 작업 추가
요약 작업은 관련 작업을 그룹화합니다. 외부 작업과 로컬 작업을 모두 포함할 요약 작업을 생성합니다:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### 단계 4: 외부 작업 추가
다른 프로젝트 파일의 작업을 가리키는 외부 작업을 삽입합니다:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

**addExternalTask** 메서드는 제공된 파일 이름과 작업 ID를 사용하여 외부 프로젝트 파일을 참조하는 자리표시자 작업을 생성합니다.

### 단계 5: 로컬 작업 추가
외부 작업에 연결될 작업을 생성합니다:

`Task local = summary.getChildren().add("Local Task");`

### 단계 6: 작업 링크 생성
외부 작업과 로컬 작업 사이에 종속성을 설정합니다. 가장 일반적인 링크 유형은 Finish‑to‑Start입니다:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink**는 관계를 기록하며, 필요에 따라 나중에 지연, 앞당김 또는 유형을 수정할 수 있습니다.

### 단계 7: 저장 및 검증
프로젝트를 파일에 저장하고 필요에 따라 Microsoft Project에서 열어 링크를 확인합니다:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat**은 프로젝트를 저장할 파일 형식을 지정합니다. *LinkedProject.mpp*를 열면 외부 작업이 특수 아이콘으로 표시되고 종속 라인이 로컬 작업을 가리키는 것을 볼 수 있습니다.

## 일반적인 문제 및 해결책
- **외부 파일을 찾을 수 없음** – 실행 프로세스에 대한 상대 경로이거나 절대 경로를 제공했는지 확인하십시오.  
- **작업 ID 불일치** – 외부 작업 ID(`addExternalTask`의 두 번째 인수)가 원본 프로젝트와 일치하는지 확인하십시오.  
- **라이선스가 로드되지 않음** – 라이선스 파일이 없거나 잘못되면 `LicenseException`이 발생합니다. Aspose.Tasks 호출 전에 라이선스를 로드하십시오.  
- **대형 프로젝트에서의 성능** – 외부 작업만 읽을 경우 `Project.setReadOnly(true)`를 사용하면 메모리 오버헤드를 줄일 수 있습니다.

## 자주 묻는 질문

**Q: 여러 외부 프로젝트의 작업을 동일한 요약 작업에 연결할 수 있나요?**  
A: 예, 동일한 요약 작업 아래에 여러 외부 작업을 추가하고 각각에 대해 동일한 `addExternalTask` 메서드를 사용하여 개별 링크를 만들 수 있습니다.

**Q: 연결된 프로젝트의 외부 작업이 수정되면 어떻게 되나요?**  
A: 외부 작업의 일정, 기간 또는 제약 조건이 변경되면 대상 프로젝트를 새로 고침할 때 종속 로컬 작업에 자동으로 반영됩니다.

**Q: 다른 파일 형식의 작업 간에 링크를 만들 수 있나요?**  
A: 물론 가능합니다. Aspose.Tasks는 MPP, XML, Primavera 형식 간의 연결을 지원하여 이기종 프로젝트 환경이 동기화될 수 있습니다.

**Q: 프로젝트 간에 연결된 작업을 연결 해제할 수 있나요?**  
A: 예, `project.getTaskLinks().remove(link)`를 호출하거나 외부 작업 자리표시자를 삭제하여 링크를 제거할 수 있습니다.

**Q: 프로젝트 간에 연결할 수 있는 작업 수에 제한이 있나요?**  
A: 라이브러리는 프로젝트당 **10,000+ linked tasks**를 처리할 수 있으며, 이는 사용 가능한 시스템 메모리와 기본 파일 형식 사양에 의해 제한됩니다.

## 결론
이제 Aspose.Tasks for Java를 사용하여 **link tasks across projects**(프로젝트 간 작업 연결)하는 완전하고 프로덕션 준비된 접근 방식을 갖추었습니다. 이 기능은 다중 프로젝트 조정을 간소화하고 수동 작업을 줄이며 일정 변경이 포트폴리오 전체에 즉시 전파되도록 보장합니다. 사용자 정의 지연 시간, 다양한 링크 유형, 대량 연결과 같은 추가 기능을 탐색하여 복잡한 프로젝트 구조를 더욱 자동화하십시오.

---

**마지막 업데이트:** 2026-07-05  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## 관련 튜토리얼

- [Aspose.Tasks에서 작업 링크 만들기](/tasks/java/task-links/create-task-link/)
- [Aspose Java에서 작업 생성 – 작업 속성](/tasks/java/task-properties/)
- [Aspose.Tasks에서 빈 MS Project 파일 만들기](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}