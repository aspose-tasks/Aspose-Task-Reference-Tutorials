---
title: 초과 근무, 남은 비용을 모니터링하고 Aspose.Tasks에서 작업하세요.
linktitle: 초과 근무, 남은 비용을 모니터링하고 Aspose.Tasks에서 작업하세요.
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 초과 근무, 남은 비용을 모니터링하고 Java 프로젝트에서 작업하는 방법을 알아보세요. 효과적인 프로젝트 관리를 위한 쉬운 단계.
type: docs
weight: 18
url: /ko/java/resource-assignments/overtime-remaining-costs-work/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 초과 근무, 남은 비용 및 프로젝트 작업을 모니터링하는 방법을 알아봅니다. 이는 프로젝트 관리자와 팀 리더가 프로젝트를 예산 범위 내에서 순조롭게 진행하는지 확인하는 데 매우 중요할 수 있습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): Java용 Aspose.Tasks에는 Java SE 6 이상이 필요합니다.
2.  Aspose.Tasks for Java Library: 다음에서 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): Eclipse, IntelliJ IDEA 또는 NetBeans와 같은 모든 Java IDE.

## 패키지 가져오기
Java 파일에서 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 1단계: 데이터 디렉터리 설정
프로젝트 파일이 있는 디렉터리를 정의합니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 파일의 경로로.
## 2단계: 프로젝트 로드
 인스턴스화`Project` 개체를 만들고 프로젝트 파일을 로드합니다.
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 바꾸다`"ResourceAssignmentOvertimes.mpp"` 프로젝트 파일 이름으로.
## 3단계: 자원 할당 반복
프로젝트의 각 자원 할당을 반복합니다.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## 4단계: 초과 근무 비용 및 작업 인쇄
각 자원 할당에 대한 초과 근무 비용과 작업을 검색하고 인쇄합니다.
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## 5단계: 남은 비용 및 작업 인쇄
각 자원 할당에 대해 남은 비용과 작업을 검색하고 인쇄합니다.
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## 6단계: 남은 초과 근무 비용 및 작업량 인쇄
남은 초과 근무 비용과 각 자원 할당에 대한 작업을 검색하고 인쇄합니다.
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## 결론
초과 근무, 남은 비용, 프로젝트 작업을 모니터링하는 것은 성공적인 프로젝트 관리에 매우 중요합니다. Aspose.Tasks for Java를 사용하면 이 정보에 쉽게 액세스하고 추적하여 프로젝트가 일정과 예산 범위 내에서 유지되도록 할 수 있습니다.
## FAQ
### 다른 Java 라이브러리와 함께 Java용 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks for Java는 다른 Java 라이브러리 및 프레임워크와 호환됩니다.
### Aspose.Tasks는 다양한 프로젝트 파일 형식을 지원합니까?
예, Aspose.Tasks는 MPP, XML 등을 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### 평가판을 사용할 수 있나요?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### 문제가 발생하면 어디서 지원을 받을 수 있나요?
 Aspose.Tasks 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15) 지원을 위해.
### Aspose.Tasks 라이선스를 어떻게 구매할 수 있나요?
 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).