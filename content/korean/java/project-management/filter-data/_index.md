---
title: Aspose.Tasks의 MPP 파일에서 데이터 필터링
linktitle: Aspose.Tasks의 MPP 파일에서 데이터 필터링
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MPP 파일에서 데이터를 필터링하는 방법을 알아보세요. 프로젝트 관리 워크플로를 손쉽게 향상하세요.
type: docs
weight: 14
url: /ko/java/project-management/filter-data/
---
## 소개
Java 개발 영역에서 프로젝트 작업을 효율적으로 관리하는 것은 성공적인 프로젝트 관리의 중추적인 측면입니다. Aspose.Tasks for Java는 프로젝트 관리 작업을 프로그래밍 방식으로 처리하기 위한 강력한 솔루션을 제공하여 개발자에게 MPP 파일의 데이터를 원활하게 필터링하는 데 필요한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 파일에서 데이터를 필터링하는 프로세스를 자세히 살펴보고 각 단계를 세분화하여 포괄적인 이해를 보장합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse, NetBeans 등 선호하는 IDE를 선택하세요.

## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## 1단계: 프로젝트 설정
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```
 이 단계에서는`Project` MPP 파일의 경로를 제공하여 개체를 생성합니다.
## 2단계: 필터 검색
```java
Filter filter = project.getTaskFilters().toList().get(1);
```
 여기서 우리는`Filter` 프로젝트의 개체입니다. 검색하려는 필터의 인덱스를 지정할 수 있습니다.
## 3단계: 필터 기준에 액세스
```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```
이 단계에는 필터의 기준 및 작동에 액세스하는 작업이 포함됩니다.
## 4단계: 기준 세부정보 검색
```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```
여기서는 첫 번째 기준 행의 세부정보를 검색합니다.
## 5단계: 기준 행 반복
```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```
이 단계에는 기준 행을 반복하고 해당 세부정보에 액세스하는 작업이 포함됩니다.
## 6단계: 기준 정보 인쇄
```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```
이 마지막 단계에서는 기준에 대한 정보를 인쇄합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 파일에서 데이터를 필터링하는 방법을 살펴보았습니다. 이러한 단계별 지침을 따르면 프로젝트 데이터를 쉽게 효과적으로 관리하고 조작하여 Java 개발 워크플로우를 향상시킬 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일을 지원하여 프로젝트 관리 작업의 호환성과 유연성을 보장합니다.
### Q: 특정 프로젝트 요구 사항에 따라 필터 기준을 사용자 정의할 수 있습니까?
답: 물론이죠! Aspose.Tasks for Java를 사용하면 프로젝트의 고유한 요구 사항에 따라 필터 기준을 맞춤화하여 대상 데이터 조작 및 분석이 가능합니다.
### Q: Aspose.Tasks for Java는 소규모 프로젝트와 대규모 프로젝트 모두에 적합합니까?
A: 예, 소규모 프로젝트를 관리하든 광범위한 프로젝트 포트폴리오를 처리하든 Aspose.Tasks for Java는 다양한 프로젝트 관리 시나리오에 필요한 확장성과 성능을 제공합니다.
### Q: Aspose.Tasks for Java는 포괄적인 문서와 지원 리소스를 제공합니까?
 답: 물론이죠! 당신은[선적 서류 비치](https://reference.aspose.com/tasks/java/) 자세한 가이드 및 API 참조를 확인하세요. 또한, 발생한 질문이나 문제에 대해 Aspose.Tasks 커뮤니티 포럼에서 도움을 구할 수 있습니다.
### Q: 구매하기 전에 Java용 Aspose.Tasks의 기능을 살펴볼 수 있나요?
 답: 물론이죠! 무료 평가판을 이용하실 수 있습니다.[웹사이트](https://releases.aspose.com/) Aspose.Tasks for Java의 기능을 직접 경험해보세요.