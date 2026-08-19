---
date: 2026-02-26
description: Aspose.Tasks for Java를 사용하여 작업을 분할하는 방법을 배우세요 – 작업 분할, 프로젝트 캘린더 설정 및
  리소스 할당 생성에 대한 최종 가이드.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 작업을 분할하는 방법
url: /ko/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 분할하는 방법

## 소개
Java 기반 프로젝트에서 **작업을 분할하는 방법**을 찾고 있다면, 바로 이곳이 맞습니다. Aspose.Tasks for Java는 장기 작업을 더 작고 관리하기 쉬운 부분으로 나누는 깔끔하고 프로그래밍 방식의 방법을 제공하여, 리소스 레벨링, 정확한 보고 및 프로젝트 일정 단축에 도움이 됩니다. 이 튜토리얼에서는 프로젝트 캘린더 설정부터 리소스 할당 생성, 최종적으로 작업을 여러 구간으로 분할하는 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **작업 분할이란?** 전체 지속 시간을 유지하면서 단일 작업을 여러 작은 구간으로 나누는 것.  
- **Java에서 작업을 분할하는 이유는?** 정확한 리소스 할당과 향상된 진행 상황 추적을 가능하게 합니다.  
- **어떤 라이브러리를 사용하나요?** Aspose.Tasks for Java가 분할 및 시간 단계 기능을 내장하고 있습니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상에서 작동합니다.

## 전제 조건
튜토리얼을 진행하기 전에 다음 전제 조건을 확인하세요:
- 머신에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
- Aspose.Tasks for Java 라이브러리를 다운로드하여 프로젝트에 추가했습니다. 라이브러리는 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져옵니다:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## 1단계: 새 프로젝트 만들기
Aspose.Tasks 라이브러리를 사용하여 새 프로젝트를 생성합니다:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## 2단계: 프로젝트 캘린더 설정
**프로젝트 캘린더**를 설정하면 작업일, 휴일 및 전체 일정이 정의됩니다. 정확한 시간 단계 계산을 위해 필수적인 단계입니다.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## 3단계: 루트 작업 추가
모든 프로젝트에는 루트 컨테이너가 필요합니다. 루트 작업을 추가하면 이후 작업들을 연결할 위치가 생깁니다.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## 4단계: 분할할 새 작업 추가
분할하려는 작업을 생성합니다. 여기서는 예시로 3일 지속 시간을 설정합니다.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## 5단계: 리소스 할당 생성
**리소스 할당**은 리소스(또는 플레이스홀더)를 작업에 연결합니다. 시간 단계 데이터를 생성하기 전에 반드시 필요합니다.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## 6단계: 시간 단계 데이터 생성
시간 단계 데이터는 작업 기간 동안 작업이 어떻게 배분되는지를 나타냅니다. 이를 생성하면 작업을 분할할 준비가 됩니다.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## 7단계: 작업 분할
이제 **작업을 여러 부분으로 분할**합니다. 예시에서는 3일 작업을 1일 구간 3개로 나눕니다.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## 작업을 분할하는 이유
작업을 분할하면 다음과 같은 세부 제어가 가능합니다:
- **리소스 레벨링:** 각 구간에 다른 리소스를 할당합니다.  
- **진행 상황 추적:** 구간별로 상태를 업데이트합니다.  
- **보고:** 보다 상세한 간트 차트와 보고서를 생성합니다.

## 일반적인 문제와 해결책
- **캘린더 데이터 누락:** 분할 전에 `timephasedDataFromTaskDuration` 호출을 확인하세요.  
- **0‑기간 구간:** 각 분할 구간이 0이 아닌 기간을 갖는지 확인하십시오. 그렇지 않으면 라이브러리가 해당 구간을 무시합니다.  
- **라이선스 예외:** 유효한 라이선스 없이 실행하면 내보낸 파일에 워터마크가 추가될 수 있습니다.

## 자주 묻는 질문
### 다른 기간으로 작업을 분할할 수 있나요?
예, 각 구간의 기간을 프로젝트 요구에 맞게 조정할 수 있습니다.

### Aspose.Tasks for Java가 모든 Java 버전과 호환되나요?
Aspose.Tasks for Java는 Java 8 이상과 원활하게 작동하도록 설계되어 광범위한 호환성을 제공합니다.

### Aspose.Tasks for Java를 무료로 사용할 수 있나요?
Aspose.Tasks for Java는 무료 체험판을 제공하므로 구매 전에 기능을 탐색할 수 있습니다.

### Aspose.Tasks for Java에 대한 지원은 어떻게 받나요?
[Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15)에서 도움을 받고 커뮤니티와 연결할 수 있습니다.

### Aspose.Tasks for Java에 임시 라이선스가 필요합니까?
테스트 및 평가 목적을 위해 [this link](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

---

**마지막 업데이트:** 2026-02-26  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}