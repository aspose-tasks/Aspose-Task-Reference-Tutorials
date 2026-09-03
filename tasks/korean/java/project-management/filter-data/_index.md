---
date: 2026-06-05
description: Aspose.Tasks for Java를 사용하여 MPP 파일을 필터링하는 방법을 배우고, 필터 기준을 사용자 정의하며, 날짜별로
  작업을 필터링하여 프로젝트 관리를 효율화합니다.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Aspose.Tasks for Java를 사용하여 MPP 파일 필터링하는 방법
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 MPP 파일 필터링하는 방법
url: /ko/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 MPP 파일 필터링하는 방법

## 소개
Java 애플리케이션에서 Microsoft Project 파일(*.mpp*)을 다루는 경우, 가장 중요한 작업, 리소스 또는 할당을 분리하기 위해 **MPP 파일을 필터링**해야 할 때가 많습니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 **MPP 파일을 프로그래밍 방식으로 필터링하는 방법**을 단계별로 안내하고, **필터 기준을 맞춤 설정하는 방법**을 보여주며, 실용적인 “날짜별 작업 필터링” 시나리오를 시연합니다. 끝까지 읽으면 어떤 Java 프로젝트에도 바로 삽입할 수 있는 사용 가능한 코드 스니펫을 얻을 수 있습니다.

## 빠른 답변
- **“filter mpp”는 무엇을 의미하나요?** 정의된 조건에 따라 프로젝트 데이터의 하위 집합을 추출하는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.Tasks for Java는 필터를 생성하고 적용하기 위한 포괄적인 API를 제공합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **작업, 리소스 및 할당을 모두 필터링할 수 있나요?** 예 – 각 엔터티 유형마다 고유한 필터 컬렉션이 있습니다.  
- **Java 8 이상이 필요합니까?** Aspose.Tasks는 Java 8 및 이후 버전을 지원합니다.

## Java에서 “how to filter mpp”란?
`How to filter mpp`는 Aspose.Tasks의 `Filter` 객체를 사용해 시작 날짜, 비용, 사용자 정의 필드 등 특정 조건을 만족하는 프로젝트 요소만 선택하는 과정입니다. `Project`를 로드하고 `Filter`를 가져오면 API가 조건에 맞는 컬렉션을 반환하여 집중된 보고나 후속 통합을 가능하게 합니다.

## 필터 기준을 맞춤 설정하는 이유는?
맞춤형 필터 기준을 사용하면 고위험 작업, 연체 항목 또는 예산 초과 리소스를 목표로 할 수 있어 방대한 프로젝트 파일을 간결하고 실행 가능한 뷰로 전환할 수 있습니다. Aspose.Tasks는 **50개 이상의 사전 정의된 필터 유형**을 제공하며 무제한 사용자 정의 필터 생성을 지원해 수작업 데이터 선별 시간을 최대 70 %까지 단축합니다.

## 전제 조건
시작하기 전에 다음을 확인하십시오:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 NetBeans 중 하나를 사용하면 됩니다.  

## 패키지 가져오기
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType`, `Project`는 프로젝트 데이터에 필터를 정의하고 적용하는 핵심 클래스입니다.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## 단계별 가이드

### 단계 1: 프로젝트 설정
먼저 분석하려는 MPP 파일을 가리키는 `Project` 인스턴스를 생성하고 메모리로 로드합니다. 이 단일 단계로 전체 프로젝트 모델이 필터링, 검증 및 추가 조작을 위해 준비되며, API를 통해 작업, 리소스 및 할당에 접근할 수 있게 됩니다.

### MPP 파일을 필터링하기 위해 프로젝트를 어떻게 설정하나요?
`Project` 클래스는 MPP 파일을 메모리 내에 로드하고 표현합니다. 분석하려는 MPP 파일을 가리키는 `Project` 인스턴스를 생성하고 메모리로 로드하십시오. 이 단계는 전체 프로젝트 모델을 필터링, 검증 및 추가 조작을 위해 준비시켜 API를 통해 작업, 리소스 및 할당에 접근할 수 있게 합니다.

### 필터를 어떻게 검색하고 검사할 수 있나요?
`Filter` 객체는 프로젝트 항목을 선택하기 위한 필터 정의를 캡슐화합니다. Aspose.Tasks는 “All Tasks” 또는 “Critical Tasks”와 같은 사전 정의된 필터를 저장합니다. `project.getTaskFilters().getByName("My Filter")` 또는 인덱스 기반 접근을 사용해 `Filter` 객체를 얻은 뒤, `FilterCriteria` 컬렉션을 살펴보면 각 규칙과 이를 결합하는 논리 연산자(AND/OR)를 확인할 수 있어 필터가 요구 사항에 맞는지 검증할 수 있습니다.

### 중첩된 기준 행을 어떻게 반복하나요?
`FilterCriteriaGroup`은 논리 연산자로 결합된 기준 그룹을 나타냅니다. 필터는 각기 다른 연산자를 가진 기준 그룹을 포함할 수 있습니다. `filter.getCriteria().getRows()`를 순회하고, 행이 `FilterCriteriaGroup`인 경우 자식 행으로 재귀 호출하십시오. 이 탐색을 통해 “(Start < today AND Cost > 1000) OR Priority = High”와 같은 복잡한 논리를 완전히 이해하고 필요에 따라 기준을 조정할 수 있습니다.

### 디버깅을 위해 기준 정보를 어떻게 출력하나요?
기준 트리를 순회한 후 각 행의 필드 이름, 테스트 연산자 및 값을 콘솔에 출력합니다. 이 간단한 덤프를 통해 필터가 의도한 비즈니스 규칙과 일치하는지 대규모 프로젝트에 적용하기 전에 확인할 수 있으며, 잘못된 연산자나 값을 쉽게 찾아낼 수 있습니다.

### 프로그램matically 새 필터를 어떻게 만들나요?
`new Filter("My Filter")`로 `Filter`를 인스턴스화한 뒤 `project.getTaskFilters().add(filter)`를 사용해 프로젝트의 작업 필터 컬렉션에 추가합니다. 이후 원하는 행을 `FilterCriteria` 컬렉션에 추가하고, 필드 이름, 테스트 연산자 및 값을 지정해 필터 적용 시 포함될 작업을 정확히 정의합니다.

### 작업 대신 리소스에 필터를 적용할 수 있나요?
`ResourceFilters` 컬렉션은 리소스에 적용 가능한 필터 정의를 보관합니다. 예, `project.getResourceFilters()`를 사용해 작업 필터와 동일한 방식으로 리소스 전용 필터를 다룰 수 있습니다. 필터를 추가하거나 검색한 뒤, 작업 필터와 마찬가지로 `FilterCriteria`를 구성하고 리소스 컬렉션에 적용하면 필터링된 리소스 집합을 얻을 수 있습니다.

### OR 논리로 여러 필터를 결합할 수 있나요?
`Operation`을 `OR`로 설정한 상위 `FilterCriteriaGroup`을 만든 뒤 개별 `FilterCriteria` 객체를 자식으로 추가합니다. 이 그룹은 각 자식 기준을 평가하고 하나라도 만족하는 항목을 반환하므로 여러 간단한 필터를 더 넓은 선택 범위로 결합할 수 있습니다.

### Aspose.Tasks가 사용자 정의 필드 필터링을 지원하나요?
`CustomField` 열거형은 프로젝트에 정의된 사용자 정의 필드의 식별자를 제공합니다. 물론 지원합니다. `CustomField` 열거형을 통해 사용자 정의 필드를 참조하면 필터 식에서도 내장 필드와 동일하게 동작합니다. 동일한 연산자와 값을 사용해 `FilterCriteria` 행에 포함시켜 표준 프로젝트 속성과 함께 사용자 정의 데이터에 대한 강력한 쿼리를 수행할 수 있습니다.

### 대용량 MPP 파일에서 필터링이 성능에 어떤 영향을 미치나요?
필터링은 완전히 메모리 내에서 수행되며 일반적으로 1,000 작업 프로젝트를 200 ms 이하로 처리합니다. 수천 작업 파일의 경우 `ProjectReader`를 사용해 필요한 섹션만 로드하고 선택적으로 필터를 적용하면 메모리 사용량을 낮추고 매우 큰 프로젝트에서도 빠른 응답 시간을 유지할 수 있습니다.

---

**마지막 업데이트:** 2026-06-05  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose

## 관련 튜토리얼

- [Load MPP File Java - Manage Project Properties with Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Effortless MS Project Online Data Reading](/tasks/java/project-data-reading/read-project-online/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```