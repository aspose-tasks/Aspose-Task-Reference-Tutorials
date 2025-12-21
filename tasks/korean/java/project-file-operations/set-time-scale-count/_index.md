---
date: 2025-12-21
description: Aspose.Tasks for Java를 사용하여 Gantt 차트 뷰를 사용자 정의하고, 프로젝트 시각화를 관리하며, 프로젝트를
  PDF로 저장하는 방법을 배웁니다. 시간 축 개수를 손쉽게 조정하십시오.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 간트 차트 맞춤 설정 – Aspose.Tasks에서 MS Project 시간 눈금 개수 마스터하기
url: /ko/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt 차트 사용자 지정 – Aspose.Tasks에서 MS Project 시간 눈금 카운트 마스터하기

## Introduction
Microsoft Project에서 **Gantt 차트** 시각화를 사용자 지정해야 할 경우, 시간 눈금 카운트를 제어하는 것이 핵심 기술입니다. Aspose.Tasks for Java를 사용하면 하단 및 중간 시간 눈금 티어를 프로그래밍 방식으로 설정하고, 눈금 표시를 미세 조정한 뒤 **프로젝트를 PDF로 저장**하여 이해관계자와 공유할 수 있습니다. 이 튜토리얼은 환경 설정부터 사용자 지정된 Gantt 뷰를 반영한 깔끔한 PDF 생성까지 전체 과정을 단계별로 안내합니다.

## Quick Answers
- **“Gantt 차트 사용자 지정”이란 무엇인가요?** 시간 눈금 티어, 색상 및 레이아웃을 조정하여 보고 요구사항에 맞추는 작업입니다.  
- **하단 티어 카운트를 설정하는 API 메서드는?** `view.getBottomTimescaleTier().setCount(int)`.  
- **프로젝트에서 직접 PDF를 생성할 수 있나요?** 예—`project.save(..., SaveFileFormat.Pdf)`를 사용합니다.  
- **프로덕션 사용에 라이선스가 필요한가요?** 상업용 라이선스가 필요하며, 무료 체험판을 제공하고 있습니다.  
- **지원되는 Java 버전은?** 최신 Aspose.Tasks 라이브러리는 Java 8 이상에서 동작합니다.

## What is “customize Gantt chart” in Aspose.Tasks?
Gantt 차트를 사용자 지정한다는 것은 시간 눈금 간격, 눈금 표시, 작업 막대 등 시각적 요소를 프로그래밍 방식으로 변경하여 **프로젝트 시각화 관리**에 맞게 차트를 조정하는 것을 의미합니다. 시간 눈금 카운트를 변경하면 각 구간이 며칠, 몇 주, 몇 달을 나타내는지를 제어할 수 있어 다양한 청중에게 차트를 더 명확하게 전달할 수 있습니다.

## Prerequisites
시작하기 전에 다음을 준비하세요:

1. **Java 개발 환경** – JDK 8 이상 설치.  
2. **Aspose.Tasks for Java 라이브러리** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **기본 Java 지식** – Java 문법 및 객체 지향 개념에 익숙할 것.

## Import Packages
Java 프로젝트에 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
프로젝트 파일을 읽고 쓸 디렉터리를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 실제 머신의 절대 경로로 교체하세요.

### Step 2: Create a New Project Instance
모든 작업 및 뷰 설정을 보관할 새로운 `Project` 객체를 인스턴스화합니다:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
`GanttChartView` 객체를 생성합니다—이 객체를 통해 **Gantt 뷰 Java** 코드를 생성하고 차트 외관을 제어합니다:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
하단 티어를 두 개의 간격으로 표시하고 눈금 표시를 숨깁니다:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
중간 티어에도 동일한 구성을 적용합니다:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
구성한 뷰를 `Project` 인스턴스에 추가합니다:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
사용자 지정 Gantt 차트를 보여줄 수 있도록 특정 기간을 가진 작업 몇 개를 생성합니다:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
마지막으로 **사용자 지정된 Gantt 차트**를 포함한 프로젝트를 PDF 파일로 내보냅니다:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

생성된 PDF는 하단 및 중간 시간 눈금 티어가 **사용자 지정**된 모습을 보여주어 이해관계자에게 명확하고 인쇄 가능한 일정 뷰를 제공합니다.

## Common Issues & Troubleshooting
- **PDF가 빈 페이지로 나옵니다** – `dataDir` 경로가 파일 구분자(`/` 또는 `\`)로 끝나는지, 디렉터리가 실제로 존재하는지 확인하세요.  
- **눈금이 여전히 표시됩니다** – 두 티어 모두 `setShowTicks(false)`가 호출되었는지 확인하세요.  
- **기간이 적용되지 않습니다** – 작업 기간을 생성할 때 `TimeUnitType.Hour`(또는 적절한 단위)를 사용했는지 확인하세요.

## Frequently Asked Questions

**Q: Aspose.Tasks for Java가 대규모 프로젝트 파일을 처리할 수 있나요?**  
A: 예, 라이브러리는 방대한 프로젝트 데이터를 고성능으로 처리하도록 최적화되어 있습니다.

**Q: Aspose.Tasks for Java가 다양한 Java IDE와 호환되나요?**  
A: 물론입니다 – Eclipse, IntelliJ IDEA, NetBeans 등 주요 IDE와 원활히 작동합니다.

**Q: 시간 눈금 설정 외에 Gantt 차트 외관을 더 커스터마이즈할 수 있나요?**  
A: 예, Aspose.Tasks는 막대 색상, 폰트, 그리드 라인 등 광범위한 스타일 옵션을 제공합니다.

**Q: Aspose.Tasks for Java의 체험 버전을 제공하나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험 버전을 받을 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: Aspose.Tasks 포럼 [여기](https://forum.aspose.com/c/tasks/15)에서 지원 및 도움을 받을 수 있습니다.

**Q: Gantt 차트 배경 색을 프로그래밍 방식으로 변경하려면 어떻게 하나요?**  
A: `java.awt.Color`를 import한 뒤 `view.getGanttChartProperties().setBackgroundColor(Color)` 메서드를 사용합니다.

## Conclusion
이 단계들을 따라 하면 **Gantt 차트** 시간 눈금 티어를 **사용자 지정**하고 **프로젝트 시각화**를 개선하며 Aspose.Tasks for Java를 이용해 **프로젝트를 PDF로 저장**하는 방법을 익히게 됩니다. 이 접근 방식은 시각적 출력에 대한 완전한 제어를 제공하여 팀이나 클라이언트와 명확하고 전문적인 일정 정보를 쉽게 공유할 수 있게 합니다.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}