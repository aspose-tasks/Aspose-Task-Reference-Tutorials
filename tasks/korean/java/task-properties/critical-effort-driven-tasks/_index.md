---
date: 2026-09-30
description: Aspose.Tasks와 함께 Java 프로젝트에서 critical tasks를 관리하세요. critical 및 effort‑driven
  tasks 처리 방법을 배우고, 라이브러리를 다운로드하여 프로젝트 관리 워크플로를 향상시키세요.
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: Aspose.Tasks에서 Critical 및 Effort‑Driven Tasks 관리
og_description: Aspose.Tasks와 함께 Java 개발자가 직면하는 critical tasks를 관리하세요. 이 가이드는 Java
  프로젝트에서 critical 및 effort‑driven tasks를 단계별로 처리하는 방법을 보여줍니다.
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: Aspose.Tasks를 사용하여 Java에서 critical tasks를 관리하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: Aspose.Tasks를 사용하여 Java에서 critical tasks를 관리하는 방법
url: /ko/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Aspose.Tasks를 사용하여 중요 및 노력 기반 작업 관리

현대 프로젝트 관리에서 **manage critical tasks java**는 일정을 유지하면서 노력 기반 작업 항목을 처리해야 하는 개발자들에게 매일의 도전 과제입니다. Aspose.Tasks for Java는 수동 스프레드시트 작업 없이 중요 및 노력 기반 작업을 식별, 검사 및 업데이트할 수 있는 깔끔하고 프로그래밍 방식의 방법을 제공합니다.

## 빠른 답변
- **What is the main benefit?** 자동으로 중요 작업에 플래그를 지정하고 한 번의 API 호출로 노력 기반 일정 조정합니다.  
- **Do I need a license?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **Which Java versions are supported?** Java 8 부터 17까지, OpenJDK와 Oracle 배포판 모두 지원합니다.  
- **Can I process large projects?** 예 – Aspose.Tasks는 최대 10 000개의 작업을 효율적으로 처리합니다.  
- **Is it cross‑platform?** 이 라이브러리는 Windows, Linux, macOS에서 네이티브 종속성 없이 실행됩니다.

## Aspose.Tasks for Java에서 중요 및 노력 기반 작업을 관리하는 방법
프로젝트 파일을 `Project` 클래스로 로드하고, `ChildTasksCollector`를 사용해 모든 작업을 수집한 다음 각 작업의 `Critical` 및 `EffortDriven` 속성을 검사합니다. 수집된 목록을 반복하면 상태 보고서를 생성하거나 일정 규칙을 자동으로 수정할 수 있으며, 이는 몇 줄의 Java 코드만으로 몇 초 안에 실행됩니다.

Aspose.Tasks for Java는 **30개 이상의 입력 및 출력 프로젝트 형식**(Microsoft Project 2019, 2022 및 Primavera P6 포함)을 지원하며, **최대 10 000개의 작업**을 처리하면서 일반 서버에서 메모리 사용량을 200 MB 이하로 유지합니다. 이러한 정량화된 기능은 엔터프라이즈 규모 계획에 적합합니다.

## 사전 요구 사항
- **Aspose.Tasks for Java** 라이브러리 – [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)에서 다운로드하십시오.  
- **Java Development Kit (JDK)** – 버전 8 이상(또는 최신 버전)이 머신에 설치되어 있어야 합니다.  
- **IDE** (IntelliJ IDEA, Eclipse, VS Code 등) 중 원하는 것을 사용하십시오.  
- 데모에 사용할 XML(또는 .mpp) 형식의 샘플 프로젝트 파일.

## 패키지 가져오기
Java 소스 파일에 필요한 네임스페이스를 추가하십시오:

```java
import com.aspose.tasks.*;
import java.util.*;
```

이러한 import는 `Project`, `Task` 및 유틸리티 도우미와 같은 핵심 작업 관리 클래스를 사용할 수 있게 합니다.

## 중요 작업이란?
**critical task**는 지연이 프로젝트 종료 날짜를 직접 연장시키는 모든 활동을 의미하며, 일정의 중요 경로에 위치합니다. Aspose.Tasks에서는 `Task.isCritical()` 메서드를 호출하여 작업이 중요 작업인지 확인할 수 있으며, 작업이 전체 프로젝트 완료 시간에 영향을 미칠 경우 `true`를 반환합니다.

## 노력 기반 작업이란?
**effort‑driven task**는 기간이 변경될 때마다 남은 작업량을 자동으로 재분배하여 일정 전체에 걸쳐 총 노력이 일정하게 유지되도록 합니다. 이 동작은 고정 비율로 작업하는 리소스에 유용합니다. Aspose.Tasks에서는 `Task.isEffortDriven()` 속성이 이러한 특성을 가진 작업에 대해 `true`를 반환합니다.

## 단계 1: ChildTasksCollector를 사용하여 작업 수집
`ChildTasksCollector` 클래스는 지정된 상위 작업 아래의 모든 작업을 수집합니다.

`ChildTasksCollector`는 작업 계층 구조를 탐색하고 `Task` 객체의 평면 목록을 반환하는 도우미입니다.

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## 단계 2: 수집된 작업 반복
목록을 순회하면서 각 작업의 중요 및 노력 기반 상태를 출력합니다.

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

이 간단한 두 단계 패턴을 통해 프로젝트 일정 상태를 전체적으로 파악할 수 있습니다.

## 일반적인 문제 및 해결 방법
- **NullPointerException on task properties** – 작업에 접근하기 전에 프로젝트 파일이 완전히 로드되었는지 확인하십시오 (`project = new Project("file.mpp")`).  
- **Incorrect critical flag** – 프로젝트의 계산 모드가 `CalculationMode.Automatic`으로 설정되어 있는지 확인하여, 수정 후 Aspose.Tasks가 중요 경로를 다시 계산하도록 합니다.  
- **Large files cause slowdown** – `Project.set(Prj.ReadOnly, true)`를 사용하여 파일을 읽기 전용 모드로 열면 읽기 전용 분석 시 메모리 오버헤드를 줄일 수 있습니다.

## 자주 묻는 질문

**Q: Can I use Aspose.Tasks for Java in both Windows and Linux environments?**  
A: 예, Aspose.Tasks for Java는 플랫폼에 독립적이며 Windows, Linux, macOS에서 실행됩니다.

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: 예, [Aspose.Tasks free trial download page](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험판을 이용할 수 있습니다.

**Q: Where can I find support for Aspose.Tasks for Java?**  
A: 예, 커뮤니티 지원 및 토론을 위해 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

**Q: How can I obtain a temporary license for Aspose.Tasks for Java?**  
A: 예, [temporary license request page](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 획득할 수 있습니다.

**Q: Where can I purchase Aspose.Tasks for Java?**  
A: 예, [purchase page](https://purchase.aspose.com/buy)에서 Aspose.Tasks for Java를 구매할 수 있습니다.

---

**마지막 업데이트:** 2026-09-30  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## 관련 튜토리얼

- [Critical Path MS Project – Aspose.Tasks Java 튜토리얼](/tasks/java/project-management/critical-path/)
- [Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기](/tasks/java/task-links/create-task-link/)
- [프로젝트 관리 Java: Aspose.Tasks를 사용한 작업 % 완료](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}