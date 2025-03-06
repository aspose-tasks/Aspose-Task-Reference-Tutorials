---
title: Aspose.Tasks 레이아웃 빌더를 사용하여 메모리 예외 처리
linktitle: Aspose.Tasks 레이아웃 빌더를 사용하여 메모리 예외 처리
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks Layout Builder를 효율적으로 사용하여 .NET에서 메모리 예외를 처리하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 12
url: /ko/net/advanced-features/layout-builder-out-of-memory/
---
## 소개

모든 소프트웨어 응용 프로그램이 원활하게 작동하려면 메모리 예외를 처리하는 것이 중요합니다. .NET용 Aspose.Tasks로 작업할 때 개발자는 특히 대규모 프로젝트나 복잡한 레이아웃을 처리할 때 메모리 관련 문제에 직면하는 경우가 많습니다. 이 튜토리얼에서는 Aspose.Tasks Layout Builder를 사용하여 메모리 예외를 효과적으로 처리하는 방법을 살펴보겠습니다.

## 전제조건

이 튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

1. C# 프로그래밍에 대한 기본 지식: 이 자습서에서는 C# 구문 및 개념에 익숙하다고 가정합니다.
2.  .NET용 Aspose.Tasks 설치: 개발 환경에 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
3. IDE(통합 개발 환경): 코딩 및 컴파일을 위해 Visual Studio와 같은 IDE를 설치합니다.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져옵니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

Aspose.Tasks Layout Builder를 사용하여 메모리 예외를 효과적으로 처리하는 방법을 이해하기 위해 제공된 예제 코드를 여러 단계로 분석해 보겠습니다.

## 1단계: 프로젝트 로드

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

 이 단계에서는 프로젝트 파일 "Blank2010.mpp"를 인스턴스로 로드합니다.`Project` 수업.

## 2단계: 간트 차트 보기 사용자 정의

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

여기서는 더 나은 시각화를 위해 시간 척도 단위와 개수를 조정하여 간트 차트 보기를 사용자 정의합니다.

## 3단계: 이미지 저장 옵션 구성

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

 이 단계에서는 다음의 인스턴스를 생성합니다.`ImageSaveOptions` 출력 이미지의 형식과 기간 설정을 지정합니다.

## 4단계: 프로젝트를 이미지로 저장

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

마지막으로 지정된 옵션으로 프로젝트를 저장합니다. 프로젝트가 너무 크거나 복잡한 경우 메모리 예외가 발생할 수 있는 곳입니다.

## 5단계: 예외 처리

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

여기에서는 메모리 및 비트맵 크기와 관련된 특정 예외를 포착하고 처리하여 적절한 오류 메시지 또는 처리 논리를 제공합니다.

## 결론

이 단계별 가이드를 따르면 .NET 애플리케이션에서 Aspose.Tasks Layout Builder로 작업할 때 메모리 예외를 효과적으로 처리할 수 있습니다. 리소스 사용을 최적화하고 프로젝트의 복잡성을 고려하여 메모리 관련 문제를 완화하는 것을 잊지 마십시오.

## FAQ

### Q1: .NET용 Aspose.Tasks란 무엇입니까?

A1: Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다.

### Q2: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A2: 다음 사이트를 방문하여 Aspose.Tasks에 대한 임시 라이선스를 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### Q3: Aspose.Tasks는 대규모 프로젝트 파일을 처리하는 데 적합합니까?

A3: 예, Aspose.Tasks는 대규모 프로젝트 파일을 효율적으로 처리할 수 있는 기능과 최적화를 제공하지만 개발자는 여전히 메모리 관리 전략을 고려해야 합니다.

### Q4: Aspose.Tasks를 사용하여 Gantt 차트의 모양을 사용자 지정할 수 있나요?

A4: 물론이죠! Aspose.Tasks는 요구 사항에 따라 Gantt 차트의 모양과 레이아웃을 사용자 정의할 수 있는 광범위한 기능을 제공합니다.

### Q5: Aspose.Tasks에 대한 추가 도움말과 지원은 어디서 찾을 수 있나요?

 A5: 다음에서 더 많은 도움과 지원을 찾을 수 있을 뿐만 아니라 커뮤니티에 참여할 수도 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).