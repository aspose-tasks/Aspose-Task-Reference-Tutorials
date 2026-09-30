---
date: 2026-09-30
description: Aspose.Tasks for Java를 사용하여 작업 확장 속성을 만드는 방법을 배우세요, 맞춤 작업 필드를 추가하기 위한
  선도적인 Java 프로젝트 관리 라이브러리입니다.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Aspose.Tasks Java를 사용하여 작업 확장 속성을 만드는 방법
og_description: Aspose.Tasks for Java를 사용하여 작업 확장 속성을 만드는 방법을 배우세요, 맞춤 작업 필드를 추가하기
  위한 선도적인 Java 프로젝트 관리 라이브러리입니다.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Aspose.Tasks Java를 사용하여 작업 확장 속성을 만드는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Aspose.Tasks Java를 사용하여 작업 확장 속성을 만드는 방법
url: /ko/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Java를 사용하여 작업 확장 속성 만들기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에 **작업 확장 속성**을 만드는 방법을 배웁니다. 사용자 정의 필드를 추가하면 기본 열에 포함되지 않은 프로젝트별 데이터를 캡처할 수 있어 보고 및 리소스 계획을 보다 세밀하게 제어할 수 있습니다. 가이드가 끝날 때쯤이면 모든 작업에 일반 텍스트, 조회 기능이 있는 텍스트 및 기간 속성을 추가할 수 있게 됩니다.

## 빠른 답변
- **‘확장 속성’은 무엇을 의미합니까?** 작업, 리소스 또는 할당에 정의하고 연결하는 사용자 정의 필드입니다.  
- **이 기능을 제공하는 라이브러리는 무엇입니까?** Aspose.Tasks for Java, Java 프로젝트 관리 라이브러리입니다.  
- **시도하려면 라이선스가 필요합니까?** 예 – Aspose 웹사이트에서 30일 무료 체험을 이용할 수 있습니다.  
- **조회 값을 추가할 수 있나요?** 물론 가능합니다; 텍스트 또는 기간 필드에 허용되는 값 목록을 제공할 수 있습니다.  
- **API가 Java 8 및 이후 버전과 호환됩니까?** 예, Java 8 이상을 지원하며 모든 주요 운영 체제에서 실행됩니다.

## 작업 확장 속성이란 무엇입니까?
작업 확장 속성은 프로젝트 파일의 각 작업에 대한 추가 정보를 저장하는 사용자 정의 열입니다. 기본 필드와 같이 동작하지만 텍스트, 숫자, 날짜 또는 기간과 같은 필요한 모든 데이터 유형을 저장할 수 있습니다.

## 왜 Aspose.Tasks for Java를 사용합니까?
Aspose.Tasks는 **50개 이상의 파일 형식**을 지원하며 Microsoft Project를 설치하지 않아도 **10,000개 이상의 작업**이 포함된 프로젝트를 처리할 수 있습니다. 이 라이브러리는 완전히 오프라인으로 작동하여 데이터 프라이버시를 보장하고 엔터프라이즈 규모 솔루션에 대한 결정적인 성능을 제공합니다.

## 전제 조건
- 기본 Java 프로그래밍 지식.  
- Aspose.Tasks for Java 라이브러리가 설치되어 있어야 합니다. [website](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
- Java IDE(IntelliJ IDEA, Eclipse 또는 VS Code)가 머신에 설정되어 있어야 합니다.

## 패키지 가져오기
`import` 문을 사용하면 `Project`, `ExtendedAttributeDefinition`, `ExtendedAttribute`와 같은 핵심 클래스를 사용할 수 있습니다.

`Project`는 Microsoft Project 파일을 나타내며 파일을 읽고, 수정하고, 저장하는 메서드를 제공합니다.  
`ExtendedAttributeDefinition`은 작업, 리소스 또는 할당에 연결할 수 있는 사용자 정의 필드를 정의합니다.  
`ExtendedAttribute`는 정의의 인스턴스로, 특정 엔터티에 대한 실제 값을 보유합니다.

## 작업에 일반 텍스트 확장 속성을 추가하려면 어떻게 합니까?
일반 텍스트 확장 속성을 추가하려면 먼저 프로젝트를 로드하고, Text 유형의 정의를 만든 다음 프로젝트 컬렉션에 추가하고, 작업을 생성한 뒤 정의에서 속성을 인스턴스화하고, 텍스트 값을 설정하고, 작업에 연결한 후 마지막으로 프로젝트를 저장합니다.

### 1. 문서 디렉터리 경로 설정
소스 파일과 출력 파일이 위치하는 경로를 지정합니다.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. 새 프로젝트 만들기
`Project` 객체를 인스턴스화하고, 필요에 따라 기존 .mpp 파일을 로드합니다.

```java
String dataDir = "Your Document Directory";
```

### 3. Text1 유형의 확장 속성 정의 만들기
“Text1”이라는 이름의 일반 텍스트 열로 사용자 정의 필드를 정의합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. 정의를 프로젝트의 확장 속성 컬렉션에 추가
프로젝트가 인식하도록 새 정의를 등록합니다.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. 프로젝트에 작업 추가
사용자 정의 필드를 받을 작업을 생성합니다.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. 속성 정의에서 확장 속성 만들기
특정 작업에 바인딩할 수 있는 인스턴스를 생성합니다.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. 생성된 확장 속성에 값 할당
저장하려는 실제 텍스트를 설정합니다. 예: “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. 작업에 확장 속성 추가
속성 인스턴스를 작업의 `ExtendedAttributes` 컬렉션에 연결합니다.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. 프로젝트 저장
업데이트된 프로젝트를 원하는 형식으로 디스크에 저장합니다.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## 조회 옵션이 있는 텍스트 속성을 추가하려면 어떻게 합니까?
조회가 있는 텍스트 속성을 추가할 때는 일반 텍스트 속성에 대한 단계와 동일하게 진행하지만, 정의를 추가하기 전에 `LookupValues` 컬렉션에 허용된 문자열을 채워 넣습니다. 이러한 값은 Microsoft Project에서 드롭다운 목록으로 표시되어 데이터 일관성을 보장합니다.

## 조회 옵션이 있는 기간 속성을 추가하려면 어떻게 합니까?
조회가 있는 기간 속성을 추가하려면 정의를 만들 때 `Text1` 유형을 `Duration2`로 교체하고, `LookupValues` 컬렉션에 “1 day”, “2 days”와 같은 기간 문자열을 채워 넣습니다. 정의가 프로젝트에 추가된 후 속성 인스턴스를 만들고, 기간 값을 설정한 뒤 작업에 연결하고 파일을 저장합니다.

## 일반적인 문제 및 해결 방법
- **조회 값이 표시되지 않음** – `project.getExtendedAttributes().add(definition)`을 호출하기 *전에* 각 조회 항목을 `LookupValues` 컬렉션에 추가했는지 확인하십시오.  
- **속성 값이 저장되지 않음** – 값을 설정한 *후에* `ExtendedAttribute` 인스턴스를 작업에 추가했는지 확인하십시오.  
- **파일 크기가 예상치 않게 증가함** – 매우 큰 프로젝트를 다룰 때는 증분 저장을 활성화하기 위해 `project.setSaveOptions(new ProjectSaveOptions())` 호출을 고려하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 Spring, Hibernate, Apache POI 등을 포함한 모든 Java 생태계와 원활하게 통합됩니다.

**Q: Aspose.Tasks for Java가 대규모 프로젝트 관리 애플리케이션에 적합합니까?**  
A: 물론입니다. 이 라이브러리는 수천 개 작업이 포함된 프로젝트를 처리하도록 설계되었으며 메모리 사용량을 낮게 유지하기 위해 스트리밍을 지원합니다.

**Q: 상업 프로젝트에서 Aspose.Tasks for Java를 사용할 때 라이선스 고려 사항이 있나요?**  
A: 예, 유효한 상업용 라이선스가 필요합니다. 자세한 내용은 [Aspose.Tasks website](https://purchase.aspose.com/buy)에서 확인할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원이나 도움을 받으려면 어떻게 해야 하나요?**  
A: 커뮤니티 도움을 위해 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)을 방문하거나, Aspose 계정을 통해 지원 티켓을 열 수 있습니다.

**Q: 구매하기 전에 Aspose.Tasks for Java를 체험할 수 있나요?**  
A: 예, [Aspose.Tasks free trial](https://releases.aspose.com/) 페이지에서 무료 체험 버전을 이용할 수 있습니다.

---

**마지막 업데이트:** 2026-09-30  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## 관련 튜토리얼

- [Java 프로젝트 관리에서 사용자 정의 열 및 확장 속성](/tasks/java/project-management/extended-attributes/)
- [Aspose.Tasks for Java로 확장 작업 속성 읽기](/tasks/java/task-properties/extended-task-attributes/)
- [프로젝트 aspose.tasks 만들기 – 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}