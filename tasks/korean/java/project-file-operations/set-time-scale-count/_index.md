---
title: Aspose.Tasks에서 MS 프로젝트 시간 규모 계산 마스터하기
linktitle: Aspose.Tasks에서 시간 척도 수 설정
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 시간 규모 수를 효과적으로 관리하는 방법을 알아보세요. 프로젝트 시각화 및 관리를 손쉽게 최적화하세요.
weight: 22
url: /ko/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 시간 규모 계산 마스터하기

## 소개
MS Project에서 시간 규모 수를 관리하면 프로젝트 시각화 및 관리에 큰 영향을 미칠 수 있습니다. 프로젝트 관리 작업을 프로그래밍 방식으로 처리하기 위한 강력한 API인 Aspose.Tasks for Java를 사용하면 시간 척도 수를 효율적으로 조작하여 프로젝트 보기를 특정 요구 사항에 맞게 조정할 수 있습니다.
## 전제조건
시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.
1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
2.  Aspose.Tasks for Java 라이브러리: Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍에 대한 기본 지식: Java 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 1단계: 데이터 디렉터리 설정
프로젝트 파일이 저장될 데이터 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 데이터 디렉토리 경로로.
## 2단계: 프로젝트 인스턴스 생성
 새 인스턴스화`Project` 물체:
```java
Project project = new Project();
```
그러면 새 프로젝트 개체가 생성됩니다.
## 3단계: 간트 차트 보기 구성
 만들기`GanttChartView` Gantt 차트 보기를 구성하는 개체:
```java
GanttChartView view = new GanttChartView();
```
## 4단계: 하위 계층에 대한 시간 척도 수 설정
하단 날짜 표시줄 계층에 대한 개수 및 틱 표시 여부를 설정합니다.
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
이는 간격 수와 하위 계층에 대한 틱 표시 여부를 지정합니다.
## 5단계: 중간 계층에 대한 시간 단위 수 설정
마찬가지로 중간 기간 계층을 구성합니다.
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## 6단계: 프로젝트에 뷰 추가
프로젝트에 구성된 보기를 추가합니다.
```java
project.getViews().add(view);
```
그러면 프로젝트에 사용자 정의된 보기가 추가됩니다.
## 7단계: 프로젝트에 테스트 데이터 추가
데모를 위해 프로젝트에 일부 테스트 데이터를 추가합니다.
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
이렇게 하면 지정된 기간을 가진 두 개의 작업이 생성됩니다.
## 8단계: 프로젝트를 PDF로 저장
프로젝트를 PDF 파일로 저장합니다.
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
이렇게 하면 적용된 구성이 포함된 프로젝트가 PDF 파일로 저장됩니다.

## 결론
Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 시간 규모 수를 효과적으로 관리하면 더 나은 시각화 및 관리를 위해 프로젝트 보기를 사용자 정의할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java가 대규모 프로젝트 파일을 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 대규모 프로젝트 파일을 효율적으로 처리할 수 있습니다.
### Q: Aspose.Tasks for Java는 다른 Java IDE와 호환됩니까?
A: 예, Aspose.Tasks for Java는 Eclipse 및 IntelliJ IDEA와 같은 널리 사용되는 Java 통합 개발 환경(IDE)과 원활하게 작동합니다.
### Q: Aspose.Tasks for Java를 사용하여 Gantt 차트의 모양을 사용자 정의할 수 있나요?
A: 물론, Aspose.Tasks for Java는 요구 사항에 따라 Gantt 차트의 모양을 사용자 정의할 수 있는 광범위한 기능을 제공합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 네, 다음 사이트에서 무료 평가판을 받으실 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 A: Aspose.Tasks 포럼에서 지원과 지원을 찾을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
