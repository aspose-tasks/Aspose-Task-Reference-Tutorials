---
title: Aspose.Tasks의 작업과 연결된 WBS
linktitle: Aspose.Tasks의 작업과 연결된 WBS
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 WBS 마스터 - 작업 WBS 코드를 읽고 번호를 다시 매기는 방법을 알아보세요. 프로젝트 관리 효율성을 높이세요!
type: docs
weight: 36
url: /ko/java/task-properties/wbs-associated-with-task/
---
## 소개
Aspose.Tasks for Java를 사용하여 프로젝트 관리의 세계에 오신 것을 환영합니다! 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업과 관련된 WBS(작업 분할 구조)의 복잡성을 자세히 살펴보겠습니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 WBS 코드를 효율적으로 관리하는 데 필요한 기본 사항을 탐색하는 데 도움이 될 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Tasks가 다운로드되어 프로젝트에 추가되었습니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
프로젝트를 시작하려면 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## WBS 코드 읽기
작업과 관련된 WBS 코드를 읽는 것부터 시작해 보겠습니다. 다음과 같이하세요:
## 1단계: 프로젝트 로드
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## 2단계: 작업 수집
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 3단계: 구문 분석 및 사용자 정의
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
이 조각은 프로젝트의 작업과 관련된 WBS 코드를 읽고 사용자 정의합니다.
## 작업 WBS 코드 번호 다시 매기기
이제 작업에 대한 WBS 코드 번호 다시 매기기를 살펴보겠습니다.
## 1단계: 프로젝트 로드
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## 2단계: 모든 작업 선택
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## 3단계: 초기 WBS 코드 출력
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## 4단계: WBS 코드 번호 다시 매기기
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## 5단계: 업데이트된 WBS 코드 출력
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
다음 단계를 수행하면 프로젝트의 작업에 대한 WBS 코드 번호를 효과적으로 다시 매길 수 있습니다.
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 WBS 코드로 작업하는 방법을 성공적으로 배웠습니다. 이러한 지식을 통해 프로젝트의 작업 계층 구조를 효율적으로 관리하고 사용자 정의할 수 있습니다.
## 자주 묻는 질문
### Q: Aspose.Tasks for Java에 대한 설명서는 어디에서 찾을 수 있나요?
 A: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/tasks/java/).
### Q: Java용 Aspose.Tasks를 어떻게 다운로드할 수 있나요?
 답: 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 네, 무료 평가판을 받으실 수 있습니다[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원을 위해.
### Q: Aspose.Tasks for Java에 대한 임시 라이선스를 얻을 수 있나요?
 A: 네, 임시 면허를 받으세요.[여기](https://purchase.aspose.com/temporary-license/).