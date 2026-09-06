---
date: 2026-08-29
description: Aspose.Tasks for Java를 사용하여 링크 유형을 설정하고 작업 종속성을 관리하는 방법을 단계별 튜토리얼에서 배웁니다.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java에서 링크 유형 설정 방법
og_description: Aspose.Tasks for Java를 사용하여 링크 유형을 설정하고 작업 종속성을 관리하는 방법을 알아보세요. 개발자를
  위한 단계별 가이드.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Aspose.Tasks for Java에서 링크 유형 설정 방법
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Aspose.Tasks for Java에서 링크 유형 설정 방법
url: /ko/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java에서 링크 유형 설정 방법

## 소개
프로젝트에서 작업 종속성을 *관리*하면서 **링크 설정 방법**에 대해 궁금하다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 새 프로젝트를 만들고, 작업을 추가하고, 링크 유형(Start‑to‑Start, Finish‑to‑Start 등)을 정의하는 과정을 단계별로 안내합니다. 끝까지 진행하면 실제 일정 요구에 맞게 작업 관계를 맞춤 설정하는 자신감을 얻고, API가 최대 10,000개의 작업을 포함하는 대규모 계획을 어떻게 처리하는지 확인할 수 있습니다.

## 빠른 답변
- **종속성을 나타내는 클래스는 무엇인가요?** `TaskLink`는 두 작업 간의 링크를 모델링하는 핵심 객체입니다.  
- **관계 유형을 정의하는 열거형은?** `TaskLinkType` (예: `StartToStart`, `FinishToStart`).  
- **기존 링크 유형을 읽을 수 있나요?** 예 – `Project.getTaskLinks()`를 반복하고 `getLinkType()`을 호출합니다.  
- **이 코드에 라이선스가 필요합니까?** 테스트용 임시 라이선스로 작동하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **Java 8+와 호환되나요?** 물론 – Aspose.Tasks는 Java 8부터 Java 21까지 지원하며, 13개의 주요 릴리스를 포괄합니다.

## 작업 링크란?
**작업 링크**는 프로젝트 일정에서 두 작업 간의 종속성을 모델링합니다.  
`TaskLink`를 생성, 수정 또는 삭제하여 선행‑후속 관계를 반영할 수 있으며, 이를 통해 스케줄러가 시작 및 종료 날짜를 자동으로 계산합니다.

## 왜 Aspose.Tasks 링크 유형을 사용하나요?
Aspose.Tasks는 **30개 이상의 입력 및 출력 형식**을 지원하며 전체 파일을 메모리에 로드하지 않고도 **최대 10,000개의 작업**을 포함하는 프로젝트를 처리할 수 있습니다. 이러한 정량화된 기능은 엔터프라이즈 규모 계획에서도 빠른 성능을 보장하며, 라이브러리는 사용자 정의 필드 및 리소스 할당과 같은 Microsoft Project의 모든 기능을 보존합니다.

## 전제 조건
- **Java 개발 환경** – JDK 8 이상이 설치되고 구성되어 있어야 합니다.  
- **Aspose.Tasks 라이브러리** – 최신 JAR을 [다운로드 링크](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
- **문서 디렉터리** – 샘플 프로젝트 파일을 보관할 폴더를 컴퓨터에 생성합니다.

## 패키지 가져오기
우리는 필수 Aspose.Tasks 클래스를 가져오는 것으로 시작합니다. 이렇게 하면 IDE가 나중에 사용할 API 호출을 인식할 수 있게 됩니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Aspose.Tasks for Java에서 링크 유형을 설정하는 방법?
새로운 `Project` 인스턴스를 로드하고 두 작업을 추가한 다음 원하는 `TaskLinkType`으로 `TaskLink`를 생성합니다. 이 두 단계 패턴을 사용하면 한 번의 호출로 네 가지 표준 종속성 유형 중 어느 것이든 정의할 수 있습니다. `Project`는 전체 프로젝트 파일과 일정을 나타냅니다. `Task`는 프로젝트 내의 개별 작업 항목입니다. `TaskLink`는 선행 작업을 후속 작업에 연결합니다. `TaskLinkType`은 관계를 지정하는 열거형이며 (Start‑to‑Start, Finish‑to‑Start 등) 입니다.

### 단계 1: 링크 유형 설정
`TaskLink`는 두 작업 간의 종속성을 나타내며, `TaskLinkType`은 `StartToStart`와 같은 가능한 관계 유형을 열거합니다. 이 단계에서는 새 프로젝트를 만들고 두 작업을 추가한 뒤 **Start‑to‑Start** 관계를 사용하여 연결합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** `StartToStart`를 `FinishToStart`, `StartToFinish` 또는 `FinishToFinish`로 교체하여 필요에 따라 **작업 종속성 관리**를 할 수 있습니다.

### 단계 2: 링크 유형 가져오기
`Project.getTaskLinks()`는 일정에 있는 모든 `TaskLink` 객체의 컬렉션을 반환합니다. 이 컬렉션을 반복하면 각 링크의 `TaskLinkType`을 읽고 올바른 관계가 저장되었는지 확인할 수 있습니다.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

콘솔은 `StartToStart`, `FinishToStart` 등과 같은 값을 출력하여 이전에 설정한 링크 유형을 확인합니다.

## 일반적인 문제 및 해결책
- **링크 추가 시 NullPointerException** – `TaskLink`를 만들기 전에 선행 작업과 후속 작업이 프로젝트에 추가되어 있는지 확인하십시오.  
- **저장 후 잘못된 링크 유형** – 링크 유형을 설정한 후에는 항상 `project.save("output.mpp")`(또는 다른 지원 형식)를 호출하여 변경 사항을 저장하십시오.  
- **라이선스를 찾을 수 없음** – Aspose.Tasks 라이선스 파일을 프로젝트 클래스패스에 배치하고 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 로드하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks가 다양한 Java 환경과 호환됩니까?**  
A: 예, Aspose.Tasks는 추가 종속성 없이 표준 Java SE, Java EE 및 Android 개발 키트와 통합됩니다.

**Q: 프로젝트 요구 사항에 따라 링크 유형을 맞춤 설정할 수 있나요?**  
A: 물론입니다. `TaskLinkType` 열거형은 네 가지 표준 유형을 제공하며, 지연값과 결합하여 복잡한 일정을 모델링할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?**  
A: 자세한 가이드, API 레퍼런스 및 코드 샘플은 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)을 참조하십시오.

**Q: Aspose.Tasks용 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 테스트용 임시 라이선스를 받으려면 [temporary license page](https://purchase.aspose.com/temporary-license/)를 방문하십시오.

**Q: Aspose.Tasks 관련 문의에 대한 지원은 어디서 받을 수 있나요?**  
A: 지원 및 토론을 위해 [support forum](https://forum.aspose.com/c/tasks/15)에서 Aspose.Tasks 커뮤니티에 참여하십시오.

**Q: 프로젝트를 저장한 후에 링크 유형을 변경할 수 있나요?**  
A: 예. 프로젝트를 로드하고 `TaskLink`를 검색한 뒤 `setLinkType()`을 새로운 열거값으로 호출하고 다시 저장하면 됩니다.

**Q: Aspose.Tasks가 Microsoft Project (MPP) 파일을 읽는 것을 지원하나요?**  
A: 지원합니다. `new Project("file.mpp")`를 사용하여 MPP 파일을 로드하고 위의 XML 예제와 동일하게 작업 링크를 처리할 수 있습니다.

---

**마지막 업데이트:** 2026-08-29  
**테스트 대상:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 교차 프로젝트 작업 링크 만들기](/tasks/java/task-links/create-cross-project-task-link/)
- [Aspose.Tasks에서 프로젝트 시작 날짜 설정 및 상위/하위 작업 관리](/tasks/java/task-properties/parent-child-tasks/)
- [Java에서 MPP 파일 로드 - Aspose.Tasks로 프로젝트 속성 관리](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}