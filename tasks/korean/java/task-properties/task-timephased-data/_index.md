---
date: 2026-02-28
description: Aspose.Tasks for Java를 사용하여 작업 시간 단계 데이터를 관리하는 방법을 배우고, 라이브러리를 다운로드하고,
  무료로 체험하여 프로젝트 추적을 효율화하세요.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 작업 시간 단계 데이터를 관리하는 방법 (Java)
url: /ko/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 작업 시간 구간 데이터 활용 방법

## Introduction
프로젝트 일정에 대한 철저한 관리를 원한다면 **Aspose 사용 방법**을 찾고 계신 것이 맞습니다. 작업 시간 구간 데이터의 정확한 추적은 성공적인 프로젝트 관리의 핵심이며, Aspose.Tasks for Java은 이 과정을 자동화하는 데 필요한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용해 프로젝트를 생성하고, 리소스를 할당하고, 기준선을 설정한 뒤, 최종적으로 시간 구간 데이터를 검색하고 표시하는 전체 흐름을 단계별로 안내합니다.

## Quick Answers
- **“시간 구간 데이터(timephased data)”란 무엇인가요?** 프로젝트 일정 동안 작업, 비용 또는 남은 작업을 일, 주, 월 등 시간 간격별로 나눈 데이터입니다.  
- **어떤 라이브러리가 이 기능을 제공하나요?** Aspose.Tasks for Java.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상.  
- **결과를 Excel로 내보낼 수 있나요?** 예 – `TimephasedData` 컬렉션을 순회하면서 원하는 형식으로 값을 기록할 수 있습니다.

## What is Task Timephased Data?
작업 시간 구간 데이터는 프로젝트 캘린더의 각 시간 구간마다 작업(또는 비용)이 예약된 양을 나타냅니다. 이를 통해 작업 배분 상황을 파악하고, 과다 할당을 발견하며, 계획 대비 실제 진행 상황을 비교할 수 있습니다.

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Full control** – Microsoft Project를 열지 않고도 프로그래밍 방식으로 시간 구간 정보를 생성, 수정, 조회할 수 있습니다.  
- **Cross‑platform** – Java를 지원하는 모든 OS에서 동작합니다.  
- **No COM dependencies** – 서버‑사이드 자동화에 최적화되었습니다.  
- **Rich API** – 기준선, 작업 컨투어, 사용자 정의 필드를 기본적으로 지원합니다.

## Prerequisites
코드 작성을 시작하기 전에 다음을 준비하세요:

- **Java Development Environment** – JDK 8 이상이 설치되고 `JAVA_HOME`이 설정되어 있어야 합니다.  
- **Aspose.Tasks for Java Library** – Aspose.Tasks 라이브러리를 다운로드하여 프로젝트에 포함시킵니다. 라이브러리는 [여기](https://releases.aspose.com/tasks/java/)에서 찾을 수 있습니다.  
- **Document Directory** – 샘플 프로젝트 파일(`project.xml`)을 읽고 쓸 수 있는 로컬 폴더가 필요합니다.

## Import Packages
Java 프로젝트에서 필요한 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* `Project` 인스턴스를 생성하고, 원하는 시작 날짜로 `Calendar`를 초기화한 뒤, 이를 프로젝트의 `START_DATE` 속성에 할당합니다.

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* 루트 작업 아래에 **Task**라는 새 작업을 추가합니다. 또한 **Rsc**라는 리소스를 생성하고 표준 요금 및 초과 근무 요금을 설정합니다.

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* 작업 기간을 **6일**로 지정합니다.

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* 앞서 정의한 리소스를 `ResourceAssignment`를 통해 작업에 연결합니다.

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* 할당의 중지 및 재시작 날짜를(플레이스홀더 값 사용) 설정하고, **Back‑Loaded** 작업 컨투어를 적용하여 작업량이 할당 말기에 집중되도록 합니다.

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* 기준선을 설정하면 이후에 계획값과 실제값을 비교할 수 있습니다.

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* 작업을 **50 % 완료** 상태로 표시하면 남은 작업량 계산에 반영됩니다.

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* 이 호출은 할당에 대한 **남은 작업**을 프로젝트의 시간 구간별로 가져옵니다.

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* 시간 구간 항목 수와 첫 번째 항목의 값을 간단히 출력합니다. 실제 환경에서는 리스트를 순회하면서 데이터를 보고서나 UI에 내보내게 됩니다.

## Common Issues and Solutions
- **`getTimephasedData`에서 NullPointerException** – 메서드를 호출하기 전에 할당의 `START`와 `FINISH` 날짜가 설정되어 있는지 확인하세요.  
- **잘못된 작업 컨투어** – 선택한 `WorkContourType`이 일정 전략에 맞는지 확인하십시오; `BackLoaded`는 여러 옵션 중 하나에 불과합니다.  
- **기준선이 변경 사항을 반영하지 않음** – 작업, 리소스, 할당을 정의한 후에 `project.setBaseline`을 호출해야 합니다.

## Frequently Asked Questions
### Q: Aspose.Tasks for Java를 어떤 Java 프로젝트에서도 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 모든 Java 기반 프로젝트와 호환됩니다.

### Q: Aspose.Tasks for Java에 대한 추가 지원은 어디서 받을 수 있나요?
A: 지원 및 토론을 위해 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15)을 방문하세요.

### Q: Aspose.Tasks for Java의 무료 체험판을 이용할 수 있나요?
A: 예, 무료 체험판은 [여기](https://releases.aspose.com/)에서 확인할 수 있습니다.

### Q: Aspose.Tasks for Java 임시 라이선스는 어떻게 얻나요?
A: 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.

### Q: Aspose.Tasks for Java를 구매하려면 어디로 가야 하나요?
A: 구매는 [여기](https://purchase.aspose.com/buy)에서 진행할 수 있습니다.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}