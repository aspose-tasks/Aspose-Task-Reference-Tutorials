---
date: 2026-09-30
description: 강력한 Java 프로젝트 관리 라이브러리인 Aspose.Tasks를 사용하여 Java로 MPP 프로젝트의 진행률을 설정하는
  방법을 배웁니다. 단계별 가이드를 따라 보세요.
keywords:
- how to set progress
- java project management library
- Aspose.Tasks Java
- MPP project Java
lastmod: 2026-09-30
linktitle: Aspose.Tasks에서 작업 진행률 변경
og_description: 선도적인 Java 프로젝트 관리 라이브러리 Aspose.Tasks를 사용하여 Java로 MPP 프로젝트의 진행률을 설정하는
  방법을 알아보세요. 전체 코드 없이 가이드를 확인하세요.
og_image_alt: Guide showing how to set task progress in an MPP file using Aspose.Tasks
  for Java
og_title: Java와 Aspose.Tasks를 사용하여 MPP 프로젝트에서 진행률 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  headline: How to set progress in an MPP project using Java and Aspose.Tasks
  type: TechArticle
- description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  name: How to set progress in an MPP project using Java and Aspose.Tasks
  steps:
  - name: Set up your Java project
    text: Create a new Maven or Gradle project and add the Aspose.Tasks JAR to your
      classpath. This gives you access to the `Project`, `Task`, and related classes.
  - name: Define the document directory
    text: Specify where the project file will be stored. Replace the placeholder with
      the actual path on your machine. `dataDir` is a string that specifies the folder
      path where the MPP file will be saved.
  - name: Create a new project (create mpp project java)
    text: '`Project` represents an in‑memory Microsoft Project file that can be saved
      to .mpp format.'
  - name: Add a task to the project (add task project)
    text: '`Task` is an object representing a single work item within a Project.'
  - name: Set the task’s progress
    text: '`Tsk.PERCENT_COMPLETE` is the field that stores a task’s completion percentage.'
  - name: Display the updated progress
    text: Reading `Tsk.PERCENT_COMPLETE` returns the current progress value for the
      task. By following these steps you have successfully **created an MPP project
      in Java**, added a task, and **changed its progress** – all using Aspose.Tasks.
  type: HowTo
- questions:
  - answer: Any recent version (2023‑2025) supports `Project` creation; using the
      latest release ensures you have all bug fixes and performance improvements.
    question: What version of Aspose.Tasks is required to create an MPP file?
  - answer: Yes, call `project.save("output.pdf", SaveFileFormat.PDF);` after setting
      the progress to generate a visual report.
    question: Can I export the project to PDF after updating progress?
  - answer: Loop through `project.getRootTask().getChildren()` and set `Tsk.PERCENT_COMPLETE`
      for each task; the API updates each task efficiently.
    question: Is it possible to batch‑update progress for many tasks?
  - answer: Resources must be added explicitly; task progress does not affect resource
      allocation unless you modify resource‑related fields.
    question: Does the library handle resource assignments automatically?
  - answer: Use `project.setPassword("yourPassword");` before calling `project.save(...)`
      to encrypt the file.
    question: How do I protect the generated MPP file with a password?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task progress
title: Java와 Aspose.Tasks를 사용하여 MPP 프로젝트에서 진행률 설정하는 방법
url: /ko/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java와 Aspose.Tasks를 사용하여 MPP 프로젝트에서 진행률 설정하는 방법

## 소개
현대 **Java 프로젝트 관리**에서는 **Java로 MPP 프로젝트 생성** 파일을 만들고 작업 진행률을 최신 상태로 유지하는 것이 제시간에 전달하기 위해 필수적입니다. 이 튜토리얼에서는 강력한 **Java 프로젝트 관리 라이브러리**인 Aspose.Tasks를 사용하여 작업의 **진행률 설정 방법**을 프로그래밍 방식으로 보여줍니다. Windows, Linux, macOS에서 작동합니다. 프로젝트 생성부터 업데이트된 완료 비율을 확인하는 전체 흐름을 대화식 단계별 스타일로 설명합니다.

## 빠른 답변
- **“create mpp project java”는 무엇을 의미합니까?**  
  이는 Java 코드를 사용하여 Microsoft Project (.mpp) 파일을 프로그래밍 방식으로 생성하는 것을 의미합니다.
- **어떤 라이브러리가 이를 도와줍니까?**  
  Aspose.Tasks for Java, a dedicated **Java 프로젝트 관리 라이브러리**.
- **작업 진행률을 설정하는 데 필요한 코드 라인은 몇 줄입니까?**  
  프로젝트가 인스턴스화된 후 10줄 미만입니다.
- **프로덕션 사용을 위해 라이선스가 필요합니까?**  
  예, 상업용 라이선스가 필요합니다; 무료 체험판을 사용할 수 있습니다.
- **이 코드를 모든 Java IDE에서 실행할 수 있나요?**  
  물론입니다 – Java 8+을 지원하는 모든 IDE에서 작동합니다.

## “create mpp project java”란 무엇입니까?
Java에서 MPP 프로젝트를 생성한다는 것은 코드를 사용하여 Microsoft Project 파일(`.mpp`)을 생성하는 것을 의미하며, 이는 Microsoft Project 또는 호환 가능한 뷰어에서 열 수 있습니다. 이를 통해 일정 자동 생성, 대량 작업 생성 및 엔터프라이즈 시스템과의 원활한 통합이 가능해집니다.

## 왜 Aspose.Tasks를 Java 프로젝트 관리 라이브러리로 사용합니까?
Aspose.Tasks는 프로젝트 생성, 작업 조작 및 보고를 위한 **전체 API 커버리지**를 제공합니다. **30개 이상의 입력 및 출력 형식**을 지원하며 전체 파일을 메모리에 로드하지 않고도 **최대 10,000개의 작업**을 처리할 수 있어 저사양 하드웨어에서도 고성능 처리를 제공합니다.

## 사전 요구 사항
1. **Java Development Environment** – JDK 8 이상이 설치되고 구성된 환경.  
2. **Aspose.Tasks for Java Library** – 공식 사이트에서 다운로드: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Document Directory** – 생성된 `.mpp` 파일이 저장될 머신상의 폴더.

## 패키지 가져오기
먼저, 필요한 Aspose.Tasks 클래스를 가져옵니다. 이 스니펫은 환경을 설정하며, 이후 50 % 진행률을 가진 작업을 추가합니다.

`com.aspose.tasks.*`는 **Project**, **Task**, **Tsk**와 같은 핵심 클래스를 제공하여 MPP 파일 작업에 사용됩니다.

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 1단계: Java 프로젝트 설정
새 Maven 또는 Gradle 프로젝트를 생성하고 Aspose.Tasks JAR를 클래스패스에 추가합니다. 이를 통해 `Project`, `Task` 및 관련 클래스를 사용할 수 있습니다.

### 2단계: 문서 디렉터리 정의
프로젝트 파일이 저장될 위치를 지정합니다. 플레이스홀더를 실제 머신의 경로로 교체하세요.

`dataDir`은 MPP 파일이 저장될 폴더 경로를 지정하는 문자열입니다.

```java
String dataDir = "Your Document Directory";
```

### 3단계: 새 프로젝트 생성 (create mpp project java)
`Project`는 메모리 내 Microsoft Project 파일을 나타내며 .mpp 형식으로 저장할 수 있습니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4단계: 프로젝트에 작업 추가 (add task project)
`Task`는 프로젝트 내 단일 작업 항목을 나타내는 객체입니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### 5단계: 작업 진행률 설정
`Tsk.PERCENT_COMPLETE`는 작업의 완료 비율을 저장하는 필드입니다.

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### 6단계: 업데이트된 진행률 표시
`Tsk.PERCENT_COMPLETE`를 읽으면 작업의 현재 진행률 값을 반환합니다.

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

이 단계들을 따라 하면 **Java에서 MPP 프로젝트를 성공적으로 생성**하고 작업을 추가했으며, **진행률을 변경**했습니다 – 모두 Aspose.Tasks를 사용했습니다.

## Aspose.Tasks에서 작업의 진행률을 설정하는 방법은?
기존 `Project` 객체를 로드하고 대상 `Task`를 찾거나 새로 만든 뒤 `Tsk.PERCENT_COMPLETE`에 새 값을 할당합니다. 라이브러리는 부모 작업의 롤업 값을 자동으로 재계산하므로 전체 일정이 일관성을 유지합니다. 진행률을 업데이트하는 데 필요한 코드는 이 한 줄입니다.

## 일반적인 문제 및 해결 방법
- **FileNotFoundException** – `dataDir`이 파일 구분자(`/` 또는 `\`)로 끝나고 디렉터리가 존재하는지 확인하세요.  
- **LicenseException** – 프로덕션 사용을 위해 `Project` 객체를 만들기 전에 Aspose.Tasks 라이선스를 로드하세요.  
- **Incorrect percent value** – `percent` 메서드는 0에서 100 사이의 값을 기대합니다; 이 범위를 벗어나는 숫자를 전달하면 예외가 발생합니다.

## 자주 묻는 질문

**Q: MPP 파일을 생성하려면 어떤 버전의 Aspose.Tasks가 필요합니까?**  
A: 2023‑2025 범위의 최신 버전이면 `Project` 생성이 지원됩니다; 최신 릴리스를 사용하면 모든 버그 수정 및 성능 향상을 받을 수 있습니다.

**Q: 진행률을 업데이트한 후 프로젝트를 PDF로 내보낼 수 있나요?**  
A: 예, 진행률을 설정한 후 `project.save("output.pdf", SaveFileFormat.PDF);`를 호출하면 시각 보고서를 생성합니다.

**Q: 여러 작업의 진행률을 일괄 업데이트할 수 있나요?**  
A: `project.getRootTask().getChildren()`을 순회하면서 각 작업에 `Tsk.PERCENT_COMPLETE`를 설정하면 API가 효율적으로 각 작업을 업데이트합니다.

**Q: 라이브러리가 리소스 할당을 자동으로 처리합니까?**  
A: 리소스는 명시적으로 추가해야 하며, 작업 진행률은 리소스 관련 필드를 수정하지 않는 한 리소스 할당에 영향을 주지 않습니다.

**Q: 생성된 MPP 파일을 비밀번호로 보호하려면 어떻게 해야 하나요?**  
A: `project.save(...)`를 호출하기 전에 `project.setPassword("yourPassword");`를 사용하여 파일을 암호화합니다.

## 결론
Java로 MPP 프로젝트에서 **진행률 설정 방법**을 마스터하면 일정 유지 관리를 자동화하고 이해관계자에게 정보를 제공하며 프로젝트 데이터를 대규모 엔터프라이즈 워크플로에 통합할 수 있습니다. 선도적인 **Java 프로젝트 관리 라이브러리**인 Aspose.Tasks는 이러한 작업을 간단하고 고성능으로 수행하도록 도와줍니다.

---

**마지막 업데이트:** 2026-09-30  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose

## 관련 튜토리얼

- [Java 프로젝트 관리: Aspose.Tasks를 사용한 작업 % 완료](/tasks/java/task-properties/percentage-complete-calculations/)
- [Aspose.Tasks for Java를 사용하여 작업 데이터를 MPP 형식으로 업데이트하는 방법](/tasks/java/task-properties/update-task-data/)
- [Aspose.Tasks for Java로 작업 우선순위 읽기 및 설정](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}