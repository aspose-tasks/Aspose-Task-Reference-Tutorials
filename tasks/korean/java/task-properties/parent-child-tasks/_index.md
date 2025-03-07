---
title: Aspose.Tasks에서 상위 및 하위 작업 관리
linktitle: Aspose.Tasks에서 상위 및 하위 작업 관리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java로 프로젝트 관리 효율성을 향상하세요. 상위 및 하위 작업을 단계별로 관리하는 방법을 알아보세요. 지금 시작하세요!
weight: 24
url: /ko/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 상위 및 하위 작업 관리

## 소개
프로젝트 관리 영역에서는 효과적인 작업 구성이 중요합니다. Aspose.Tasks for Java는 상위 및 하위 작업을 효율적으로 관리할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트 작업을 간소화하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 이해.
-  Aspose.Tasks for Java 라이브러리가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
- 시스템에 설치된 Java IDE(통합 개발 환경).
## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다. 이러한 패키지는 Java 기능을 위한 Aspose.Tasks와의 원활한 통합을 촉진합니다.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## 1단계: 프로젝트 시작 날짜 설정
프로젝트 시작 날짜 및 기타 관련 매개변수를 설정하여 시작하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// 패키지 가져오기를 위한 추가 코드를 여기에 추가할 수 있습니다.
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## 2단계: 상위 작업 추가(작업 1)
"Task 1"이라는 상위 작업을 만들고 해당 속성을 구성합니다.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## 3단계: 하위 작업이 포함된 상위 작업(작업 2) 추가
이제 "작업 2"라는 다른 상위 작업을 추가하고 하위 작업(작업 3 및 작업 4)을 포함합니다.
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// 작업 2에 하위 작업 추가
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// 작업 3 및 작업 4에 대한 추가 구성을 여기에 추가할 수 있습니다.
```
## 4단계: 하위 작업 구성
작업 3과 작업 4에 대한 시작 날짜, 기간 및 제약 조건을 지정합니다.
```java
// 작업 3 구성
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// 작업 4 구성
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## 5단계: 작업 완료율 업데이트
작업 3과 작업 4의 완료율을 조정합니다.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## 6단계: 프로젝트 저장
마지막으로 변경 사항이 적용된 프로젝트를 저장합니다.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
이 단계별 가이드에서는 Aspose.Tasks for Java를 사용하여 상위 및 하위 작업을 효과적으로 관리하는 방법을 보여줍니다. 프로젝트 요구 사항에 맞게 다양한 구성을 실험해 보세요.
## 결론
결론적으로 Aspose.Tasks for Java는 개발자가 프로젝트 작업을 효율적으로 처리하여 원활한 구성 및 추적을 보장할 수 있도록 지원합니다. 프로젝트 관리 역량을 강화하기 위해 간략하게 설명된 단계를 구현하세요.
## 자주 묻는 질문
### Aspose.Tasks for Java는 다른 프로젝트 파일 형식과 호환됩니까?
예, Aspose.Tasks for Java는 MPP 및 XML을 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### 이 튜토리얼에서 다루는 것 이상으로 작업 속성을 사용자 정의할 수 있습니까?
전적으로! Aspose.Tasks for Java는 작업 속성에 대한 광범위한 사용자 정의 옵션을 제공합니다.
### 지원을 구할 수 있는 Aspose.Tasks 커뮤니티 포럼이 있나요?
 네, 방문하실 수 있습니다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역 사회 지원을 위해.
### Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Tasks에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
