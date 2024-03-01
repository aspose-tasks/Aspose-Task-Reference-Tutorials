---
title: Aspose.Tasks에서 작업 속성 마스터하기
linktitle: Aspose.Tasks에서 작업의 일반 속성을 읽고 씁니다.
second_title: Aspose.Tasks 자바 API
description: 작업 속성을 쉽게 관리할 수 있는 Aspose.Tasks for Java의 기능을 살펴보세요. 단계별 가이드를 사용하여 쉽게 읽고 쓰세요.
type: docs
weight: 26
url: /ko/java/task-properties/read-write-general-properties/
---
## 소개
Aspose.Tasks를 사용하여 Java에서 작업 관리의 잠재력을 최대한 활용하세요. 이 포괄적인 가이드에서는 Aspose.Tasks for Java를 사용하여 작업의 일반 속성을 읽고 쓰는 방법을 자세히 살펴보겠습니다. 숙련된 개발자이든 초보자이든 이 튜토리얼을 통해 작업 속성을 쉽게 조작할 수 있는 기술을 익힐 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Tasks를 다운로드하고 설정했습니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
- IntelliJ IDEA 또는 Eclipse와 같은 코드 편집기.
## 패키지 가져오기
작업을 시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다. 이 단계에서는 Aspose.Tasks 기능에 액세스할 수 있는지 확인합니다. 다음은 안내하는 스니펫입니다.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 태스크의 일반 속성 읽기
## 1단계: 작업 생성
프로젝트에서 작업을 생성하는 것부터 시작하세요. 여기에는 작업 이름, 시작 날짜 및 기타 관련 세부 정보 설정이 포함됩니다. 예는 다음과 같습니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## 2단계: 작업 속성 읽기
이제 작업을 생성했으므로 일반 속성을 검색하고 표시해 보겠습니다. 다음 코드 조각은 이를 수행합니다.
```java
// 태스크의 일반 속성 읽기
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## 태스크의 일반 속성 작성
## 3단계: 프로젝트 로드 및 컬렉터 생성
 일반 속성을 작성하려면 기존 프로젝트를 로드하고`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## 4단계: 속성 분석 및 표시
마지막으로 수집된 작업을 구문 분석하고 해당 속성을 표시합니다.
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
축하해요! Aspose.Tasks for Java를 사용하여 작업의 일반 속성을 성공적으로 읽고 썼습니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업 속성을 원활하게 조작하는 기본 단계를 살펴보았습니다. 이러한 기술을 익히면 Java 개발 기술을 향상하고 프로젝트의 작업 관리를 간소화할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 Java 11과 호환됩니까?
예, Aspose.Tasks는 Java 11 이상 버전과 호환됩니다.
### 상업용 프로젝트에 Aspose.Tasks를 사용할 수 있나요?
 전적으로! Aspose.Tasks는 개인 및 상업 프로젝트 모두를 위한 강력한 도구입니다. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 옵션을 살펴보세요.
### 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가를 위해.
### Aspose.Tasks에 대한 커뮤니티 지원은 어디서 찾을 수 있나요?
 커뮤니티 토론에 참여하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원과 협력을 위해.
### 참조할 수 있는 샘플 프로젝트가 있습니까?
 설명서의 예제 섹션 살펴보기[여기](https://reference.aspose.com/tasks/java/) 샘플 프로젝트 및 코드 조각의 경우.