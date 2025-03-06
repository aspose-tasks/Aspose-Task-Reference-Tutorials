---
title: Aspose.Tasks에서 프로젝트 간 작업 링크 생성
linktitle: Aspose.Tasks에서 프로젝트 간 작업 링크 생성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java로 프로젝트 협업을 강화하세요. 프로젝트 간 작업 링크를 단계별로 생성하는 방법을 알아보세요. 지금 효율성을 높이세요!
weight: 10
url: /ko/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 프로젝트 간 작업 링크 생성

## 소개
역동적인 프로젝트 관리 세계에서는 효율성과 협업이 무엇보다 중요합니다. Aspose.Tasks for Java는 프로젝트 관리 기능을 향상시키는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트 간 작업 링크를 생성하는 프로세스를 살펴보겠습니다. 이 단계별 가이드는 다양한 프로젝트 전반에 걸쳐 작업을 원활하게 연결하고 향상된 조정과 간소화된 작업 흐름을 촉진하는 기술을 갖추게 해줍니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 실무 지식.
-  Aspose.Tasks for Java가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Tasks for Java 릴리스 페이지](https://releases.aspose.com/tasks/java/).
- 프로젝트 관리 및 작업 종속성에 대한 기본적인 이해.
## 패키지 가져오기
프로세스를 시작하기 위해 Java 환경에 필요한 패키지를 가져옵니다. 이렇게 하면 Java 기능용 Aspose.Tasks에 액세스할 수 있습니다. 다음 코드 조각을 사용하세요.
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
이제 위의 코드를 이해하기 쉬운 단계로 나누어 보겠습니다.
## 1단계: 환경 설정
코드를 살펴보기 전에 Java가 설치되어 있고 Aspose.Tasks for Java 라이브러리가 프로젝트에 올바르게 추가되었는지 확인하세요.
## 2단계: 프로젝트 인스턴스 생성
Aspose.Tasks 라이브러리를 사용하여 새 프로젝트를 초기화합니다.
```java
Project project = new Project();
```
## 3단계: 요약 작업 추가
연결된 작업을 구성하고 관리하는 요약 작업을 만듭니다.
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## 4단계: 외부 작업 추가
다른 프로젝트의 작업에 대한 링크를 생성하려면 요약 작업에 외부 작업을 추가하세요.
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## 5단계: 로컬 작업 추가
요약 작업에 로컬 작업을 추가합니다. 이는 외부 작업에 연결된 작업이 됩니다.
```java
Task t = summary.getChildren().add("Task");
```
## 6단계: 작업 링크 생성
외부 작업과 로컬 작업 간의 작업 링크를 설정합니다.
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## 7단계: 결과 표시
마지막으로 변환 결과를 표시합니다.
```java
System.out.println("Process completed Successfully");
```
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 프로젝트 간 작업 링크를 생성하는 방법을 성공적으로 배웠습니다. 이 기능은 프로젝트 관리의 협업과 조정을 향상시켜 다양한 프로젝트의 작업 간의 원활한 통합을 보장합니다.
## 자주 묻는 질문
### 동일한 요약 작업에서 여러 외부 프로젝트의 작업을 연결할 수 있나요?
예, 유사한 프로세스에 따라 동일한 요약 작업 내에서 다양한 외부 프로젝트의 작업을 연결할 수 있습니다.
### 연결된 프로젝트의 외부 작업이 수정되면 어떻게 되나요?
외부 작업에 대한 모든 수정 사항은 현재 프로젝트의 연결된 작업에 반영됩니다.
### 서로 다른 파일 형식의 작업 간에 링크를 만드는 것이 가능합니까?
예, Aspose.Tasks for Java는 다양한 파일 형식의 프로젝트 간 작업 연결을 지원합니다.
### 프로젝트 간에 연결된 작업을 연결 해제할 수 있나요?
예, 적절한 Aspose.Tasks 메서드를 사용하여 작업 링크를 제거하면 작업 링크를 해제할 수 있습니다.
### 프로젝트 간에 연결할 수 있는 작업 수에 제한이 있나요?
연결할 수 있는 작업 수는 Aspose.Tasks 라이선스의 기능과 제한 사항에 따라 달라집니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
