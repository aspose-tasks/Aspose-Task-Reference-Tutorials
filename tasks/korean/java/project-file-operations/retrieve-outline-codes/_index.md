---
title: Aspose.Tasks에서 MS 프로젝트 개요 코드 검색
linktitle: Aspose.Tasks에서 개요 코드 검색
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 프로그래밍 방식으로 Microsoft Project 개요 코드를 검색하는 방법을 알아보세요. 프로젝트 관리 역량을 강화하세요.
type: docs
weight: 15
url: /ko/java/project-file-operations/retrieve-outline-codes/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 개요 코드를 검색하는 방법을 알아봅니다. MS Project의 개요 코드는 프로젝트 작업, 자원 및 할당을 분류하고 구성하는 구조화된 방법을 제공합니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작하고 관리할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### 1. 자바 개발 환경
시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 JDK를 다운로드하여 설치할 수 있습니다.
### 2. Aspose.Tasks 라이브러리
 Aspose.Tasks 라이브러리를 다운로드하여 Java 프로젝트에 포함하세요. 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
먼저 Java 코드의 Aspose.Tasks에서 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 로드
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 이 단계에서는 Microsoft Project 파일을`Project` 제공된 파일 이름을 사용하는 개체입니다.
## 2단계: 개요 코드 검색
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
프로젝트의 각 개요 코드 정의를 반복합니다.
## 3단계: 개요 코드 속성에 액세스
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
별칭, 필드 ID 및 필드 이름과 같은 개요 코드 정의의 다양한 속성을 검색하고 인쇄합니다.
## 4단계: Enterprise 사용자 정의 코드 확인
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
개요 코드가 기업 맞춤형 코드인지 확인하고 그에 따라 결과를 인쇄합니다.
## 5단계: 개요 코드 마스크 표시
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
개요 코드와 연관된 각 마스크를 반복하고 해당 레벨과 마스크 값을 인쇄합니다.
## 6단계: 개요 코드 값 표시
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
각 개요 코드 값을 반복하고 해당 설명, 값 ID, 값 및 유형을 인쇄합니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 개요 코드를 검색하는 방법을 배웠습니다. 제공된 단계를 따르면 Java 애플리케이션의 개요 코드에 효과적으로 액세스하고 조작하여 고급 프로젝트 관리 기능을 사용할 수 있습니다.
## FAQ
### Q1: Aspose.Tasks for Java를 사용하여 프로젝트 파일의 개요 코드를 수정할 수 있습니까?
A: 예, Aspose.Tasks for Java는 프로그래밍 방식으로 MS 프로젝트 파일의 개요 코드를 수정하는 API를 제공합니다.
### Q2: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음 사이트에서 Aspose.Tasks for Java의 무료 평가판을 다운로드할 수 있습니다.[Aspose.Tasks 웹사이트](https://releases.aspose.com/).
### Q3: Aspose.Tasks for Java에 대한 기술 지원은 어떻게 받을 수 있나요?
 A: 다음을 방문하여 기술 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 거기에 쿼리를 게시하세요.
### Q4: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
 A: 예. Aspose.Tasks for Java의 임시 라이선스를 다음 사이트에서 구매할 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/).
### Q5: Aspose.Tasks for Java에 대한 전체 문서는 어디에서 찾을 수 있나요?
 A: 다음을 참조할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/tasks/java/) Aspose.Tasks for Java 사용에 대한 자세한 내용은