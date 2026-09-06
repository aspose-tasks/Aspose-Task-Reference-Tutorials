---
date: 2026-08-29
description: Aspose.Tasks를 사용하여 Microsoft Project 없이 Java에서 프로젝트에 task를 추가하고 task
  list를 만들며 baseline을 설정하는 방법을 배웁니다.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Aspose.Tasks에서 Task Baseline 만들기
og_description: Aspose.Tasks를 사용하여 Java에서 프로젝트에 task를 추가하고 baseline을 설정하는 방법을 배웁니다.
  이 가이드는 Microsoft Project 없이 단계별 코드를 보여줍니다.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Java에서 프로젝트에 task를 추가하고 baseline을 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Java에서 프로젝트에 task를 추가하고 baseline을 설정하는 방법
url: /ko/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 프로젝트에 작업을 추가하고 기준선을 설정하는 방법

## 소개
이 튜토리얼에서는 프로그래밍 방식으로 **add task to project**를 수행하고, Microsoft Project 작업 기준선을 생성한 뒤 파일을 저장합니다—Microsoft Project를 전혀 열지 않고도 가능합니다. Aspose.Tasks for Java는 순수 Java API를 제공하여 모든 플랫폼에서 작동하므로 자동화된 빌드 파이프라인, 보고 서비스 또는 .mpp 파일을 조작해야 하는 모든 서버 측 솔루션에 적합합니다.

## 빠른 답변
- **What does Aspose.Tasks do?** Microsoft Project를 필요로 하지 않고 Microsoft Project 파일을 생성, 읽기 및 편집하기 위한 Java API를 제공합니다.  
- **Do I need Microsoft Project installed?** 아니요, 라이브러리는 완전히 독립적으로 작동합니다.  
- **Which Java version is required?** JDK 8 이상이 필요합니다.  
- **Can I set a baseline for a single task?** 예 – 원하는 작업만 포함하는 리스트에 `setBaseline`을 호출하면 됩니다.  
- **Is a license needed for production?** 예, 상용 라이선스를 사용하면 평가 제한이 해제되고 모든 기능을 사용할 수 있습니다.

## 작업 기준선이란?
작업 기준선은 일정이 처음 저장될 때 작업에 대해 원래 계획된 시작 날짜, 종료 날짜 및 작업량을 기록합니다. 이 스냅샷은 기준점으로 작용하여 프로젝트 관리자가 실제 진행 상황과 비용을 초기 계획과 비교하고, 성과 분석을 위한 편차를 계산할 수 있게 합니다.

## Java에서 프로젝트에 작업을 추가하기 위해 Aspose.Tasks를 사용하는 이유
데스크톱 설치 없이 작업을 생성, 수정 및 기준선을 설정할 수 있어 완전 자동화된 워크플로우를 구현할 수 있습니다. Aspose.Tasks는 **50+ 입력 및 출력 형식**을 지원하며 **수백 개의 작업**이 포함된 프로젝트도 메모리 사용량을 200 MB 이하로 유지하면서 처리할 수 있어 클라우드 서비스 및 CI/CD 파이프라인에 이상적입니다.

## 전제 조건
1. **Java Development Kit (JDK)** – JDK 8 이상을 설치합니다.  
2. **Aspose.Tasks for Java** – 라이브러리를 [download link](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks를 사용하려면 필요한 패키지를 가져오세요:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 단계 1: 프로젝트 객체 생성
`Project` 클래스는 메모리 내에서 Microsoft Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 이를 인스턴스화하면 작업, 리소스 및 캘린더를 추가할 수 있는 빈 프로젝트가 생성됩니다.
```java
Project project = new Project();
```
여기서 새 `Project` 객체를 인스턴스화합니다 – 이는 작업 목록을 보관할 MS Project 파일을 나타냅니다.

## 단계 2: 프로젝트에 작업 추가
`Task` 클래스는 프로젝트 일정에서 개별 작업 항목을 나타냅니다. 각 `Task`는 자체 기간, 시작 날짜 및 리소스 할당을 가질 수 있습니다.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()`를 사용하여 프로젝트 계층 구조의 루트에 접근하고 **add task to Microsoft Project**를 수행합니다. 문자열 `"Task"`는 작업 이름이며, 필요에 따라 원하는 설명으로 교체할 수 있습니다.

## 단계 3: 지정된 작업에 기준선 설정
`BaselineType`은 어떤 기준선 슬롯(Baseline, Baseline1 … Baseline10)을 기록할지 정의하는 열거형입니다. 작업 리스트를 전달하면 선택한 항목만 기준선을 설정할 수 있습니다.
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**set baseline without MS Project**를 위해, 기준선을 설정하려는 작업 리스트(여기서는 `myList`)를 만든 뒤 `setBaseline`에 전달합니다. 선택적인 기준선만 필요하다면 추가한 작업으로 `myList`를 채우세요.

## 단계 4: 전체 프로젝트에 기준선 설정
`setBaseline`은 선택한 기준선 값을 프로젝트의 모든 작업에 기록합니다.  
전체 프로젝트에 한 번에 기준선을 설정하려면 원하는 `BaselineType`을 지정하여 `setBaseline`을 호출하면 됩니다.
```java
project.setBaseline(BaselineType.Baseline);
```
이 호출은 프로젝트의 **모든 작업**에 선택된 기준선 값을 기록하여 원래 일정의 완전한 스냅샷을 보장합니다.

## Aspose.Tasks를 사용하여 Microsoft Project에 작업을 추가하는 방법
`add()`는 지정된 상위 작업 아래에 새로운 하위 작업을 생성하고 새로 만든 `Task` 객체를 반환합니다.  
상위 `Task` 객체(보통 루트 작업)에서 `add()`를 호출하여 작업을 추가합니다. 이 메서드는 지속 시간, 시작 날짜, 리소스 또는 사용자 정의 필드 등을 추가로 구성할 수 있는 새로운 `Task` 인스턴스를 반환하며, 이후 프로젝트 파일을 저장합니다.

## MS Project 없이 기준선 설정하는 방법
Aspose.Tasks를 사용하면 완전히 코드만으로 기준선을 생성할 수 있습니다. `BaselineType`(예: `BaselineType.Baseline`)을 선택하고 `setBaseline`을 호출합니다. `Baseline1`‑`Baseline10`을 사용해 여러 개의 수정 기준선을 유지할 수 있으며, 모두 Microsoft Project를 열지 않고 수행됩니다.

## 일반적인 문제 및 해결책
- **Baseline not appearing:** 기준선을 설정한 후 `project.save("output.mpp")`를 호출했는지 확인하세요(간결성을 위해 저장 단계는 생략되었습니다).  
- **Task list appears empty:** 작업을 올바른 상위(`getRootTask()` 또는 하위 작업)에 추가했는지 확인하세요.  
- **Version mismatch errors:** 최신 Aspose.Tasks JAR를 사용하여 최신 .mpp 형식과의 호환성을 보장하세요.

## 자주 묻는 질문

**Q: Microsoft Project를 설치하지 않고 Aspose.Tasks for Java를 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 독립적으로 작동하며 호스트 머신에 Microsoft Project가 필요하지 않습니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project와 호환되나요?**  
A: 물론입니다. 이 라이브러리는 2007년부터 최신 2024년 릴리스까지의 Project 파일을 지원합니다.

**Q: Aspose.Tasks for Java를 사용하여 프로젝트 리소스를 조작할 수 있나요?**  
A: 예, 작업과 마찬가지로 리소스를 프로그래밍 방식으로 추가, 업데이트 및 삭제할 수 있습니다.

**Q: Aspose.Tasks for Java가 작업 종속성 설정을 지원하나요?**  
A: 예, `TaskLink` 클래스를 사용하여 선행‑후행 관계를 정의할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 기술 지원이 제공되나요?**  
A: 예, [support forum](https://forum.aspose.com/c/tasks/15)에서 Aspose 직원 및 커뮤니티가 질문에 답변해 줍니다.

## 결론
이 단계들을 따라 하면 Java에서 **add task to project**하는 방법, 작업 목록 생성, 그리고 Aspose.Tasks를 사용하여 **set baseline without MS Project**하는 방법을 배웠습니다. 이 접근 방식은 프로젝트 자동화를 간소화하고 데스크톱 Project 설치 필요성을 없애며 일정의 모든 측면을 완전하게 프로그래밍적으로 제어할 수 있게 합니다.

---

**마지막 업데이트:** 2026-08-29  
**테스트 대상:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [프로젝트 생성 방법 aspose.tasks – 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Aspose.Tasks for Java에서 기준선 기간 설정 방법](/tasks/java/task-baselines/task-baseline-duration/)
- [Aspose Java에서 작업 생성 – 작업 속성](/tasks/java/task-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}