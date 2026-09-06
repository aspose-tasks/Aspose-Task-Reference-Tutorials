---
date: 2026-08-29
description: Aspose.Tasks for Java를 사용하여 baseline duration을 설정하고 프로젝트 진행 상황을 추적하는
  방법을 배웁니다. 이 step‑by‑step 가이드는 task baselines를 효율적으로 관리하는 데 도움이 됩니다.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java에서 Baseline Duration 설정 방법
og_description: Aspose.Tasks for Java를 사용하여 baseline duration을 설정하고 프로젝트 진행 상황을 추적하는
  방법을 배웁니다. 자세한 이 가이드를 따라 task baselines를 효율적으로 관리하세요.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: 프로젝트 진행 상황을 추적하기 위해 baseline duration 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: 프로젝트 진행 상황을 추적하기 위해 baseline duration 설정하는 방법
url: /ko/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 진행 상황을 추적하기 위한 기준 기간 설정 방법

## 소개
프로젝트 진행 상황을 추적하려면 견고한 기준선이 필요합니다. 이 튜토리얼에서는 Aspose.Tasks Java 라이브러리를 사용하여 Microsoft Project 파일의 작업에 **기준 기간 설정 방법**을 알아보고, 초기에 기준선을 설정하면 프로젝트 전체 기간 동안 일정 편차, 비용 변동 및 자원 과다 할당을 모니터링하는 데 어떻게 도움이 되는지 이해하게 됩니다.

## 빠른 답변
- **“set baseline”이 의미하는 바는 무엇인가요?** 작업의 원래 시작, 종료 및 기간을 기록하여 향후 변경 사항과 비교할 수 있습니다.  
- **어떤 Aspose.Tasks 클래스가 프로젝트를 생성하나요?** `Project` 클래스 – 또한 **프로젝트 인스턴스 생성** 방법을 올바르게 배울 수 있습니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 무료 평가 라이선스로 테스트가 가능하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **중간 기준선을 조회할 수 있나요?** 예, Aspose.Tasks를 사용하면 중간 기준선 및 해당 고정 비용을 조회할 수 있습니다.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상을 권장합니다.  
- **이것이 프로젝트 진행 상황을 추적하는 데 어떻게 도움이 되나요?** 기준선을 설정하면 내장된 보고 기능을 사용해 실제 날짜를 원래 계획과 즉시 비교할 수 있습니다.

## 작업 기준선이란 무엇이며 왜 설정해야 하나요?
작업 기준선은 특정 시점에 계획된 일정(시작 날짜, 종료 날짜 및 기간)을 기록합니다. 기준선을 설정하면 프로젝트가 진행됨에 따라 일정 편차, 비용 초과 및 자원 과다 할당을 쉽게 파악할 수 있는 기준점을 만들게 됩니다.

## 기준선 관리에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks는 **전체 .mpp 호환성**을 제공하므로 Microsoft Office를 설치하지 않고도 기본 Microsoft Project 파일을 읽고 쓸 수 있습니다. API를 통해 **50개 이상의 입력 및 출력 형식**에 프로그래밍 방식으로 접근할 수 있으며, **중간 기준선 1‑10**을 지원하고 전체 파일을 메모리에 로드하지 않고도 **수백 페이지 프로젝트**를 처리할 수 있어 고성능 배치 처리에 필수적입니다.

## 전제 조건
1. **Java 개발 환경** – JDK 8 이상이 설치되고 구성되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 라이브러리를 [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE 또는 빌드 도구** – Maven, Gradle 또는 선호하는 IDE를 사용합니다.

## 패키지 가져오기
다음 import 문은 프로젝트, 작업, 기준선 및 시간 구간 데이터 작업에 필요한 핵심 Aspose.Tasks 클래스를 가져옵니다.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 단계 1: 프로젝트 인스턴스 생성
`Project` 클래스는 메모리 내에서 Microsoft Project 파일을 나타내며 모든 작업의 진입점입니다.

```java
Project project = new Project();
```

## 단계 2: 작업 기준선 생성
`TaskBaseline`은 특정 작업에 대한 계획된 시작, 종료 및 기간을 저장합니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 단계 3: 작업 기준선 정보 표시
`getBaselines()` 메서드는 작업에 연결된 기준선 컬렉션을 반환합니다.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 단계 4: 중간 기준선 및 고정 비용 확인
`BaselineType`은 기본 및 중간 기준선(Baseline, Baseline1‑Baseline10)을 열거합니다.

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 단계 5: 시간 구간 데이터 출력
`TimephasedData`는 특정 시간 구간에 대한 일정 정보를 나타냅니다.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

이 단계들을 따라 하면 Aspose.Tasks for Java를 사용하여 모든 작업에 **기준 기간을 설정**하고 상세한 기준선 정보를 조회할 수 있으며, 이를 통해 프로젝트 수명 주기 전반에 걸쳐 **프로젝트 진행 상황을 추적**하는 신뢰할 수 있는 방법을 제공합니다.

## 일반적인 문제 및 해결책
- **기준선이 MS Project에 표시되지 않음:** 작업을 추가한 **후에** `project.setBaseline(BaselineType.Baseline)`을 호출했는지 확인하십시오.  
- **`getBaselines()`에서 NullPointerException:** 기준선을 설정하기 전에 작업이 프로젝트에 추가되었는지 확인하십시오.  
- **시간 단위 불일치:** 특히 사용자 정의 캘린더를 사용할 때는 `TimeUnitType`을 사용해 기간을 올바르게 포맷하십시오.

## FAQ
### MS Project에서 작업 기준선이란 무엇인가요?
MS Project에서 작업 기준선은 작업에 대한 초기 계획 일정(시작 날짜, 종료 날짜 및 기간)의 스냅샷입니다.

### 작업 기준선 관리가 중요한 이유는 무엇인가요?
작업 기준선을 관리하면 계획된 일정과 실제 진행 상황을 비교할 수 있어 보다 나은 추적 및 의사결정을 지원합니다.

### 설정된 작업 기준선을 수정할 수 있나요?
예, MS Project에서 작업 기준선을 수정하여 프로젝트 계획 변경을 반영할 수 있습니다. 다만 원래 기준선에서의 모든 편차를 문서화하는 것이 중요합니다.

### Aspose.Tasks가 다른 프로젝트 관리 기능을 지원하나요?
예, Aspose.Tasks는 작업 일정 관리, 자원 할당, 간트 차트 생성 등 프로젝트 관리에 필요한 다양한 기능을 제공합니다.

### Aspose.Tasks 지원은 어디에서 찾을 수 있나요?
Aspose.Tasks에 대한 지원은 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 찾을 수 있으며, 여기서 질문을 하고 다른 사용자와 소통할 수 있습니다.

## 추가 자주 묻는 질문
**Q: 각 작업마다 `setBaseline`을 호출해야 하나요?**  
A: 아니요. `project.setBaseline(BaselineType.Baseline)`을 호출하면 프로젝트의 모든 작업에 대한 기준선을 한 번에 기록합니다.

**Q: 특정 작업에 중간 기준선을 설정하려면 어떻게 해야 하나요?**  
A: 작업 일정 업데이트 후 `project.setBaseline(BaselineType.Baseline1)`(또는 Baseline2‑Baseline10)를 사용합니다.

**Q: 기준선 데이터를 CSV로 내보낼 수 있나요?**  
A: 예. `task.getBaselines()`를 반복하면서 원하는 필드를 표준 Java I/O를 사용해 CSV 파일에 기록합니다.

**Q: 이미 기준선이 포함된 기존 .mpp 파일을 읽을 수 있나요?**  
A: 물론입니다. `new Project("myproject.mpp")`로 파일을 로드한 뒤 위와 같이 각 작업의 기준선을 접근하면 됩니다.

**Q: Aspose.Tasks가 다중 프로젝트 파일을 처리하나요?**  
A: Aspose.Tasks는 단일 프로젝트 .mpp 파일을 지원합니다. 다중 프로젝트 시나리오에서는 프로그램matically 프로젝트를 결합해야 합니다.

---

**마지막 업데이트:** 2026-08-29  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Java 작업 목록 만들기 – Aspose.Tasks를 사용한 MS Project 기준선](/tasks/java/task-baselines/create-task-baseline/)
- [Java MPP 프로젝트 만들기 – Aspose.Tasks로 작업 진행 상황 변경](/tasks/java/task-properties/change-progress/)
- [프로젝트 관리 기준선 – Aspose.Tasks를 사용한 작업 일정 관리](/tasks/java/task-baselines/baseline-task-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}