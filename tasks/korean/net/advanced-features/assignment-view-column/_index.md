---
date: 2026-03-19
description: Aspose.Tasks for .NET를 사용하여 프로젝트를 XML로 내보낼 때 여러 사용자 정의 열을 추가하고 사용자 정의
  열 너비를 지정하는 방법을 배웁니다.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks의 할당 보기에서 여러 사용자 정의 열 추가
url: /ko/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 할당 보기(Assignment View)에 다중 사용자 정의 열 추가하기

## 소개

이 튜토리얼에서는 **다중 사용자 정의 열**을 Aspose.Tasks for .NET의 할당 보기(Assignment View)에 추가하는 방법을 알아봅니다. 사용자 정의 열을 사용하면 메모, 비용 또는 사용자 정의 플래그와 같은 추가 데이터를 내보낸 보고서에 직접 표시할 수 있습니다. 가이드를 마치면 사용자 정의 열 너비를 지정하고, 프로젝트를 XML로 내보내며, 프로젝트 관리 요구에 맞게 보기를 맞춤 설정할 수 있게 됩니다.

## 빠른 답변
- **무엇을 할 수 있나요?** 사용자 정의 열에 할당 데이터를 표시하고 외관을 제어합니다.  
- **어떤 형식이 지원되나요?** `Spreadsheet2003SaveOptions`를 사용해 프로젝트를 XML(또는 기타 형식)으로 내보냅니다.  
- **라이선스가 필요합니까?** 예, 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **몇 개의 열을 추가할 수 있나요?** 제한 없음 – 추가 `AssignmentViewColumn` 인스턴스를 만들기만 하면 됩니다.

## 다중 사용자 정의 열이란?
다중 사용자 정의 열은 프로젝트를 저장하거나 내보낼 때 기본 할당 열 옆에 표시되는 사용자가 정의한 필드입니다. `ResourceAssignment` 객체의 사용자 정의 메모, 비용 코드 또는 계산된 값과 같은 속성을 표시하는 유연성을 제공합니다.

## 할당 보기(Assignment View)에 다중 사용자 정의 열을 추가하는 이유
- **향상된 보고:** 기본 열에 포함되지 않은 프로젝트 고유 정보를 포함합니다.  
- **의사결정 지원:** 이해관계자가 원시 파일을 탐색하지 않아도 필요한 정확한 데이터를 확인할 수 있습니다.  
- **일관된 서식:** 열 너비와 텍스트 변환을 제어해 깔끔하고 읽기 쉬운 출력물을 만들 수 있습니다.  

## 사전 요구 사항

시작하기 전에 다음을 준비하세요:

1. C# 프로그래밍 언어에 대한 기본 지식.  
2. Aspose.Tasks for .NET 라이브러리 설치. 설치되지 않았다면 **[여기](https://releases.aspose.com/tasks/net/)**에서 다운로드하세요.  
3. Visual Studio와 같은 통합 개발 환경(IDE).  

## 단계별 가이드

### 단계 1: 네임스페이스 가져오기
프로젝트와 시각화 작업에 필요한 클래스를 사용하기 위해 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### 단계 2: 프로젝트 로드
`Project` 인스턴스를 생성하고 기존 MPP 파일을 로드합니다.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### 단계 3: 스프레드시트 저장 옵션 생성
`Spreadsheet2003SaveOptions`를 인스턴스화합니다 – 이 객체를 통해 내보내기 전에 할당 보기를 사용자 정의할 수 있습니다.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### 단계 4: 사용자 정의 열 정의
표시하려는 각 데이터에 대해 `AssignmentViewColumn`을 생성합니다. 아래 예에서는 너비 200 포인트인 **Notes** 열을 추가합니다.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**팁:** *다중* 사용자 정의 열을 추가하려면 다른 필드 이름과 대리자(delegate) 로직을 사용해 이 단계를 반복하고, 각 인스턴스를 `options.AssignmentView.Columns`에 추가하면 됩니다.

### 단계 5: 옵션에 사용자 정의 열 추가
열(또는 열들)을 할당 보기의 `Columns` 컬렉션에 추가합니다.

```csharp
options.AssignmentView.Columns.Add(column);
```

### 단계 6: 할당 순회(선택적 디버깅)
할당을 순회하면서 사용자 정의 열 텍스트가 올바르게 생성되는지 확인할 수 있습니다.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### 단계 7: 사용자 정의 열과 함께 프로젝트 저장
마지막으로 프로젝트를 저장합니다. 예제에서는 XML로 저장하지만, 지원되는 다른 형식도 선택할 수 있습니다.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 사용자 정의 열이 포함된 프로젝트를 XML로 내보내는 방법
구성된 `Spreadsheet2003SaveOptions`와 함께 `project.Save`를 호출하면 Aspose.Tasks가 **다중 사용자 정의 열**을 포함한 프로젝트 데이터를 선택한 XML 파일에 기록합니다. 이를 통해 풍부한 프로젝트 정보를 다른 시스템이나 이해관계자와 쉽게 공유할 수 있습니다.

## 가독성을 위한 사용자 정의 열 너비 서식 지정
`AssignmentViewColumn` 생성자의 두 번째 매개변수는 열 너비(포인트 단위)를 제어합니다. 예상 텍스트 양에 맞게 값을 조정하세요. 예를 들어, **300**은 긴 메모에 적합하고, **100**은 짧은 플래그에 충분합니다.

## 일반적인 문제와 해결책
- **열 텍스트가 비어 있음:** 대리자가 문자열을 반환하는지, 그리고 기본 할당 속성(예: `Asn.NotesText`)이 채워졌는지 확인하세요.  
- **내보낸 파일에 열이 보이지 않음:** `Save` 호출 전에 `options.AssignmentView.Columns`에 사용자 정의 열이 포함되어 있는지 확인합니다.  
- **너비가 무시되는 경우:** 일부 내보내기 형식은 자체 레이아웃 규칙을 갖습니다. XML은 너비를 반영하지만, PDF/HTML은 추가 스타일링이 필요할 수 있습니다.

## 자주 묻는 질문

### Q1: 할당 보기(Assignment View)에 다중 사용자 정의 열을 추가할 수 있나요?
**A:** 예, 추가 `AssignmentViewColumn` 객체를 만들고 각각을 `options.AssignmentView.Columns`에 추가하면 됩니다.

### Q2: 일반적인 할당 필드에 대한 사전 정의된 변환기가 있나요?
**A:** 예, Aspose.Tasks는 많은 표준 필드에 대해 내장 변환기를 제공하므로 사용자 정의 대리자를 작성하지 않아도 데이터를 쉽게 추출할 수 있습니다.

### Q3: 사용자 정의 열의 외관(예: 텍스트 서식, 스타일 적용)을 맞춤 설정할 수 있나요?
**A:** 물론입니다. 너비 설정 외에도 열의 스타일 옵션을 통해 글꼴, 정렬 및 기타 시각적 속성을 조정할 수 있습니다.

### Q4: 할당 보기에서 기본 열을 제거할 수 있나요?
**A:** `Columns` 컬렉션에서 기본 열을 제거하거나 너비를 0으로 설정하면 기본 열을 제외할 수 있습니다.

### Q5: Aspose.Tasks가 사용자 정의 열이 포함된 스프레드시트 외에 다른 형식으로도 프로젝트를 내보낼 수 있나요?
**A:** 예, Aspose.Tasks는 PDF, HTML, XML 등 다양한 형식으로 내보내면서 사용자 정의 열 정의를 유지합니다.

---

**마지막 업데이트:** 2026-03-19  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}