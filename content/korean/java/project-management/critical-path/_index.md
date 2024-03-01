---
title: Aspose.Tasks에서 중요한 MS 프로젝트 경로 계산
linktitle: Aspose.Tasks 프로젝트에서 중요 경로 계산
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 주요 경로를 계산하는 방법을 알아보세요. 이는 효율적인 프로젝트 관리를 위한 단계별 지침을 제공합니다.
type: docs
weight: 10
url: /ko/java/project-management/critical-path/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 주요 경로를 계산하는 과정을 안내합니다. 주요 경로는 프로젝트의 전체 일정이 지연되지 않도록 제 시간에 완료해야 하는 작업 순서를 식별하는 데 도움이 되므로 프로젝트 관리에 필수적입니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 라이브러리용 Aspose.Tasks가 다운로드되어 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
시작하려면 Java 클래스에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
```
## 1단계: 데이터 디렉터리 설정
MS 프로젝트 파일이 있는 데이터 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: MS 프로젝트 파일 로드
Aspose.Tasks 라이브러리를 사용하여 MS 프로젝트 파일을 로드합니다.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3단계: 계산 모드 설정
임계 경로 계산을 활성화하려면 계산 모드를 자동으로 설정하십시오.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## 4단계: 작업 추가
프로젝트에 작업을 추가하세요. 이 예에서는 세 개의 하위 작업을 추가합니다.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## 5단계: 작업 링크 생성
작업 링크를 생성하여 작업 간 종속성을 정의합니다.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## 6단계: 중요 경로 표시
프로젝트의 주요 경로를 검색하고 표시합니다.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## 7단계: 결과 표시
프로세스가 성공적으로 완료되었음을 나타내는 메시지를 표시합니다.
```java
System.out.println("Process completed Successfully");
```

## 결론
Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 주요 경로를 계산하는 것은 효과적인 프로젝트 관리에 매우 중요합니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 타임라인에 중요한 작업 순서를 정확하게 식별할 수 있습니다.
## FAQ
### Q: 모든 버전의 MS 프로젝트 파일에서 Aspose.Tasks for Java를 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 MS Project 2003부터 MS Project 2019까지 .mpp 파일을 포함하여 다양한 버전의 MS Project 파일을 지원합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 A: 다음에서 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
 A: 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Java용 Aspose.Tasks를 어떻게 구입할 수 있나요?
 A: 웹사이트에서 Java용 Aspose.Tasks를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).