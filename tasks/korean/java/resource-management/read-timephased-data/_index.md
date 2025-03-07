---
title: Aspose.Tasks에서 리소스에 대한 시간대별 데이터 읽기
linktitle: Aspose.Tasks에서 리소스에 대한 시간대별 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스에서 시간대별 데이터를 추출하는 방법을 알아보세요. 단계별 튜토리얼.
weight: 15
url: /ko/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 리소스에 대한 시간대별 데이터 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스에 대한 시간대별 데이터를 읽는 프로세스를 안내합니다. 이 라이브러리는 Microsoft Project 파일을 프로그래밍 방식으로 관리하기 위한 강력한 기능을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 설치 지침을 따르십시오.
2.  Java 라이브러리용 Aspose.Tasks: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/) 설명서에 제공된 설치 지침을 따르세요.

## 패키지 가져오기
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## 1단계: 데이터 디렉터리 설정
먼저 MS 프로젝트 파일이 있는 디렉터리를 정의합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: MS 프로젝트 템플릿 파일 읽기
MS 프로젝트 템플릿 파일의 이름을 지정합니다.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## 3단계: 입력 파일을 프로젝트로 읽기
Aspose.Tasks를 사용하여 입력 파일을 읽고 프로젝트 개체로 로드합니다.
```java
Project project = new Project(dataDir + fileName);
```
## 4단계: ID로 리소스 가져오기
고유 식별자(ID)로 프로젝트에서 원하는 리소스를 검색합니다.
```java
Resource resource = project.getResources().getByUid(1);
```
## 5단계: 자원 작업을 위한 시간대별 데이터 인쇄
자원 작업에 대한 시간대별 데이터를 인쇄합니다.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## 6단계: 자원 비용에 대한 시간대별 데이터 인쇄
자원 비용에 대한 시간대별 데이터를 인쇄합니다.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스에 대한 시간대별 데이터를 읽는 방법을 배웠습니다. 다음 단계를 수행하면 프로그래밍 방식으로 프로젝트 파일에서 중요한 정보를 효율적으로 추출할 수 있습니다.
## FAQ
### Aspose.Tasks는 Microsoft Project 외에 다른 유형의 프로젝트 파일을 처리할 수 있나요?
예, Aspose.Tasks는 MPP, XML, CSV를 포함한 다양한 파일 형식을 지원합니다.
### Aspose.Tasks는 다른 Java 개발 환경과 호환됩니까?
예, Aspose.Tasks는 모든 주요 Java IDE 및 프레임워크와 호환됩니다.
### Aspose.Tasks를 사용하여 프로젝트 데이터를 조작할 수 있나요?
물론 Aspose.Tasks는 프로젝트 데이터를 생성, 수정 및 분석하기 위한 광범위한 API를 제공합니다.
### Aspose.Tasks는 엔터프라이즈급 프로젝트에 적합합니까?
예, Aspose.Tasks는 안정성과 확장성으로 인해 기업 환경에서 널리 사용됩니다.
### Aspose.Tasks를 사용하는 동안 문제가 발생하면 어디서 지원을 받을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티와 지원팀의 도움을 받으세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
