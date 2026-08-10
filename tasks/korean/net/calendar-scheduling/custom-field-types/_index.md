---
date: 2026-07-19
description: Aspose.Tasks for .NET에서 사용자 정의 필드 유형을 추가하는 방법을 단계별 코드, 전제 조건 및 FAQ와 함께
  배웁니다.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks의 사용자 정의 필드 유형
og_description: Aspose.Tasks for .NET에서 사용자 정의 필드 유형을 추가하는 방법을 배웁니다. 이 단계별 가이드를 따라
  확장 속성을 효율적으로 생성, 정의 및 활용하세요.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Aspose.Tasks for .NET에서 사용자 정의 필드 유형 추가 방법
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Aspose.Tasks for .NET에서 사용자 정의 필드 유형 추가 방법
url: /ko/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 사용자 정의 필드 유형 추가 방법

## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일에 **사용자 정의 필드** 유형을 추가하는 방법을 알아봅니다. 사용자 정의 필드를 사용하면 작업, 리소스 또는 프로젝트 자체에 위험 점수, 부서 코드, 사용자 메모와 같은 추가 정보를 직접 저장할 수 있습니다. 환경 설정부터 정의, 추가 및 사용자 정의 텍스트 필드 검증까지 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **사용자 정의 필드란?** 작업/리소스에 텍스트, 숫자, 날짜 또는 플래그를 저장할 수 있는 사용자 정의 열입니다.  
- **어떤 클래스로 사용자 정의 필드를 정의하나요?** `ExtendedAttributeDefinition`.  
- **기존 프로젝트에 사용자 정의 필드를 추가할 수 있나요?** 예—프로젝트를 로드하고 정의를 만든 다음 컬렉션에 추가하면 됩니다.  
- **Aspose.Tasks에 라이선스가 필요합니까?** 프로덕션에서는 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Tasks에서 “사용자 정의 필드 추가”란 무엇인가요?
**사용자 정의 필드 추가**는 `ExtendedAttributeDefinition`을 생성하고 이를 프로젝트의 `ExtendedAttributes` 컬렉션에 연결하는 과정을 의미합니다. 이를 통해 표준 Project 스키마에 포함되지 않은 메타데이터를 저장할 수 있습니다. 작업, 리소스 또는 프로젝트 자체에 적용하여 위험 수준, 부서 코드, 사용자 메모 등 기본 필드에 없는 정보를 캡처할 수 있습니다.

## 프로젝트 관리에서 사용자 정의 필드를 사용하는 이유
Aspose.Tasks는 **50개 이상의 내장 확장 속성 유형**을 지원하며 파일 크기에 크게 영향을 주지 않고 **무제한의 사용자 정의 필드**를 정의할 수 있습니다. 사용자 정의 필드를 사용하면 다음을 수행할 수 있습니다.  
이 필드들은 Microsoft Project에서 추가 열로 표시되며 수식, 보고서 및 필터에서 참조할 수 있습니다. 프로젝트 파일에 저장되어 함께 이동하므로 다운스트림 도구에서도 사용자 정의 데이터가 유지됩니다.

## 전제 조건

### 1. Visual Studio 설치
머신에 Visual Studio(2019 이상)가 설치되어 있는지 확인하세요. Microsoft 웹사이트에서 다운로드할 수 있습니다.

### 2. Aspose.Tasks for .NET
프로젝트에 Aspose.Tasks NuGet 패키지를 추가하세요. 최신 버전은 [여기](https://releases.aspose.com/tasks/net/)에서 다운로드합니다.

### 3. 기본 C# 지식
C# 구문, 클래스 및 .NET 프로젝트 구조에 익숙해야 합니다.

## 네임스페이스 가져오기

`Project`, `ExtendedAttributeDefinition` 및 관련 열거형은 `Aspose.Tasks` 네임스페이스에 포함됩니다. 파일 상단에 다음과 같이 가져오세요:

`Aspose.Tasks` 네임스페이스는 Microsoft Project 파일을 처리하기 위한 모든 핵심 타입을 제공합니다.

```csharp

```

## 프로젝트에 사용자 정의 필드 추가 방법?

기존 프로젝트를 로드하고, 사용자 정의 필드 정의를 만든 뒤, 프로젝트의 확장 속성 컬렉션에 추가합니다—세 단계만으로 작업, 리소스 및 프로젝트 자체에 적용할 수 있으며 파일 저장 시 사용자 정의 필드가 지속됩니다.

### 단계 1: 프로젝트 객체 생성
`Project`는 Aspose.Tasks의 최상위 객체로, 메모리 내에 단일 Project 파일을 나타냅니다. 인스턴스를 생성하면 파일이 로드되고 작업, 리소스 및 확장 속성에 접근할 수 있습니다.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 단계 2: 사용자 정의 필드 정의
`ExtendedAttributeDefinition`은 새로운 열을 설명합니다. 이 예에서는 작업용 **텍스트** 유형 사용자 정의 필드를 만들고 별칭을 “MyText”로 지정합니다. `ExtendedAttributeTask.Text1` 열거형 값은 Aspose.Tasks가 값을 저장할 위치를 지정합니다.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### 단계 3: 프로젝트에 사용자 정의 필드 정의 추가
프로젝트의 `ExtendedAttributes` 컬렉션은 모든 사용자 정의 필드 정의를 보관합니다. 정의를 추가하면 프로젝트 내 모든 작업에서 해당 필드를 사용할 수 있게 됩니다.

```csharp
project.ExtendedAttributes.Add(definition);
```

## 일반적인 문제 및 해결책
- **필드가 MS Project UI에 표시되지 않음** – `Alias` 속성을 설정했는지 확인하세요; MS Project는 별칭을 열 머리글로 표시합니다.  
- **저장 시 예외 발생** – 프로젝트 파일이 읽기 전용이 아니며 유효한 라이선스가 있는지 확인하세요.  
- **재로드 후 사용자 정의 필드 값이 사라짐** – 작업에 값을 할당한 후 `project.Save("output.mpp")`를 호출했는지 확인하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 .NET 프레임워크와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET Framework, .NET Core 및 .NET 5/6/7과 호환됩니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준 애플리케이션에 적합한가요?**  
A: 물론입니다. **10,000개 작업**까지 처리할 수 있으며 다중 스레드 서버 환경에서도 실행됩니다.

**Q: Aspose.Tasks가 여러 프로젝트 파일 형식을 지원하나요?**  
A: 예—Aspose.Tasks는 MPP, XML, HTML, CSV 형식을 읽고 쓸 수 있어 **주요 Microsoft Project 버전**을 모두 지원합니다.

**Q: Aspose.Tasks를 사용해 리소스 데이터를 조작할 수 있나요?**  
A: 예, 리소스를 추가, 업데이트 및 삭제할 수 있으며 리소스에도 사용자 정의 필드를 할당할 수 있습니다.

**Q: Aspose.Tasks 사용자를 위한 커뮤니티 포럼이 있나요?**  
A: 예, 다른 사용자와 소통하고 Aspose 팀의 지원을 받을 수 있는 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)이 있습니다.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks에서 MS Project 확장 속성 정의 마스터하기](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Aspose.Tasks로 MS Project 확장 속성 조작하기](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks에서 필드 헬퍼 MS Project 통합](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}