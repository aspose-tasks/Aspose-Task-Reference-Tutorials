---
title: Aspose.Tasks에서 MS 프로젝트 작업 기준선 생성
linktitle: Aspose.Tasks에서 작업 기준선 생성
second_title: Aspose.Tasks 자바 API
description: 프로젝트 데이터를 손쉽게 관리하기 위한 강력한 라이브러리인 Aspose.Tasks를 사용하여 Java에서 Microsoft Project 작업 기준선을 생성하는 방법을 알아보세요.
type: docs
weight: 11
url: /ko/java/task-baselines/create-task-baseline/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 작업 기준선을 생성하는 프로세스를 자세히 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있도록 하는 강력한 Java 라이브러리입니다. Aspose.Tasks를 사용하면 작업, 리소스, 달력을 포함한 프로젝트 데이터를 손쉽게 조작하여 프로젝트 관리 작업을 간소화할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): Java용 Aspose.Tasks를 사용하려면 시스템에 JDK가 설치되어 있어야 합니다. Oracle 웹사이트에서 JDK를 다운로드하여 설치할 수 있습니다.
2.  Java 라이브러리용 Aspose.Tasks: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/) 제공됩니다.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks 작업을 시작하려면 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 1단계: 프로젝트 객체 생성
```java
Project project = new Project();
```
 먼저 새 항목을 만듭니다.`Project` 물체. 이 개체는 작업할 Microsoft Project 파일을 나타냅니다.
## 2단계: 프로젝트에 작업 추가
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 사용하여`getRootTask()` 메서드를 사용하여 프로젝트의 루트 작업에 액세스한 다음 새 작업을 추가합니다.`add()` 방법. 괄호 안에 작업 이름을 입력하세요.
## 3단계: 지정된 작업에 대한 기준 설정
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
특정 작업에 대한 기준을 설정하려면 작업 목록(`myList` 이 경우) 기준을 설정하려는 작업으로 채웁니다. 그런 다음`setBaseline()` 기준 유형과 작업 목록을 지정하는 방법입니다.
## 4단계: 전체 프로젝트에 대한 기준선 설정
```java
project.setBaseline(BaselineType.Baseline);
```
 또는 간단히 호출하여 전체 프로젝트에 대한 기준선을 설정할 수 있습니다.`setBaseline()` 기준선 유형이 지정된 메서드입니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 작업 기준선을 생성하는 방법을 살펴보았습니다. 위에 설명된 단계를 따르면 프로젝트 데이터를 효율적으로 관리하고 프로젝트 관리 작업을 쉽게 간소화할 수 있습니다.
## FAQ
### Microsoft Project를 설치하지 않고도 Java용 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks for Java를 사용하면 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있습니다.
### Aspose.Tasks for Java는 다른 버전의 Microsoft Project와 호환됩니까?
예, Aspose.Tasks for Java는 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Aspose.Tasks for Java를 사용하여 프로젝트 리소스를 조작할 수 있나요?
물론, Aspose.Tasks for Java는 필요에 따라 리소스를 추가, 업데이트, 제거하는 등 프로젝트 리소스를 조작하기 위한 강력한 기능을 제공합니다.
### Java용 Aspose.Tasks는 작업 종속성 설정을 지원합니까?
예, Aspose.Tasks for Java를 사용하면 작업 종속성을 쉽게 설정할 수 있으므로 프로젝트 내에서 작업 순서를 설정할 수 있습니다.
### Aspose.Tasks for Java에 대한 기술 지원이 제공됩니까?
 예, 다음을 통해 Aspose.Tasks for Java에 대한 기술 지원에 액세스할 수 있습니다.[지원 포럼](https://forum.aspose.com/c/tasks/15), 커뮤니티 및 Aspose 지원 직원에게 질문하고 도움을 구할 수 있습니다.