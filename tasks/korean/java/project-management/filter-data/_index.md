---
date: 2025-12-25
description: Aspose.Tasks for Java를 사용하여 MPP 파일을 필터링하는 방법을 배우고, 필터 기준을 맞춤 설정하여 프로젝트
  관리 워크플로를 효율화하세요.
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
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
Java 애플리케이션에서 Microsoft Project 파일(.mpp)을 다룰 때, 실제로 중요한 데이터에 집중하기 위해 **작업, 리소스 또는 할당**을 **필터링**해야 하는 경우가 많습니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 **MPP 파일을 프로그래밍 방식으로 필터링하는 방법**을 단계별로 살펴보고, **프로젝트별 보고 요구에 맞게 필터 기준을 커스터마이징**하는 방법을 보여드립니다. 끝까지 따라오시면 자체 코드베이스에 바로 적용할 수 있는 명확한 예제를 얻으실 수 있습니다.

## 빠른 답변
- **“filter mpp”가 의미하는 것은?** 정의된 조건에 따라 프로젝트 데이터의 일부 집합을 추출하는 것을 말합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.Tasks for Java가 풍부한 API를 제공하여 필터를 생성하고 적용할 수 있습니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하고, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **작업, 리소스, 할당 모두 필터링할 수 있나요?** 예 – 각 엔터티 유형마다 자체 필터 컬렉션이 있습니다.  
- **Java 8 이상이 필요합니까?** Aspose.Tasks는 Java 8 및 이후 버전을 지원합니다.

## Java에서 “how to filter mpp”란?
MPP 파일을 필터링한다는 것은 Aspose.Tasks API를 사용해 기준(예: 작업 시작 날짜, 비용, 사용자 정의 필드 등)을 정의하고, 해당 규칙을 만족하는 항목만을 가져오는 것을 의미합니다. 이를 통해 집중된 보고서를 생성하고, 상태 검사를 자동화하거나 프로젝트 데이터를 다른 시스템과 연계할 수 있습니다.

## 필터 기준을 커스터마이징해야 하는 이유
프로젝트마다 우선순위가 다릅니다. **필터 기준을 커스터마이징**하면 위험도가 높은 작업, 마감이 지난 항목, 예산을 초과한 리소스 등을 별도로 추출할 수 있어 대시보드가 보다 실용적이 되고, 코드 재사용성도 높아집니다.

## 사전 준비
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – [다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 NetBeans 중 하나.

## 패키지 가져오기
필요한 클래스를 Java 프로젝트에 import합니다:

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
먼저, 작업하려는 MPP 파일을 가리키는 `Project` 인스턴스를 생성합니다.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### 단계 2: 필터 가져오기
Aspose.Tasks는 미리 정의된 필터(예: “All Tasks”, “Critical Tasks”)를 저장합니다. 인덱스나 이름으로 원하는 필터를 가져오세요.

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **팁:** 이름으로 필터를 지정하려면 `project.getTaskFilters().getByName("My Custom Filter")`를 사용하세요.

### 단계 3: 필터 기준 접근
`Filter` 객체를 얻었으면, 해당 기준 행과 이를 결합하는 논리 연산자(AND/OR)를 확인할 수 있습니다.

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### 단계 4: 기준 상세 정보 가져오기
각 기준 행에는 테스트 유형(예: “Equals”, “GreaterThan”)과 적용 대상 필드(예: “Start”, “Cost”)가 포함됩니다.

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### 단계 5: 기준 행 반복 처리
복잡한 필터는 중첩된 기준을 가질 수 있습니다. 여기서는 두 번째 레벨 그룹의 기준을 순회합니다.

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### 단계 6: 기준 정보 출력
마지막으로, 각 중첩 기준의 상세 정보를 출력해 필터 로직을 검증합니다.

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|------|--------|
| **필터에 접근할 때 NullPointerException 발생** | 프로젝트 파일에 실제로 작업 필터가 포함되어 있는지 확인하고, 필요하면 프로그래밍 방식으로 필터를 추가하세요. |
| **필드 이름이 올바르지 않음** | `ItemType` 열거형(예: `ItemType.Task`)을 사용해 오타를 방지하세요. |
| **필터가 결과를 반환하지 않음** | 테스트 연산자와 값이 MPP 파일의 데이터와 일치하는지 확인하세요. |

## FAQ
### Q: Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일과 호환되나요?
A: 예, Aspose.Tasks for Java는 여러 버전의 Microsoft Project 파일을 지원하여 호환성과 유연성을 제공합니다.

### Q: 프로젝트 요구사항에 맞게 필터 기준을 커스터마이징할 수 있나요?
A: 물론입니다! Aspose.Tasks for Java를 사용하면 프로젝트 고유의 요구에 따라 필터 기준을 자유롭게 조정할 수 있어, 목표 데이터만을 효율적으로 다룰 수 있습니다.

### Q: Aspose.Tasks for Java는 소규모와 대규모 프로젝트 모두에 적합한가요?
A: 예, 작은 프로젝트든 방대한 포트폴리오든 Aspose.Tasks for Java는 확장성과 성능을 제공하여 다양한 규모의 프로젝트 관리에 대응합니다.

### Q: Aspose.Tasks for Java는 포괄적인 문서와 지원 리소스를 제공하나요?
A: 네, 자세한 가이드와 API 레퍼런스는 [문서](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다. 또한 Aspose.Tasks 커뮤니티 포럼을 통해 질문이나 문제에 대한 도움을 받을 수 있습니다.

### Q: 구매 전에 Aspose.Tasks for Java의 기능을 체험해볼 수 있나요?
A: 물론입니다! [웹사이트](https://releases.aspose.com/)에서 무료 체험판을 받아 기능과 성능을 직접 확인해 보실 수 있습니다.

## 자주 묻는 질문

**Q: 새 필터를 프로그래밍 방식으로 어떻게 만들나요?**  
A: `project.getTaskFilters().add(new Filter("My Filter"))`를 사용하고, 이후 `FilterCriteria` 컬렉션을 정의하면 됩니다.

**Q: 작업이 아닌 리소스에 필터를 적용할 수 있나요?**  
A: 예 – `project.getResourceFilters()`를 사용해 리소스 전용 필터를 다룰 수 있습니다.

**Q: 여러 필터를 OR 논리로 결합할 수 있나요?**  
A: `Operation`을 `OR`로 설정한 상위 `FilterCriteria`를 만든 뒤, 개별 기준을 자식으로 추가하면 됩니다.

**Q: 사용자 정의 필드에 대한 필터링을 지원하나요?**  
A: 물론입니다. 사용자 정의 필드는 다른 필드와 동일하게 취급되며, 해당 `CustomField` 열거형 값을 사용해 참조합니다.

**Q: 대용량 MPP 파일에서 필터링이 성능에 미치는 영향은?**  
A: 필터링은 메모리 내에서 수행되며 일반적으로 빠릅니다. 하지만 매우 큰 프로젝트의 경우 `ProjectReader`를 사용해 필요한 섹션만 로드하는 방식을 고려하세요.

---

**마지막 업데이트:** 2025-12-25  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}