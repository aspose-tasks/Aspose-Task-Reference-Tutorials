---
date: 2026-06-10
description: Java에서 확장 속성을 만드는 방법, Microsoft Project 파일을 로드하고, 숫자 값을 설정하며, Aspose.Tasks
  for Java를 사용하여 프로젝트를 XML로 저장하는 방법을 배웁니다.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Aspose.Tasks에서 확장 리소스 속성 처리
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Java와 Aspose.Tasks를 사용하여 확장 속성 만들기
url: /ko/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Aspose.Tasks를 사용하여 확장 속성 만들기

## 소개
이 실습 가이드에서는 Aspose.Tasks를 사용하여 Microsoft Project 파일에 대한 **Java에서 확장 속성 만들기**를 수행합니다. 기존 프로젝트를 로드하고, 새로운 숫자 속성을 정의하고, 리소스에 값을 할당한 다음, 변경 사항을 XML 파일로 저장하는 과정을 단계별로 안내합니다. 최종적으로 Java 기반 프로젝트 관리 솔루션에 쉽게 적용할 수 있는 재사용 가능한 코드 패턴을 얻게 됩니다.

## 빠른 답변
- **확장 속성이란?**  
  사용자 정의 필드(예: 나이, 기술 수준)로, 리소스 또는 작업에 대한 추가 데이터를 저장합니다.  
- **어떤 API가 이를 생성합니까?**  
  Aspose.Tasks for Java는 사용자 정의 속성을 정의하고 관리하기 위해 `ExtendedAttributeDefinition` 클래스를 제공합니다.  
- **라이선스가 필요합니까?**  
  개발에는 임시 평가 라이선스로 충분하지만, 프로덕션 배포에는 정식 라이선스가 필요합니다.  
- **숫자를 저장할 수 있나요?**  
  예 – 정확한 소수 값을 할당하려면 `setNumericValue(BigDecimal)`를 사용합니다.  
- **변경 사항을 어떻게 저장합니까?**  
  `project.save("output.xml", SaveFileFormat.Xml)`를 호출하여 업데이트된 프로젝트를 XML 형식으로 저장합니다.

## 사용자 정의 속성이란?
**사용자 정의 속성**(확장 속성이라고도 함)은 Microsoft Project의 리소스 또는 작업에 추가할 수 있는 추가 열입니다. 직원 연령, 인증 수준 또는 비즈니스 고유 지표와 같이 기본 필드에 포함되지 않은 데이터를 캡처할 수 있습니다.

## Java에서 확장 속성을 생성하는 이유
Java에서 확장 속성을 생성하면 프로젝트 데이터를 프로그래밍 방식으로 풍부하게 만들 수 있어 파일 간 일관성을 보장하고 자동 보고를 가능하게 합니다. 속성을 한 번 정의하면 수동 입력 없이도 여러 리소스나 작업에 적용할 수 있어 시간 절약과 오류 감소에 도움이 됩니다.

- **조직에 맞게 데이터 맞춤화** – 수동 Excel 작업 없이도 중요한 모든 지표를 저장합니다.  
- **보다 풍부한 보고 활성화** – 나중에 대시보드나 분석을 위해 사용자 정의 필드를 조회합니다.  
- **일관성 유지** – 여러 프로젝트에 동일한 정의를 프로그래밍 방식으로 적용하여 인적 오류를 없앱니다.  
- **성능 검증** – Aspose.Tasks는 제품 벤치마크에 따라 전체 파일을 메모리에 로드하지 않고도 최대 10,000개의 작업과 5,000개의 리소스를 처리합니다.

## 전제 조건
1. **Java Development Kit** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 최신 릴리스를 [여기](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE** – Eclipse, IntelliJ IDEA 또는 Java와 호환되는 개발 환경.

## Java에서 확장 속성을 만드는 방법
프로젝트를 로드하고, 속성을 정의하고, 리소스에 연결한 뒤 파일을 저장합니다 – 모두 몇 단계의 간단한 절차로 이루어집니다. 다음 섹션에서는 각 단계를 간결히 설명하고 실제 코드가 들어갈 자리인 플레이스홀더를 제공합니다.

### 단계별 가이드

#### 패키지 가져오기
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` 및 관련 클래스는 `com.aspose.tasks` 네임스페이스에 있습니다. Java 파일 상단에 이들을 import하십시오.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### 단계 1: 데이터 디렉터리 정의
`Paths`는 플랫폼에 독립적인 방식으로 파일 시스템 경로를 얻는 메서드를 제공하는 유틸리티 클래스입니다.

```java
String dataDir = "Your Data Directory";
```

#### 단계 2: Microsoft Project 파일 로드
`Project`는 메모리 내에서 Microsoft Project 파일을 나타내며, 내용에 대한 읽기 및 쓰기 접근을 허용합니다.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### 단계 3: 사용자 정의 속성 정의
`ExtendedAttributeDefinition`은 리소스 또는 작업에 연결할 수 있는 새로운 사용자 정의 필드의 스키마를 정의합니다.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### 단계 4: Java에서 숫자 값 설정
`ExtendedAttributeResource`는 특정 리소스 인스턴스에 대한 사용자 정의 속성 값을 보유합니다.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### 단계 5: 리소스 추가 및 사용자 정의 속성 연결
`Resource`는 사람, 장비 또는 자재와 같은 프로젝트 리소스를 모델링합니다.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### 단계 6: 프로젝트를 XML로 저장
`SaveFileFormat`은 XML을 포함한 프로젝트 저장을 위한 지원 출력 형식을 열거합니다.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### 단계 7: 결과 표시
`System.out.println`은 표준 콘솔 출력에 텍스트 한 줄을 출력합니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 함정 및 팁
- **속성 ID 충돌:** 새 정의를 만들기 전에 항상 `project.getExtendedAttributes().getById(id)`를 호출하여 중복 식별자를 방지합니다.  
- **정밀도 처리:** 정확한 숫자 값을 위해 `float`/`double`보다 `BigDecimal`을 선호합니다; 이는 보고 시 반올림 오류를 방지합니다.  
- **파일 경로 신뢰성:** `Paths.get(...).toAbsolutePath()`를 사용하거나 IDE 작업 디렉터리를 구성하여 `FileNotFoundException`을 방지합니다.  

## 자주 묻는 질문

**Q: 작업에도 리소스와 마찬가지로 사용자 정의 속성을 만들 수 있나요?**  
A: 예 – 속성 스키마를 정의할 때 `ExtendedAttributeResource` 대신 `ExtendedAttributeTask`를 사용합니다.

**Q: 한 번에 여러 사용자 정의 속성을 추가할 수 있나요?**  
A: 물론입니다. 각 속성마다 별도의 `ExtendedAttributeDefinition` 객체를 생성하고 원하는 리소스나 작업에 연결합니다.

**Q: 프로젝트를 어떤 형식으로 저장할 수 있나요?**  
A: Aspose.Tasks는 XML, MPP, PDF, HTML 등 30가지 이상의 추가 형식을 지원합니다. 이 예제에서는 `SaveFileFormat.Xml`을 사용했습니다.

**Q: 개발 빌드에 라이선스가 필요합니까?**  
A: 테스트용으로는 임시 평가 라이선스로 충분합니다. 프로덕션 배포 시에는 정식 상용 라이선스가 필요합니다.

**Q: 나중에 사용자 정의 속성 값을 어떻게 읽어올 수 있나요?**  
A: `resource.getExtendedAttributes()`를 호출하고 컬렉션을 순회하면서 `getNumericValue()` 또는 `getTextValue()`로 저장된 값을 가져옵니다.

---

**마지막 업데이트:** 2026-06-10  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [리소스 생성 방법 – Aspose.Tasks for Java를 사용한 리소스 관리](/tasks/java/resource-management/)
- [사용자 정의 필드 만들기 Aspose - 확장 속성 처리](/tasks/java/project-management/extended-attributes/)
- [프로젝트 생성 방법 – Aspose.Tasks를 사용한 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}