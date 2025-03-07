---
title: Aspose.Tasks를 사용한 MS 프로젝트 자원 백분율 계산
linktitle: Aspose.Tasks에서 리소스에 대한 백분율 계산 수행
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS Project 리소스 비율을 계산하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
weight: 14
url: /ko/java/resource-management/percentage-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 MS 프로젝트 자원 백분율 계산

## 소개
Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스에 대한 백분율 계산을 수행하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 Aspose.Tasks를 활용하여 Microsoft Project 파일에서 리소스 데이터를 효율적으로 조작하고 추출하는 프로세스를 자세히 살펴보겠습니다. Aspose.Tasks는 Microsoft Project 문서 작업을 위한 포괄적인 기능을 제공하는 강력한 Java API로, 개발자가 프로젝트 관리 기능을 Java 애플리케이션에 원활하게 통합할 수 있도록 해줍니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### 자바 개발 환경
 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. 다음에서 JDK를 다운로드하고 설치할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks 라이브러리
Aspose.Tasks 라이브러리를 Java 프로젝트에 통합해야 합니다. 아직 다운로드하지 않았다면 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/) 설명서에 제공된 설치 지침을 따르십시오.[여기](https://reference.aspose.com/tasks/java/).

## 패키지 가져오기
코딩을 시작하기 전에 이 튜토리얼에 필요한 필수 패키지를 가져와 보겠습니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## 1단계: 프로젝트 파일 경로 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` Microsoft Project 파일의 경로를 사용하세요.
## 2단계: 프로젝트 로드
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
이 코드는 지정된 데이터 디렉터리에 있는 "Software Development.mpp"라는 Microsoft Project 파일을 로드합니다.
## 3단계: 리소스 반복
```java
for (Resource res : prj.getResources()) {
```
프로젝트의 각 리소스를 반복합니다.
## 4단계: 자원 이름 및 작업 완료율 확인
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
자원 이름이 null이 아닌지 확인한 다음 각 자원에 대해 완료된 작업 비율을 인쇄합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 활용하여 MS 프로젝트 리소스에 대한 백분율 계산을 효율적으로 수행하는 방법을 배웠습니다. 이러한 단계를 수행하면 프로젝트 관리 기능을 Java 애플리케이션에 원활하게 통합하여 프로젝트 리소스 활용에 대한 향상된 제어 및 통찰력을 제공할 수 있습니다.
## FAQ
### 다른 Java 프레임워크와 함께 Java용 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks for Java는 Spring, Hibernate 등과 같은 다양한 Java 프레임워크와 호환됩니다.
### Aspose.Tasks는 모든 버전의 Microsoft Project 파일을 지원합니까?
Aspose.Tasks는 MPP, MPT, XML 등을 포함한 모든 버전의 Microsoft Project 파일을 지원합니다.
### Aspose.Tasks를 사용하여 프로젝트 일정을 조작할 수 있나요?
물론 Aspose.Tasks는 작업, 리소스, 달력 등을 포함하여 프로젝트 일정을 조작하기 위한 포괄적인 기능을 제공합니다.
### Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 예, Aspose.Tasks 커뮤니티 포럼에서 도움을 찾고 다른 사용자와 교류할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks는 평가 목적으로 임시 라이선스를 제공합니까?
 예, 다음에서 평가용 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
