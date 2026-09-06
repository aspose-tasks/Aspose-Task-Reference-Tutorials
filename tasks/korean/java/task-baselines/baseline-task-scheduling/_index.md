---
date: 2026-08-29
description: Aspose.Tasks for Java를 사용하여 baseline 데이터를 읽고 작업을 스케줄링하는 방법을 배우고, 계획 대비
  실제 진행 상황을 효율적으로 비교할 수 있습니다.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks의 Baseline 작업 스케줄링
og_description: Aspose.Tasks for Java를 사용하여 baseline 데이터를 읽고 작업을 스케줄링하는 방법을 배우면, 계획
  대비 실제 진행 상황을 정확하게 비교할 수 있습니다.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Aspose.Tasks를 사용하여 baseline을 읽고 작업을 스케줄링하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Aspose.Tasks를 사용하여 baseline을 읽고 작업을 스케줄링하는 방법
url: /ko/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 기준선 및 작업 일정 읽는 방법

이 가이드에서는 Aspose.Tasks for Java를 사용하여 **기준선을 읽는 방법**과 작업을 프로그래밍 방식으로 일정에 배정하는 방법을 알아봅니다. 튜토리얼이 끝날 때쯤 원래 프로젝트 계획을 캡처하고 실제 진행 상황과 비교하며 변동 보고서를 생성할 수 있게 됩니다—Microsoft Project를 설치할 필요 없이.

## 프로젝트 관리 기준선 소개

효과적인 프로젝트 관리를 위해 **프로젝트 관리 기준선**을 관리하는 것은 핵심 요소입니다. 이는 원래 계획을 캡처하고 나중에 **계획 대비 실제 진행**을 비교할 수 있게 하여 변동을 조기에 파악할 수 있게 합니다. 이번 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업 기준선을 일정에 배정하는 방법을 단계별로 살펴보고, **프로젝트 기준선을** 자신 있게 관리하고 프로젝트를 정상 궤도에 유지하는 도구를 제공합니다.

## 빠른 답변
- **프로젝트 관리 기준선은 무엇을 나타내나요?**  
  프로젝트 시작 시 승인된 일정, 비용 및 범위를 기록하며 변동 분석을 위한 기준점을 제공합니다.  
- **Java에서 기준선 일정을 처리하는 라이브러리는 무엇인가요?**  
  Aspose.Tasks for Java는 45개 이상의 입력 및 출력 형식을 지원하고 최대 100 000개의 작업을 처리할 수 있는 순수 Java API를 제공합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?**  
  무료 체험판으로 테스트가 가능하며, 실제 운영을 위해서는 상용 라이선스가 필요합니다.  
- **주요 전제 조건은 무엇인가요?**  
  Java Development Kit (JDK) 11 이상 및 Aspose.Tasks for Java 라이브러리.  
- **기준선 날짜를 설정한 후에도 확인할 수 있나요?**  
  예—`TaskBaseline` 객체를 사용하여 시작, 종료 및 기간 값을 읽을 수 있습니다.

## 프로젝트 관리 기준선이란 무엇인가요?

프로젝트 관리 기준선은 실행 시작 시 승인된 일정, 예산 및 범위를 기록합니다. 이는 프로젝트 수명 주기 전반에 걸쳐 성과를 측정하고 편차를 식별하기 위한 기준점으로 활용됩니다. 여기에는 계획된 시작 및 종료 날짜, 총 비용, 범위 세부 정보가 포함되어 향후 비교를 위한 포괄적인 스냅샷을 제공합니다.

## 왜 Aspose.Tasks를 기준선 일정에 사용하나요?

Aspose.Tasks는 Microsoft Project가 설치되지 않아도 동작하는 순수 Java API를 제공합니다. **45개 이상의 입력 및 출력 형식**을 지원하고, 메모리 효율 모드에서 **최대 100 000개의 작업**을 처리할 수 있으며, 기준선 데이터를 읽고 쓰는 내장 메서드를 제공해 자동화된 보고 및 통합을 간편하게 합니다.

## 전제 조건
- **Java Development Kit (JDK)** – JDK 11 이상을 설치합니다. [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드할 수 있습니다.  
- **Aspose.Tasks for Java 라이브러리** – 최신 릴리스를 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드하고 JAR 파일을 프로젝트의 클래스패스에 추가합니다.

## 패키지 가져오기
`Project`, `Task`, `TaskBaseline` 클래스는 `com.aspose.tasks` 네임스페이스에 있습니다. 소스 파일 상단에 이를 import합니다:

`Project` 클래스는 메모리 내에서 단일 프로젝트 파일을 나타내는 Aspose.Tasks의 최상위 객체이며, 작업, 리소스 및 기준선 컬렉션에 대한 접근을 제공합니다.

## 기준선을 읽는 방법은?
프로젝트를 로드한 뒤 각 작업에 대해 `TaskBaseline` 컬렉션을 조회합니다. `TaskBaseline` 객체는 `setBaseline`을 호출했을 때 캡처된 기준선 시작, 종료 및 기간을 반환합니다. 이 직접적인 접근 방식은 XML이나 바이너리 파일을 파싱하지 않고도 기준선 값을 읽을 수 있게 해줍니다.

## 단계 1: 새 프로젝트 인스턴스 만들기
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## 단계 2: 작업 정의 및 기준선 설정
```java
Project project = new Project();
```

## 단계 3: 기준선 정보 접근
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 단계 4: 기준선 기간 표시
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 단계 5: 기준선 시작 날짜 표시
```java
System.out.println(baseline.getDuration().toString());
```

## 단계 6: 기준선 종료 날짜 표시
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 일반적인 문제 및 해결책
- **기준선이 설정되지 않음:** 작업을 추가한 **후에** `project.setBaseline(BaselineType.Baseline)`을 호출했는지 확인하세요; 그렇지 않으면 기준선 컬렉션이 비어 있습니다.  
- **Null 값:** `task.getBaselines()`가 빈 리스트를 반환하면, 기준선을 설정하기 전에 작업이 프로젝트 계층에 추가되었는지 확인하세요.  
- **날짜 형식:** `getStart()` 및 `getFinish()` 메서드는 `java.util.Date` 객체를 반환합니다. 사용자 정의 표시 형식이 필요하면 `SimpleDateFormat`을 사용하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks에서 새 프로젝트 인스턴스를 어떻게 만들나요?**  
A: `Project` 클래스를 인스턴스화합니다 (`Project project = new Project();`). 이렇게 하면 작업 및 기준선을 위한 새로운 프로젝트 파일이 생성됩니다.

**Q: `BaselineType.Baseline`과 다른 기준선 유형의 차이는 무엇인가요?**  
A: `BaselineType.Baseline`은 기본 기준선 (Baseline 1)을 의미합니다. Aspose.Tasks는 추가 스냅샷을 위해 Baseline 2‑10도 지원합니다.

**Q: 기준선 데이터를 Excel이나 CSV로 내보낼 수 있나요?**  
A: 예, `TaskBaseline` 객체를 순회하면서 표준 Java I/O를 사용해 값을 CSV 파일에 기록할 수 있습니다.

**Q: 기준선을 설정하면 기존 작업 날짜에 영향을 줍니까?**  
A: 기준선을 설정하면 현재 날짜를 캡처하지만 작업의 활성 일정은 변경되지 않습니다. 기준선 설정 후에도 시작/종료 날짜를 조정할 수 있습니다.

**Q: 여러 기준선을 프로그래밍 방식으로 비교할 수 있나요?**  
A: 물론입니다. `task.getBaselines().get(index)`를 통해 각 기준선을 가져와 `Start`, `Finish`, `Duration` 속성을 비교하면 됩니다.

---

**마지막 업데이트:** 2026-08-29  
**테스트 대상:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 관련 튜토리얼

- [Aspose.Tasks를 사용한 Java 작업 목록 생성 – MS Project 기준선](/tasks/java/task-baselines/create-task-baseline/)
- [Aspose.Tasks for Java에서 기준선 기간 설정 방법](/tasks/java/task-baselines/task-baseline-duration/)
- [Java MPP 프로젝트 생성 – Aspose.Tasks로 작업 진행률 변경](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}