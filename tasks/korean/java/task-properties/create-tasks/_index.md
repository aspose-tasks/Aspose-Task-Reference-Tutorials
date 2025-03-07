---
title: Aspose.Tasks에서 작업 생성
linktitle: Aspose.Tasks에서 작업 생성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java 프로젝트를 손쉽게 관리하세요. 작업, 하위 작업 등을 만듭니다. 원활한 프로젝트 관리를 위한 단계별 가이드를 따르세요.
weight: 13
url: /ko/java/task-properties/create-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 생성

## 소개
Aspose.Tasks for Java의 세계에 오신 것을 환영합니다! Java 애플리케이션에서 작업과 프로젝트를 효율적으로 관리하려는 경우 올바른 위치에 있습니다. 이 종합 가이드에서는 Aspose.Tasks for Java를 사용하여 작업을 생성하는 과정을 안내하고 원활한 경험을 보장하기 위해 각 단계를 세분화합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요.
-  Java 라이브러리용 Aspose.Tasks: 다음에서 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
- 통합 개발 환경(IDE): Eclipse 또는 IntelliJ와 같은 Java 친화적인 IDE를 사용합니다.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks 작업을 시작하는 데 필요한 패키지를 가져옵니다. Java 파일 상단에 다음 줄을 추가합니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
## 1단계: 문서 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2단계: 새 프로젝트 만들기
```java
// 새 프로젝트 만들기
Project project = new Project(dataDir + "project.mpp");
```
## 3단계: 요약 작업 추가
```java
// 요약 작업 추가
Task task = project.getRootTask().getChildren().add("Summary1");
```
## 4단계: 하위 작업 추가
```java
// 요약 작업 아래에 하위 작업 추가
Task subtask = task.getChildren().add("Subtask1");
```
프로젝트에 필요한 만큼 작업과 하위 작업을 계속 추가하세요. 각 단계는 구조화된 프로젝트 계층 구조를 구축하는 데 기여합니다.
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 작업을 생성하고 프로젝트를 관리하는 방법을 성공적으로 배웠습니다. Aspose.Tasks의 유연성과 단순성은 Java 개발자를 위한 강력한 도구입니다.
## 자주 묻는 질문
### Aspose.Tasks는 소규모 프로젝트에 적합합니까?
전적으로! Aspose.Tasks는 다목적이며 모든 규모의 프로젝트에 사용할 수 있습니다.
### Aspose.Tasks for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 문서를 참조하세요[여기](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks에 대한 임시 라이선스는 어떻게 얻나요?
 방문하다[이 링크](https://purchase.aspose.com/temporary-license/)임시 라이센스를 위해.
### Aspose.Tasks를 사용하여 작업 속성을 사용자 정의할 수 있나요?
예, 프로젝트 요구 사항에 맞게 작업 속성을 광범위하게 사용자 정의할 수 있습니다.
### Aspose.Tasks 사용자를 위한 지원 커뮤니티가 있나요?
 전적으로! Aspose.Tasks 커뮤니티에 가입하세요[지원 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
