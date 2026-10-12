---
date: 2026-10-10
description: Aspose.Tasks에서 확장 속성을 추가하고, 평가 함수를 사용하며, 이 Java 프로젝트 관리 라이브러리를 통해 프로젝트
  보고서를 생성하는 방법을 배웁니다.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Aspose.Tasks 수식에서 평가 함수 지원
og_description: Aspose.Tasks에서 확장 속성을 추가하고, 평가 함수를 사용하며, 이 Java 프로젝트 관리 라이브러리를 통해
  프로젝트 보고서를 생성하는 방법을 배웁니다.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Aspose.Tasks 수식에서 확장 속성을 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Aspose.Tasks 수식에서 확장 속성을 추가하는 방법
url: /ko/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 수식에서 확장 속성을 추가하는 방법

## 소개
Aspose.Tasks for Java는 **Java 프로젝트 관리 라이브러리**로, Java에서 `Project` 객체를 생성하고 Microsoft Project 함수를 코드 내에서 직접 평가하여 프로젝트 보고서를 생성할 수 있습니다. 이러한 수식을 삽입하면 복잡한 계산을 수행하고, 맞춤형 보고서를 생성하며, 개발 환경을 떠나지 않고 프로젝트 분석을 자동화할 수 있습니다. 이 튜토리얼에서는 프로젝트 객체를 만들고, 확장 속성을 추가하며, 평가 함수를 사용해 **add custom field task** 데이터를 추가하는 과정을 안내합니다.

## 빠른 답변
- **“create project object java”는 무엇을 의미하나요?** 메모리 내 `Project` 인스턴스를 생성하여 프로그래밍 방식으로 조작할 수 있게 합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (공식 사이트에서 다운로드).  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 Aspose.Tasks 라이선스가 필요합니다; 무료 체험판을 이용할 수 있습니다.  
- **사용자 정의 필드를 사용할 수 있나요?** 예 – 작업에 **add extended attribute**를 추가하여 사용자 정의 필드로 사용할 수 있습니다.  
- **모든 Project 파일 형식과 호환되나요?** Aspose.Tasks는 3가지 주요 형식(MPP, MPT, XML)과 50가지 이상의 추가 입출력 형식을 지원합니다.

## 전제 조건
시작하기 전에 다음을 준비하십시오:

1. **Java 개발 환경** – JDK 8 이상 및 IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
2. **Aspose.Tasks for Java 라이브러리** – [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하고 포함합니다.

## 패키지 가져오기
프로젝트, 작업 및 확장 속성을 다룰 수 있도록 Java 클래스에 Aspose.Tasks 네임스페이스를 추가합니다:

```java
import com.aspose.tasks.*;
```

## 프로젝트 보고서 생성 – create project object java
`Project` 클래스는 메모리 내 Microsoft Project 파일을 나타내며 작업, 리소스 및 사용자 정의 데이터를 노출합니다. 이 클래스를 인스턴스화하면 정의할 모든 프로젝트 요소를 담을 컨테이너가 제공됩니다.

```java
Project project = new Project();
```

위 코드는 **creates project object java**를 수행하며, 비어 있는 상태에서 맞춤 구성을 시작할 수 있습니다.

## 확장 속성을 추가하는 방법
`ExtendedAttributeDefinition` 클래스는 작업에 첨부할 수 있는 사용자 정의 필드를 정의합니다. 확장 속성을 추가하려면 `Number` 유형으로 이 클래스의 인스턴스를 만들고, “Sine”과 같은 별칭을 지정한 뒤, 프로젝트의 `ExtendedAttributes` 컬렉션에 추가하고, 해당 사용자 정의 필드가 필요한 각 작업에 연결합니다.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

여기서는 `Number` 유형의 **add extended attribute**를 “Sine”이라는 이름으로 만들고 작업에 연결합니다.

## 프로젝트에 확장 속성 추가
속성 정의를 프로젝트에 등록하여 모든 작업이 이를 참조할 수 있도록 합니다.

```java
project.getExtendedAttributes().add(attr);
```

## 새 작업 만들기
`Task`는 프로젝트 내 작업 항목을 나타내며 사용자 정의 필드를 포함할 수 있습니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 프로젝트에 사용자 정의 필드 작업 추가
이전에 정의한 확장 속성을 새로 만든 작업에 연결하여, 수식이나 계산에 사용할 수 있는 맞춤형 “Sine” 필드를 작업에 부여합니다.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

이제 작업은 수식이나 계산에 사용할 수 있는 맞춤형 “Sine” 필드를 보유하게 됩니다. 이것이 **add custom field task** 데이터를 프로그래밍 방식으로 추가하는 방법이기도 합니다.

## 평가 함수를 사용하는 이유
평가 함수를 사용하면 Microsoft Project 수식(e.g., `Sin([Start])`)을 Aspose.Tasks에 직접 삽입하여 외부 처리 없이 즉시 계산할 수 있습니다. 이를 통해 모든 프로젝트 로직을 한 곳에 유지하고 데이터 동기화 오류를 줄이며 보고서 생성 속도를 높일 수 있습니다. Aspose.Tasks는 100개 이상의 MS Project 함수를 지원하여 Java 내부에 포괄적인 계산 엔진을 제공합니다.

## 일반적인 문제 및 해결책
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | 사용자 정의 필드 유형이 예상되는 숫자 유형과 일치하는지 확인하십시오. |
| **Extended attribute not visible** | 작업을 생성하기 **전에** 속성 정의가 프로젝트에 추가되었는지 확인하십시오. |
| **License exception** | 임시 또는 정식 **Aspose.Tasks license**를 설치하십시오; 체험 모드에서는 일부 기능이 제한될 수 있습니다. |
| **Missing temporary license** | Aspose 웹사이트에서 **temporary Aspose license**를 얻으십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 복잡한 MS Project 수식을 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다양한 MS Project 함수를 평가할 수 있어 Java 애플리케이션 내에서 복잡한 계산을 수행할 수 있습니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 예, Aspose.Tasks for Java는 MPP, MPT, XML 형식을 포함한 여러 버전의 Microsoft Project 파일을 지원합니다.

**Q: 구매 전에 Aspose.Tasks for Java를 체험해볼 수 있나요?**  
A: 예, 웹사이트의 [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy)에서 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어떻게 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼인 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

**Q: Aspose.Tasks for Java용 임시 라이선스가 제공되나요?**  
A: 예, Aspose 웹사이트의 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/)에서 테스트용 임시 라이선스를 얻을 수 있습니다.

## 결론
이 단계들을 따라 **create project object**, **add extended attribute**, 그리고 평가 함수를 활용해 **generate project report**를 자동으로 생성하는 방법을 배웠습니다. 이제 이 기반을 확장하여 보다 풍부한 프로젝트 분석, 맞춤형 대시보드, 자동 일정 도구 등을 구축할 수 있으며, 모두 Aspose.Tasks for Java가 지원합니다.

---

**마지막 업데이트:** 2026-10-10  
**테스트 대상:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose

## 관련 튜토리얼

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}