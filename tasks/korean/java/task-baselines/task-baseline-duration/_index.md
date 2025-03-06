---
title: Aspose.Tasks의 작업 기준 기간 관리
linktitle: Aspose.Tasks의 작업 기준 기간 관리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 작업 기준선을 효율적으로 관리하는 방법을 알아보세요. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.
weight: 12
url: /ko/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 작업 기준 기간 관리

## 소개
MS Project에서 작업 기준선을 관리하는 것은 프로젝트 계획 및 추적에 중요합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업 기준 기간을 효과적으로 관리하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
2.  Aspose.Tasks 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 Java 프로젝트에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## 1단계: 프로젝트 인스턴스 생성
다음 코드를 사용하여 새 프로젝트 인스턴스를 초기화합니다.
```java
Project project = new Project();
```
## 2단계: 작업 기준선 만들기
다음 코드를 사용하여 새 작업을 만들고 기준을 설정합니다.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## 3단계: 작업 기준 정보 표시
기간, 시작 날짜, 완료 날짜 등과 같은 작업 기준 정보를 검색하고 표시합니다.
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## 4단계: 임시 기준 및 고정 비용 확인
기준선이 임시 기준선인지 확인하고 이와 관련된 고정 비용을 검색합니다.
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## 5단계: 시간대별 데이터 인쇄
작업 기준과 관련된 시간대별 데이터를 인쇄합니다.
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 작업 기준 기간을 효과적으로 관리할 수 있습니다.

## 결론
작업 기준선 관리는 프로젝트 관리에 필수적이며, 이를 통해 계획된 일정과의 편차를 추적할 수 있습니다. Aspose.Tasks for Java를 사용하면 이 프로세스가 간소화되고 효율적이 되어 더 나은 프로젝트 제어 및 제공이 가능해집니다.
## FAQ
### MS Project의 작업 기준선이란 무엇입니까?
MS Project의 작업 기준선은 시작 날짜, 완료 날짜 및 기간을 포함하여 작업에 대한 초기 계획 일정의 스냅샷입니다.
### 작업 기준선 관리가 중요한 이유는 무엇입니까?
작업 기준선을 관리하면 계획된 일정과 프로젝트의 실제 진행 상황을 비교하여 더 나은 추적 및 의사 결정을 내리는 데 도움이 됩니다.
### 작업 기준이 설정된 후에 이를 수정할 수 있나요?
예, 프로젝트 계획의 변경 사항을 반영하도록 MS Project의 작업 기준선을 수정할 수 있습니다. 그러나 원래 기준과의 편차를 문서화하는 것이 중요합니다.
### Aspose.Tasks는 다른 프로젝트 관리 기능을 지원합니까?
예, Aspose.Tasks는 작업 일정 관리, 리소스 할당, 간트 차트 생성을 포함하여 프로젝트 관리를 위한 광범위한 기능을 제공합니다.
### Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 Aspose.Tasks에 대한 지원은 다음에서 찾을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15), 질문을 하고 다른 사용자와 상호 작용할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
