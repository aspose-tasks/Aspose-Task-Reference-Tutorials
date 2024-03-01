---
title: Aspose.Tasks에서 작업 분할
linktitle: Aspose.Tasks에서 작업 분할
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java에서 작업 관리를 마스터하세요! 최적화된 프로젝트 일정을 위해 작업을 효율적으로 분할하는 방법을 알아보세요. 지금 다운로드하세요!
type: docs
weight: 29
url: /ko/java/task-properties/split-tasks/
---
## 소개
Java 프로젝트에서 작업 관리에 어려움을 겪고 계십니까? Aspose.Tasks for Java는 작업을 효율적으로 분할하고 프로젝트 관리 기능을 향상시키는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업을 분할하는 프로세스를 안내하여 프로젝트 타임라인과 리소스 할당을 최적화하는 데 도움을 줍니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Tasks가 다운로드되어 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Tasks for Java 문서](https://reference.aspose.com/tasks/java/).
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요.
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
Aspose.Tasks 라이브러리를 사용하여 새 프로젝트를 만드는 것부터 시작하세요.
```java
// 새 프로젝트 만들기
Project splitTaskProject = new Project();
```
## 2단계: 프로젝트 달력 설정
타임라인을 설정하려면 프로젝트의 달력 설정을 지정하세요.
```java
// 표준 달력 받기
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// 프로젝트의 달력 설정 지정
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (예제 계속)
```
## 3단계: 루트 작업 추가
프로젝트에 루트 작업을 추가합니다.
```java
// 루트 작업
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## 4단계: 분할할 새 작업 추가
분할하려는 프로젝트에 새 작업을 추가하세요.
```java
// 새 작업 추가
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## 5단계: 자원 할당 생성
작업에 대한 새 자원 할당을 만듭니다.
```java
// 새 자원 할당 만들기
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## 6단계: 시간대별 데이터 생성
자원 할당 시간대별 데이터를 생성합니다.
```java
// 자원 할당 시간대별 데이터 생성
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## 7단계: 작업 분할
작업을 여러 부분으로 분할합니다.
```java
// 작업을 3개 부분으로 나누기
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (예제 계속)
```
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 작업을 분할하는 방법을 성공적으로 배웠습니다. 이 강력한 라이브러리는 Java 프로젝트의 작업 관리를 단순화하여 프로젝트 일정 및 리소스 할당을 최적화하기 위한 효율적인 솔루션을 제공합니다.
## 자주 묻는 질문
### 기간이 다른 작업을 분할할 수 있나요?
예, 프로젝트 요구 사항에 따라 작업 기간을 조정할 수 있습니다.
### Aspose.Tasks for Java는 모든 Java 버전과 호환됩니까?
Aspose.Tasks for Java는 다양한 Java 버전과 원활하게 작동하도록 설계되어 호환성을 보장합니다.
### Java용 Aspose.Tasks를 무료로 사용할 수 있나요?
Aspose.Tasks for Java는 구매하기 전에 기능을 살펴볼 수 있는 무료 평가판을 제공합니다.
### Java용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 방문하다[Aspose.Tasks for Java 지원 포럼](https://forum.aspose.com/c/tasks/15) 도움을 받고 지역 사회와 연결됩니다.
### Aspose.Tasks for Java에 대한 임시 라이선스가 필요합니까?
 임시면허를 취득하실 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로.