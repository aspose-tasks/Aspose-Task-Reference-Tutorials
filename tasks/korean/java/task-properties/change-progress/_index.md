---
title: Aspose.Tasks에서 작업 진행 상황 변경
linktitle: Aspose.Tasks에서 작업 진행 상황 변경
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks로 Java 프로젝트 관리를 강화하세요. 이 단계별 튜토리얼에서 작업 진행 상황을 원활하게 수정하는 방법을 알아보세요. 지금 다운로드하세요!
weight: 12
url: /ko/java/task-properties/change-progress/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 진행 상황 변경

## 소개
프로젝트 관리의 동적 영역에서는 효과적인 작업 진행 상황 추적이 매우 중요합니다. Aspose.Tasks for Java는 강력한 기능으로 프로세스를 단순화하는 강력한 솔루션으로 돋보입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업 진행 상황을 변경하는 단계를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. Java 개발 환경: 시스템에 기능적인 Java 개발 환경을 설치하고 설정합니다.
2.  Aspose.Tasks for Java Library: 다음에서 라이브러리를 다운로드하세요.[링크](https://releases.aspose.com/tasks/java/).
3. 문서 디렉터리: 프로젝트 문서를 저장할 디렉터리를 만듭니다.
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하겠습니다. 이 코드 조각은 프로젝트를 초기화하고 진행률이 50%인 작업을 추가합니다.
```java
import com.aspose.tasks.*;

```
## 1단계: 프로젝트 설정
개발 환경에서 새 Java 프로젝트를 생성하는 것부터 시작하세요.
## 2단계: 필요한 패키지 가져오기
 Java 클래스에서 필수 패키지를 가져옵니다.`Project` 그리고`Task`.
## 3단계: 문서 디렉터리 지정
프로젝트 파일을 저장할 문서 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
## 4단계: 새 프로젝트 만들기
 사용`Project` 새로운 프로젝트를 생성하는 클래스입니다.
```java
Project project = new Project(dataDir + "project.mpp");
```
## 5단계: 작업 추가
 활용`Task` 프로젝트에 새 작업을 추가하는 클래스입니다.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
## 6단계: 작업 진행률 설정
 다음을 사용하여 작업 진행 상황을 설정합니다.`set` 방법과`Tsk.PERCENT_COMPLETE` 기인하다.
```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```
### 7단계: 진행 상황 표시
작업 진행 상황을 검색하고 표시합니다.
```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 작업 진행 상황을 성공적으로 변경했습니다.
## 결론
작업 진행 상황 추적을 간소화하는 것은 프로젝트 관리에 매우 중요합니다. Aspose.Tasks for Java는 사용자 친화적인 인터페이스와 강력한 기능을 제공하여 이 프로세스를 단순화합니다. 이 가이드에 설명된 단계를 익히면 프로젝트 관리 능력이 향상됩니다.
## 자주 묻는 질문
### Aspose.Tasks는 모든 Java 개발 환경과 호환됩니까?
설명서의 설치 지침에 따라 호환성을 확인하세요.
### 프로젝트 내 여러 작업의 진행 상황을 추적할 수 있나요?
모니터링하려는 각 작업에 대한 단계를 복제하세요.
### Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 무료 평가판에 액세스하세요[여기](https://releases.aspose.com/).
### Aspose.Tasks for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 포괄적인 문서 살펴보기[여기](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 방문하다[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
