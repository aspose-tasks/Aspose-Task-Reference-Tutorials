---
title: Aspose.Tasks의 할당 예산 관리
linktitle: Aspose.Tasks의 할당 예산 관리
second_title: Aspose.Tasks 자바 API
description: Microsoft Project 파일 조작을 위한 강력한 라이브러리인 Aspose.Tasks를 사용하여 Java에서 과제 예산을 효율적으로 관리하는 방법을 알아보세요.
type: docs
weight: 11
url: /ko/java/resource-assignments/assignment-budget/
---
## 소개
Aspose.Tasks for Java는 개발자에게 Java 애플리케이션에서 Microsoft Project 파일을 효율적으로 관리하고 조작하는 데 필요한 도구를 제공하는 강력한 라이브러리입니다. 프로젝트 관리 도구를 구축하든, 작업을 자동화하든, 아니면 단순히 프로그래밍 방식으로 프로젝트 파일과 상호 작용해야 하든 Aspose.Tasks는 포괄적인 기능과 직관적인 API를 통해 프로세스를 단순화합니다.
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 할당 예산 관리의 세계를 살펴보겠습니다. 필요한 패키지를 가져오는 것부터 각 예제를 단계별 가이드로 분류하는 것까지 모든 것을 다룰 것입니다. 결국에는 Java 프로젝트에서 할당 예산을 처리하는 방법을 확실하게 이해하게 됩니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 자바 개발 환경
 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. 최신 버전을 다운로드하여 설치할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks for Java
 다음에 제공된 지침에 따라 Java용 Aspose.Tasks를 다운로드하고 설정합니다.[선적 서류 비치](https://reference.aspose.com/tasks/java/) 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose.Tasks 웹사이트](https://releases.aspose.com/tasks/java/).
### 통합 개발 환경(IDE)
Java 개발을 위해 선호하는 IDE를 선택하세요. 널리 사용되는 옵션으로는 Eclipse, IntelliJ IDEA 및 NetBeans가 있습니다.
## 패키지 가져오기
Aspose.Tasks for Java에서 할당 예산 관리를 시작하려면 필요한 패키지를 프로젝트로 가져옵니다.
## 1단계: Aspose.Tasks 종속성 추가
 Maven을 사용하는 경우 다음 종속성을 추가하십시오.`pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>{latest_version}</version>
</dependency>
```
 바꾸다`{latest_version}` Java용 Aspose.Tasks의 최신 버전을 사용하세요.
## 2단계: 클래스 가져오기
Java 파일에서 필수 클래스를 가져옵니다.
```java
import com.aspose.tasks.*;
```

## 1단계: 데이터 디렉터리 정의
프로젝트 파일이 포함된 디렉터리로 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 데이터 디렉터리의 실제 경로를 사용합니다.
## 2단계: 프로젝트 파일 로드
 인스턴스화`Project` 개체를 만들고 프로젝트 파일을 로드합니다.
```java
Project prj = new Project(dataDir + "project.mpp");
```
 바꾸다`"project.mpp"` 프로젝트 파일 이름으로.
## 3단계: 자원 할당 반복
프로젝트의 각 자원 할당을 반복합니다.
```java
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
## 4단계: 예산 비용 검색
각 자원 할당에 대한 예산 비용을 검색하고 인쇄합니다.
```java
System.out.println(ra.get(Asn.BUDGET_COST));
```
## 5단계: 예산 작업 검색
각 자원 할당에 대한 예산 작업을 검색하고 인쇄합니다.
```java
System.out.println(ra.get(Asn.BUDGET_WORK).toString());
```
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java에서 할당 예산을 관리하는 방법을 살펴보았습니다. 위에 설명된 단계를 따르면 Java 프로젝트에서 예산 관련 작업을 효율적으로 쉽게 처리할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java는 모든 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks for Java는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: Aspose.Tasks for Java를 사용하여 프로그래밍 방식으로 할당 예산을 수정할 수 있나요?
답: 물론이죠! Aspose.Tasks는 Java 애플리케이션 내에서 필요에 따라 할당 예산을 조작할 수 있는 강력한 API를 제공합니다.
### Q: Aspose.Tasks for Java는 문서와 지원을 제공합니까?
 A: 네, 다음을 참고하시면 됩니다.[선적 서류 비치](https://reference.aspose.com/tasks/java/) 포괄적인 가이드를 확인하고 Aspose.Tasks 커뮤니티 포럼에서 도움을 구하세요.[여기](https://forum.aspose.com/c/tasks/15).
### Q: 구매하기 전에 Java용 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 예, 무료 평가판을 통해 Aspose.Tasks for Java의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java 라이선스는 어디서 구매할 수 있나요?
 A: 구매 페이지에서 Aspose.Tasks for Java 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).