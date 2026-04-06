---
date: 2026-04-06
description: Aspose.Tasks for .NET에서 막대 스타일을 변경하고 막대 색상을 사용자 지정하여 프로젝트 시각화를 향상시키는
  방법을 배우세요.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Aspose.Tasks의 스타일링 바
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 막대 스타일을 변경하는 방법
url: /ko/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 바 스타일 변경 방법

## 소개

Microsoft Project 파일에서 **바를 변경하는 방법**을 필요로 한다면, Aspose.Tasks for .NET은 바 색상, 형태 및 텍스트 스타일에 대한 완전한 제어를 제공합니다. 바 색상 및 기타 시각적 속성을 사용자 지정하면 프로젝트 계획을 더 쉽게 읽을 수 있고 조직의 브랜딩에 맞출 수 있습니다. 이 튜토리얼에서는 프로젝트를 로드하고 새로운 시각 규칙을 적용하여 내보내는 전체 단계별 예제를 통해 바 스타일을 변경하는 방법을 안내합니다.

## 빠른 답변
- **무엇을 스타일링할 수 있나요?** Gantt 차트의 바, 마일스톤 및 작업 텍스트.  
- **어떤 형식이 스타일이 적용된 바를 지원하나요?** PDF, XLSX, HTML 및 `PdfSaveOptions`로 저장할 때 기본 MPP.  
- **라이선스가 필요합니까?** 상용 라이선스가 프로덕션 사용에 필요합니다; 무료 체험판은 테스트에 사용할 수 있습니다.  
- **여러 스타일을 적용할 수 있나요?** 예 – 필요에 따라 `BarStyle` 객체를 여러 개 추가하십시오.  
- **.NET Core와 호환되나요?** 물론 – .NET Framework와 .NET Core/5/6+에서도 작동합니다.

## Aspose.Tasks에서 바 스타일링이란?

바 스타일링을 사용하면 Aspose.Tasks 엔진이 Gantt 차트를 렌더링할 때 적용하는 시각적 규칙을 정의할 수 있습니다. 각 규칙(**BarStyle**)은 특정 항목 유형(작업, 마일스톤 또는 요약 작업)을 대상으로 하며 색상, 형태 및 사용자 정의 텍스트까지 설정할 수 있습니다.

## 왜 바 색상을 사용자 지정해야 할까요?

바 색상을 사용자 지정하면 이해관계자가 중요한 경로, 지연된 작업 또는 마일스톤을 즉시 식별할 수 있습니다. 또한 기업 색상 체계에 맞출 수 있어 보고서가 전문적이고 브랜드에 부합하게 보입니다.

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Aspose.Tasks for .NET** – [download page](https://releases.aspose.com/tasks/net/)에서 다운로드하십시오.  
2. .NET을 지원하는 개발 환경 (Framework 4.6+, .NET Core 3.1+ 또는 그 이후 버전).  
3. C#에 대한 기본 지식 – 예제는 간단하고 독립적인 코드를 사용합니다.

## 네임스페이스 가져오기

먼저, 사용할 클래스가 포함된 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 단계 1: 프로젝트 로드

작업할 프로젝트 객체를 얻기 위해 기존 MPP 파일을 로드하거나 새 파일을 생성합니다:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 단계 2: 저장 옵션 구성

`PdfSaveOptions` 인스턴스를 생성하고 사용자 정의 스타일을 저장할 `BarStyles` 컬렉션을 초기화합니다:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 단계 3: 바 스타일 정의

이제 `BarStyle` 객체를 만들고 바의 모양을 제어하는 속성을 설정합니다. 여기에서 **바 색상**과 형태를 사용자 지정합니다:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## 단계 4: 텍스트 변환기 사용자 지정 (선택 사항)

바에 표시되는 텍스트를 조정하려면 사용자 정의 변환기를 할당할 수 있습니다. 예제에서는 이미 “T”로 시작하지 않는 작업 이름에 접두사를 추가합니다:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## 단계 5: 옵션에 바 스타일 추가

완전히 구성된 스타일을 저장 옵션의 `BarStyles` 컬렉션에 추가합니다:

```csharp
options.BarStyles.Add(style);
```

## 단계 6: 프로젝트 저장

마지막으로 프로젝트를 내보냅니다. PDF(또는 다른 형식)는 정의한 바 스타일을 사용하여 Gantt 차트를 렌더링합니다:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **바 스타일이 적용되지 않음** | `BarStyles` 컬렉션이 비어 있거나 저장 옵션에 연결되지 않았습니다. | `Save`를 호출하기 전에 `BarStyle`을 `options.BarStyles`에 추가했는지 확인하십시오. |
| **PDF에서 색상이 다르게 보임** | PDF 렌더링이 다른 색상 프로파일을 사용할 수 있습니다. | 표준 `System.Drawing.Color` 값을 사용하거나 사용자 정의 ARGB 색상을 정의하십시오. |
| **텍스트 변환기가 null 참조 예외 발생** | 일부 작업의 `Tsk.Name` 속성이 null입니다. | `task.Get(Tsk.Name)`에 접근하기 전에 null 검사를 추가하십시오. |

## FAQ

### Q1: 단일 프로젝트에 여러 바 스타일을 적용할 수 있나요?

A1: 예, 동일한 프로젝트 내에서 서로 다른 작업 유형에 여러 바 스타일을 정의하고 적용할 수 있습니다.

### Q2: 런타임 중에 바 스타일을 동적으로 변경할 수 있나요?

A2: 예, 애플리케이션 내에서 특정 조건이나 사용자 선호도에 따라 바 스타일을 동적으로 수정할 수 있습니다.

### Q3: Aspose.Tasks가 스타일이 적용된 바를 포함한 프로젝트를 다양한 파일 형식으로 내보내는 것을 지원하나요?

A3: 예, Aspose.Tasks는 PDF, XLSX, HTML 등 다양한 형식으로 스타일이 적용된 바를 포함한 프로젝트를 내보내는 것을 지원합니다.

### Q4: Aspose.Tasks에 미리 정의된 바 스타일이 있나요?

A4: Aspose.Tasks는 기본 바 스타일을 제공하지만, 개발자는 프로젝트 요구에 맞게 사용자 정의 바 스타일을 만들 수도 있습니다.

### Q5: API를 사용하여 프로젝트 내 기존 바 스타일을 검색하고 수정할 수 있나요?

A5: 예, Aspose.Tasks for .NET API를 사용하여 기존 바 스타일을 프로그래밍 방식으로 검색하고 수정할 수 있습니다.

## 자주 묻는 질문

**Q: 마일스톤이 아닌 일반 작업의 바 색상을 어떻게 변경합니까?**  
A: `style.ItemType = BarItemType.Task;` 로 설정하고 `style.BarColor`에 원하는 `Color`를 지정하십시오.

**Q: HTML로 내보낼 때 바를 스타일링하는 데 이 방법을 사용할 수 있나요?**  
A: 예. `HtmlSaveOptions`를 사용하고 `BarStyles` 컬렉션을 동일하게 채우면 됩니다.

**Q: 정의할 수 있는 바 스타일 수에 제한이 있나요?**  
A: 실질적으로 제한은 없으며 필요에 따라 추가할 수 있지만, 매우 큰 컬렉션의 경우 성능을 고려하십시오.

**Q: 스타일을 변경한 후 `project.Calculate()`를 호출해야 하나요?**  
A: 아니요, 스타일은 저장 작업 중에 적용되며 일정 변경에만 재계산이 필요합니다.

---

**마지막 업데이트:** 2026-04-06  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}