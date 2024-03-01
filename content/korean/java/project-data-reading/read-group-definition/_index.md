---
title: Aspose.Tasks에서 그룹 정의 데이터 읽기
linktitle: Aspose.Tasks에서 그룹 정의 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 그룹 정의 데이터를 읽는 방법을 알아보세요. 단계별 튜토리얼을 따라해보세요.
type: docs
weight: 10
url: /ko/java/project-data-reading/read-group-definition/
---
## 소개
Aspose.Tasks for Java는 개발자가 Microsoft Project 파일을 쉽게 조작할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트 파일에서 그룹 정의 데이터를 읽는 과정을 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같이 선호하는 IDE를 선택하세요.

## 패키지 가져오기
먼저 Aspose.Tasks for Java 작업을 시작하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
```
## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 파일이 포함된 디렉터리의 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
 다음을 사용하여 프로젝트 파일을 로드합니다.`Project` 클래스 생성자, 프로젝트 파일의 경로를 전달합니다.
## 3단계: 작업 그룹 수 검색
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 다음을 사용하여 프로젝트의 작업 그룹 수를 검색합니다.`getTaskGroups()` 방법.
## 4단계: 작업 그룹 정보 검색
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
이름, 그룹 기준 수 등 특정 작업 그룹에 대한 정보를 검색합니다.
## 5단계: 그룹 기준 정보 검색
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
필드, 그룹, 셀 색상, 패턴 등 그룹 기준에 대한 정보를 검색합니다.
## 6단계: 상위 그룹 확인
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
상위 그룹이 작업 그룹과 동일한지 확인하세요.
## 7단계: Criterion의 글꼴 정보 검색
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
글꼴 모음, 크기, 스타일, 정렬 순서 등 기준에 대한 글꼴 정보를 검색합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 그룹 정의 데이터를 읽는 방법을 배웠습니다. 다음 단계를 수행하면 Java 애플리케이션에서 작업 그룹 정보를 효과적으로 추출하고 활용할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java를 사용하여 프로젝트 파일을 수정할 수 있나요?
A: 예, Aspose.Tasks for Java는 프로그래밍 방식으로 Microsoft Project 파일을 읽고 수정하기 위한 광범위한 기능을 제공합니다.
### Q: Aspose.Tasks for Java는 모든 버전의 Microsoft Project 파일과 호환됩니까?
A: Aspose.Tasks for Java는 MPP 및 XML 형식을 포함하여 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: Aspose.Tasks for Java로 작업하는 동안 오류를 어떻게 처리할 수 있나요?
A: try-catch 블록을 사용하여 오류 처리 메커니즘을 구현하면 파일 조작 중에 발생할 수 있는 예외를 정상적으로 처리할 수 있습니다.
### Q: Aspose.Tasks for Java는 프로젝트 데이터를 다른 형식으로 내보내는 기능을 지원합니까?
A: 예, Aspose.Tasks for Java를 사용하면 프로젝트 데이터를 PDF, XLSX 및 CSV와 같은 형식으로 내보낼 수 있습니다.
### Q: Aspose.Tasks for Java에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks for Java 문서](https://reference.aspose.com/tasks/java/) 포괄적인 가이드를 보려면 다음을 참조하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역 사회 지원을 위해.