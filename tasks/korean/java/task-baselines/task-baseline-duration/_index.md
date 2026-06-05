---
date: 2026-01-23
description: Aspose.Tasks for Java를 사용하여 기준선 기간을 설정하고 프로젝트 인스턴스를 만드는 방법을 배우세요. 이 단계별
  가이드는 작업 기준선을 효율적으로 관리하는 데 도움이 됩니다.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java에서 기준선 기간 설정 방법
url: /ko/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java에서 기준선 지속 시간 설정 방법

## Introduction
프로젝트 진행 상황을 원래 계획과 비교하기 위해 기준선을 설정하는 것은 기본적인 단계입니다. 이 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project의 작업에 **기준선 지속 시간을 설정하는 방법**을 배우고, 초기에 기준선을 설정하면 나중에 시간과 골칫거리를 절약할 수 있는 이유를 확인합니다.

## Quick Answers
- **“set baseline”이 의미하는 것은?** 작업의 원래 시작일, 종료일 및 지속 시간을 기록하여 이후 변경 사항과 비교할 수 있게 합니다.  
- **Aspose.Tasks에서 프로젝트를 생성하는 클래스는?** `Project` 클래스 – 또한 **프로젝트 인스턴스 생성** 방법을 올바르게 배우게 됩니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 무료 평가 라이선스로 테스트가 가능하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **중간 기준선을 조회할 수 있나요?** 예, Aspose.Tasks를 사용하면 중간 기준선 및 해당 고정 비용을 조회할 수 있습니다.  
- **필요한 Java 버전은?** Java 8 이상을 권장합니다.

## What is a task baseline and why set it?
작업 기준선은 특정 시점에 계획된 일정(시작일, 종료일, 지속 시간)을 캡처합니다. 기준선을 설정하면 프로젝트가 진행됨에 따라 일정 지연, 비용 초과, 자원 과다 할당 등을 쉽게 파악할 수 있는 기준점을 만들게 됩니다.

## Why use Aspose.Tasks for baseline management?
- **전체 .mpp 호환성** – Office 없이도 네이티브 Microsoft Project 파일을 읽고 쓸 수 있습니다.  
- **풍부한 API** – 프로그래밍 방식으로 기준선 데이터, 중간 기준선 및 시간 단계 정보를 액세스합니다.  
- **크로스 플랫폼** – 표준 JDK가 설치된 Windows, Linux, macOS에서 모두 동작합니다.

## Prerequisites
1. **Java 개발 환경** – JDK 8 이상이 설치되고 설정되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 라이브러리를 [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE 또는 빌드 도구** – Maven, Gradle 또는 선호하는 IDE를 사용합니다.

## Import Packages
먼저, Java 프로젝트에 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Step 1: Create a Project Instance
단계 1: 프로젝트 인스턴스 생성  
프로젝트 인스턴스를 만드는 것은 이후 모든 조작의 기반이 됩니다. 이 단계에서는 Aspose.Tasks를 사용하여 **프로젝트 인스턴스 생성** 방법을 보여줍니다:

```java
Project project = new Project();
```

## Step 2: Create a Task Baseline
단계 2: 작업 기준선 생성  
프로젝트 루트에 새 작업을 추가하고 기준선을 설정합니다. 이렇게 하면 해당 작업의 원래 일정이 기록됩니다:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Step 3: Display Task Baseline Information
단계 3: 작업 기준선 정보 표시  
방금 만든 기준선을 가져와 주요 속성을 출력합니다. 이를 통해 기준선이 올바르게 설정되었는지 확인할 수 있습니다:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Step 4: Check Interim Baseline and Fixed Cost
단계 4: 중간 기준선 및 고정 비용 확인  
중간 기준선을 사용 중이라면 현재 기준선이 중간 기준선인지와 연관된 고정 비용을 조회할 수 있습니다:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Step 5: Print Timephased Data
단계 5: 시간 단계 데이터 출력  
시간 단계 데이터는 기준선이 시간에 따라 어떻게 분포되는지 보여줍니다. 컬렉션을 순회하면서 각 항목을 검사합니다:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

이러한 단계를 따라 하면 Aspose.Tasks for Java를 사용하여 모든 작업에 대해 **기준선 지속 시간을 설정하는 방법**을 익히고 상세한 기준선 정보를 조회할 수 있습니다.

## Common Issues and Solutions
- **기준선이 MS Project에 표시되지 않음:** 작업을 추가한 **후에** `project.setBaseline(BaselineType.Baseline)`을 호출했는지 확인하십시오.  
- **`getBaselines()`에서 NullPointerException:** 기준선을 설정하기 전에 작업이 프로젝트에 추가되었는지 확인하십시오.  
- **시간 단위 불일치:** 특히 사용자 정의 캘린더를 사용할 때는 `TimeUnitType`을 사용해 지속 시간을 올바르게 포맷하십시오.

## FAQ's
### What is a task baseline in MS Project?
MS Project에서 작업 기준선은 작업에 대한 초기 계획 일정(시작일, 종료일, 지속 시간)의 스냅샷을 의미합니다.

### Why is managing task baselines important?
작업 기준선을 관리하면 계획된 일정과 실제 진행 상황을 비교할 수 있어 추적 및 의사결정에 도움이 됩니다.

### Can I modify a task baseline once it's set?
예, 프로젝트 계획 변경을 반영하기 위해 MS Project에서 작업 기준선을 수정할 수 있습니다. 다만 원래 기준선에서의 모든 편차를 문서화하는 것이 중요합니다.

### Does Aspose.Tasks support other project management functionalities?
예, Aspose.Tasks는 작업 일정 관리, 자원 할당, 간트 차트 생성 등 다양한 프로젝트 관리 기능을 제공합니다.

### Where can I find support for Aspose.Tasks?
Aspose.Tasks에 대한 지원은 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 찾을 수 있으며, 여기서 질문을 하고 다른 사용자와 소통할 수 있습니다.

## Additional Frequently Asked Questions
**Q: 각 작업마다 `setBaseline`을 호출해야 하나요?**  
A: 아닙니다. `project.setBaseline(BaselineType.Baseline)`을 호출하면 프로젝트의 모든 작업에 대한 기준선을 한 번에 기록합니다.

**Q: 특정 작업에 중간 기준선을 설정하려면 어떻게 해야 하나요?**  
A: 작업 일정이 업데이트된 후 `project.setBaseline(BaselineType.Baseline1)`(또는 Baseline2‑Baseline10) 을 사용합니다.

**Q: 기준선 데이터를 CSV로 내보낼 수 있나요?**  
A: 예. `task.getBaselines()`를 순회하면서 원하는 필드를 표준 Java I/O를 사용해 CSV 파일에 기록하면 됩니다.

**Q: 이미 기준선이 포함된 기존 .mpp 파일을 읽을 수 있나요?**  
A: 물론입니다. `new Project("myproject.mpp")` 로 파일을 로드한 뒤 위와 같이 각 작업의 기준선을 접근하면 됩니다.

**Q: Aspose.Tasks가 다중 프로젝트 파일을 처리하나요?**  
A: Aspose.Tasks는 단일 프로젝트 .mpp 파일을 지원합니다. 다중 프로젝트 상황에서는 프로그램matically 프로젝트를 결합해야 합니다.

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}