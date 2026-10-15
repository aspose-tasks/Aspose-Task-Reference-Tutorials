---
date: 2026-10-15
description: Aspose.Tasks for .NET에서 사용자 정의 속성을 추가하고 프로젝트 속성을 관리하는 방법을 배우고, 프로젝트 메타데이터
  제어를 강화하세요.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Aspose.Tasks에서 사용자 정의 프로젝트 속성 컬렉션 관리
og_description: Aspose.Tasks for .NET을 사용하여 프로젝트 파일에 사용자 정의 속성을 추가하세요. 이 가이드는 사용자
  정의 속성을 관리하고, 읽으며, 부울 또는 문자열 값을 효율적으로 추가하는 방법을 보여줍니다.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: 프로젝트에 Aspose.Tasks .NET API를 사용하여 사용자 정의 속성 추가
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Aspose.Tasks for .NET에서 사용자 정의 속성을 추가하는 방법
url: /ko/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET에서 사용자 정의 속성 추가 방법

## 소개

Add custom property support lets you store project‑specific metadata that the built‑in fields don’t cover. In this tutorial you’ll learn how to **add custom property**, read it back, and manage the entire custom property collection using Aspose.Tasks for .NET. By the end you’ll be able to tailor project files with Boolean, DateTime, Double, and String values that fit your business rules.

## 빠른 답변
- **Boolean 사용자 정의 속성을 추가할 수 있나요?** 예 – `CustomPropertyType.Boolean`를 사용하십시오.  
- **지원되는 사용자 정의 속성 유형은 몇 개입니까?** 네 가지: Boolean, DateTime, Double, String.  
- **사용자 정의 속성 컬렉션이 읽기 전용인가요?** 프로젝트가 읽기 전용 소스에서 로드된 경우 읽기 전용일 수 있습니다.  
- **이 기능을 사용하려면 라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 충분하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **호환되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 사용자 정의 속성이란?

사용자 정의 속성은 Project 객체에 연결하는 사용자 정의 메타데이터 필드입니다. 이를 통해 “위험 수준”, “고객 ID”와 같이 표준 MS‑Project 필드에 포함되지 않은 추가 정보를 저장하거나 Boolean 플래그 등을 저장할 수 있습니다.

## Aspose.Tasks에서 사용자 정의 속성을 추가하는 이유

Aspose.Tasks는 **50개 이상의 입력 및 출력 형식**을 지원하며, **최대 10,000개의 작업**을 메모리에 전체 파일을 로드하지 않고도 처리할 수 있습니다. 사용자 정의 속성을 추가하면 비즈니스에 중요한 데이터를 프로젝트 파일에 직접 삽입할 수 있어 외부 데이터베이스가 필요 없으며, 데이터가 프로젝트와 함께 이동하도록 보장합니다.

## 전제 조건

- 작업 환경에 Visual Studio(최근 버전 중 하나)가 설치되어 있어야 합니다.  
- Aspose.Tasks for .NET – [download link](https://releases.aspose.com/tasks/net/)에서 다운로드하십시오.  
- C# 구문 및 .NET 프로젝트 구조에 대한 기본적인 이해가 필요합니다.

## 네임스페이스 가져오기

다음 네임스페이스를 사용하면 핵심 프로젝트 모델 및 사용자 정의 속성 API에 접근할 수 있습니다.

```csharp
using Aspose.Tasks;
using System;


```

## Aspose.Tasks에서 사용자 정의 속성을 추가하는 방법?

사용자 정의 속성을 추가하려면 먼저 프로젝트를 로드한 다음 `CustomProperty` 객체를 생성하고 이름, 유형 및 값을 설정한 뒤 프로젝트의 `CustomProperties` 컬렉션에 추가합니다. 이 작업은 메타데이터를 프로젝트 파일에 직접 삽입하며, `project.Save(...)`를 호출하면 변경 사항이 저장됩니다.  

`CustomProperty`는 프로젝트에 연결된 단일 사용자 정의 필드를 나타냅니다.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### 단계 1: 프로젝트 초기화

Project는 Aspose.Tasks에서 프로젝트 파일을 나타내는 기본 클래스입니다.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### 단계 2: 사용자 정의 속성 컬렉션 준비 상태 확인

CustomProperties는 프로젝트의 모든 사용자 정의 속성 객체를 보관하는 컬렉션입니다.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### 단계 3: 사용자 정의 속성 추가

Add 메서드는 새로운 사용자 정의 속성을 프로젝트 컬렉션에 삽입합니다.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### 단계 4: 사용자 정의 속성 접근

CustomProperties 컬렉션은 IEnumerable을 구현하여 각 CustomProperty를 반복할 수 있게 합니다.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### 단계 5: 사용자 정의 속성 값 가져오기

Get 메서드는 이름으로 사용자 정의 속성의 값을 반환합니다.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### 단계 6: 사용자 정의 속성 이름 반복

Names 속성은 컬렉션에 있는 모든 사용자 정의 속성 이름 목록을 제공합니다.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### 단계 7: 사용자 정의 속성 제거 또는 전체 삭제

Remove 메서드는 특정 속성을 삭제하고, Clear는 전체 컬렉션을 비웁니다.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## 일반적인 함정 및 문제 해결

- **읽기 전용 컬렉션** – `project.CustomProperties.IsReadOnly`가 `true`를 반환하면, 소스 파일이 독점 읽기 모드로 열려 있지 않은지 확인하거나 편집 전에 쓰기 가능한 위치로 복사하십시오.  
- **형식 불일치** – 선언된 `CustomPropertyType`과 일치하지 않는 값을 할당하면 `ArgumentException`이 발생합니다. 올바른 `Type`을 정의한 후에 `Value`를 설정하십시오.  
- **변경 사항 저장** – 속성을 추가하거나 제거한 후 `project.Save("output.mpp")`를 호출하여 변경 내용을 영구 저장하십시오. 그렇지 않으면 변경 사항은 메모리 내에만 남습니다.

## 자주 묻는 질문

**Q: Aspose.Tasks for .NET을 사용하여 프로젝트에 모든 데이터 유형의 사용자 정의 속성을 추가할 수 있나요?**  
A: 예, Boolean, DateTime, Double, String 유형을 지원하는 사용자 정의 속성을 추가할 수 있습니다.

**Q: Aspose.Tasks for .NET에서 사용자 정의 속성 이름을 반복할 수 있나요?**  
A: 물론입니다. `Names` 속성을 사용하여 사용자 정의 속성 이름을 반복할 수 있습니다.

**Q: 프로젝트에서 특정 사용자 정의 속성을 어떻게 제거할 수 있나요?**  
A: `Remove` 메서드를 사용하여 이름으로 사용자 정의 속성을 제거할 수 있습니다.

**Q: Aspose.Tasks for .NET이 임시 라이선스를 지원하나요?**  
A: 예, 평가용으로 Aspose 웹사이트에서 임시 라이선스를 받을 수 있습니다.

**Q: Aspose.Tasks for .NET에 대한 지원이나 추가 도움을 어디서 찾을 수 있나요?**  
A: 문의나 도움이 필요하면 Aspose.Tasks 포럼 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 를 방문하십시오.

---

**마지막 업데이트:** 2026-10-15  
**테스트 대상:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for .NET을 사용하여 내장 프로젝트 속성 읽는 방법](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Aspose.Tasks에서 MS Project 속성 컬렉션 관리](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks 사용자 정의 필드 유형 – 캘린더 및 일정 관리](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}