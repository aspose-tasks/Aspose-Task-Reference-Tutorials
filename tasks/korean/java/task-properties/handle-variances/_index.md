---
date: 2026-02-20
description: Aspose.Tasks for Java를 사용하여 프로젝트 시작 날짜를 설정하고 프로젝트 변동성을 관리하는 방법을 배웁니다.
  이 가이드는 작업 기간을 효율적으로 설정하는 방법도 보여줍니다.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트 시작 날짜 설정 및 작업 변동 처리 Aspose.Tasks
url: /ko/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 시작 날짜 설정 및 작업 변동성 처리 Aspose.Tasks

## Introduction
프로젝트 관리 분야에서 **set project start date**는 일정에 견고한 기반을 제공하기 위해 처음 수행하는 작업 중 하나입니다. Aspose.Tasks for Java는 이 단계와 이후 작업 변동성 처리를 간단하고 신뢰할 수 있게 만들어 줍니다. 이 튜토리얼에서는 프로젝트 시작 날짜를 설정하고, 작업 기간을 설정하며, 프로젝트 변동성을 효율적으로 관리하는 방법을 배웁니다.

## Quick Answers
- **프로젝트 시작 날짜를 설정하는 주요 메서드는 무엇인가요?** `project.set(Prj.START_DATE, …)`를 `java.util.Calendar` 인스턴스와 함께 사용합니다.  
- **변동성 추적을 위한 기준선을 나타내는 클래스는 무엇인가요?** `BaselineType.Baseline`.  
- **기준선을 설정한 후 작업 시작 및 종료 날짜를 조정할 수 있나요?** 예, `Tsk.START`와 `Tsk.STOP`을 업데이트하면 됩니다.  
- **개발용으로 라이선스가 필요합니까?** 평가용 임시 라이선스를 사용할 수 있습니다.  
- **이 코드와 호환되는 Aspose.Tasks 버전은?** 최신 Aspose.Tasks for Java 릴리스입니다.

## What is **set project start date**?
프로젝트 시작 날짜를 설정하면 모든 작업 날짜가 계산되는 기준 캘린더 날짜가 정의됩니다. 이는 일정 계산, 중요 경로 분석 및 기준선 생성에 영향을 미치며, 정확한 변동성 관리를 위해 필수적입니다.

## Why set project start date and manage variances?
- **예측 가능성:** 실제 진행 상황을 비교할 수 있는 알려진 기준선을 설정합니다.  
- **유연성:** 원래 계획을 잃지 않고 개별 작업 날짜를 조정할 수 있습니다.  
- **보고:** 일정 지연이나 조기 완료를 강조하는 명확한 변동성 보고서를 제공합니다.  

## Prerequisites
Before we dive in, make sure you have the following:

- Java Development Environment – JDK가 설치되어 있고 IDE 또는 빌드 도구가 준비되어 있음.  
- Aspose.Tasks Library – 라이브러리를 **[here](https://releases.aspose.com/tasks/java/)**에서 다운로드하십시오.  

## Import Packages
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Setting Up the Project
Create a new `Project` instance which will hold all tasks and schedule information.

```java
Project project = new Project();
```

## Step 2: Adding a Task
Add a task under the root task. This will be the work item we later adjust.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Setting Start Date and Duration
Define the project’s start date and give the task a duration. This demonstrates **set task duration** in practice.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Step 4: Setting Baseline
Create a baseline so you can later compare planned versus actual dates—essential for **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Step 5: Adjusting Task Start and Stop Dates
Modify the task’s start and stop dates to simulate a variance scenario.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*프로젝트의 특정 요구에 맞게 날짜와 기간을 자유롭게 조정하십시오.*

## Common Issues & Tips
- **Baseline must be set before adjusting dates.** 날짜를 먼저 변경하면 기준선이 원래 계획이 아닌 변경된 일정을 캡처합니다.  
- **Calendar months are zero‑based.** `Calendar.FEBRUARY`는 2월이 아니라 월 1에 해당한다는 점을 기억하세요.  
- **Duration units:** `project.getDuration(2)`는 기본적으로 2일 기간을 생성합니다; 시간이거나 주가 필요하면 단위를 조정하십시오.

## Conclusion
**set project start date**, **set task duration**, **manage project variances**를 마스터함으로써 Aspose.Tasks for Java를 사용하여 프로젝트 일정에 대한 완전한 제어권을 얻을 수 있습니다. 위 단계들은 다단계 프로젝트, 리소스 할당 및 자동 보고와 같은 보다 복잡한 시나리오로 확장할 수 있는 견고한 기반을 제공합니다.

## Frequently Asked Questions
### Is Aspose.Tasks suitable for all project management needs?
Aspose.Tasks는 다양한 프로젝트 관리 요구에 적합한 다목적 도구로, 유연성과 강력한 기능을 제공합니다.

### Can I integrate Aspose.Tasks into my existing Java project?
예, 제공된 문서 **[here](https://reference.aspose.com/tasks/java/)**를 따라 Aspose.Tasks를 Java 프로젝트에 쉽게 통합할 수 있습니다.

### Is a temporary license available for Aspose.Tasks?
예, Aspose.Tasks에 대한 임시 라이선스를 **[here](https://purchase.aspose.com/temporary-license/)**에서 얻을 수 있습니다.

### Where can I get support for Aspose.Tasks?
지원 및 토론을 위해 Aspose.Tasks 포럼 **[here](https://forum.aspose.com/c/tasks/15)**을 방문하십시오.

### Can I download Aspose.Tasks for Java?
예, 최신 Aspose.Tasks for Java 버전을 **[here](https://releases.aspose.com/tasks/java/)**에서 다운로드하십시오.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-02-20  
**테스트 환경:** Aspose.Tasks 최신 Java 릴리스  
**작성자:** Aspose