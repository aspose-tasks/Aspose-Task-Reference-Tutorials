---
title: Aspose.Tasks의 사용자 지정 할당 보기 열
linktitle: Aspose.Tasks의 사용자 지정 할당 보기 열
second_title: Aspose.태스크 .NET API
description: 프로젝트 관리 기능을 향상시키기 위해 Aspose.Tasks for .NET에 사용자 지정 할당 보기 열을 추가하는 방법을 알아보세요.
type: docs
weight: 16
url: /ko/net/advanced-features/assignment-view-column/
---
## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 할당 뷰에 대한 사용자 정의 열을 추가하는 방법을 살펴보겠습니다. 사용자 정의 열은 유연성을 제공하며 프로젝트 관리 요구 사항과 관련된 추가 정보를 표시할 수 있습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. C# 프로그래밍 언어에 대한 기본 지식.
2.  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
3. Visual Studio와 같은 IDE(통합 개발 환경).

## 네임스페이스 가져오기

먼저, 사용자 지정 할당 보기 열을 만드는 데 필요한 클래스와 메서드에 액세스하기 위해 필요한 네임스페이스를 가져와 보겠습니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 1단계: 프로젝트 로드

 시작하려면 다음을 사용하여 프로젝트 파일을 로드하십시오.`Project` 수업:

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## 2단계: 스프레드시트 저장 옵션 만들기

 다음으로 인스턴스를 생성합니다.`Spreadsheet2003SaveOptions` 이를 통해 할당 보기 열을 사용자 정의할 수 있습니다.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## 3단계: 맞춤 열 정의

 이제 다음 인스턴스를 생성하여 맞춤 열을 정의하세요.`AssignmentViewColumn`. 이 클래스에는 할당 데이터를 열 텍스트로 변환하기 위한 열 이름, 너비 및 대리자 함수가 필요합니다.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## 4단계: 옵션에 사용자 정의 열 추가

저장 옵션의 할당 보기 열 컬렉션에 사용자 정의 열을 추가합니다.

```csharp
options.AssignmentView.Columns.Add(column);
```

## 5단계: 할당 반복

프로젝트의 각 자원 할당을 반복하고 사용자 정의 열 텍스트를 표시합니다.

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

## 6단계: 사용자 정의 열을 사용하여 프로젝트 저장

마지막으로 사용자 지정 할당 보기 열을 사용하여 프로젝트를 저장합니다.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 사용자 지정 할당 보기 열을 추가하는 방법을 배웠습니다. 사용자 정의 열은 프로젝트 요구 사항에 맞는 추가 정보를 표시하는 유연성을 제공하여 프로젝트 관리 기능을 향상시킵니다.

## FAQ

### Q1: 과제 보기에 여러 사용자 지정 열을 추가할 수 있나요?

 A1: 예. 추가 인스턴스를 생성하여 여러 맞춤 열을 추가할 수 있습니다.`AssignmentViewColumn` 그리고 그것들을`Columns` 수집.

### Q2: 공통 할당 필드에 사용할 수 있는 사전 정의된 변환기가 있습니까?

A2: 예, Aspose.Tasks는 공통 할당 필드에 대해 미리 정의된 변환기를 제공하므로 사용자 지정 열에 대한 데이터를 더 쉽게 추출할 수 있습니다.

### Q3: 텍스트 서식 지정, 스타일 적용 등 사용자 지정 열의 모양을 사용자 지정할 수 있나요?

대답 3: 예, 너비, 글꼴, 정렬 등의 속성을 수정하여 사용자 지정 열의 모양을 사용자 지정할 수 있습니다.

### Q4: 과제 보기에서 기본 열을 제거할 수 있나요?

 A4: 예, 기본 열을 제외하여 제거할 수 있습니다.`Columns` 수집하거나 너비를 0으로 설정합니다.

### Q5: Aspose.Tasks는 사용자 정의 열이 있는 스프레드시트 외에 다른 형식으로 프로젝트 내보내기를 지원합니까?

A5: 예, Aspose.Tasks는 PDF, HTML, XML 등 다양한 형식으로 프로젝트 내보내기를 지원하므로 다양한 프로젝트 보고 옵션이 가능합니다.