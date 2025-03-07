---
title: Aspose.Tasks의 계산 유형
linktitle: Aspose.Tasks의 계산 유형
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks 라이브러리의 계산 유형을 사용하여 .NET 프로젝트에서 값 계산을 사용자 정의하는 방법을 알아보세요.
weight: 30
url: /ko/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 계산 유형

## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks의 계산 유형 기능을 살펴보겠습니다. Aspose.Tasks는 .NET 개발자가 시스템에 Microsoft Project를 설치할 필요 없이 Microsoft Project 파일로 작업할 수 있도록 하는 강력한 라이브러리입니다. 계산 유형을 사용하면 프로젝트 내의 작업 및 요약 작업에 대한 값이 계산되는 방식을 정의할 수 있습니다.

## 전제조건

시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.

1. C# 및 .NET 프레임워크에 대한 기본 지식
2. 시스템에 Visual Studio가 설치되어 있습니다.
3.  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
4.  참조용으로 .NET 문서용 Aspose.Tasks에 액세스 가능[여기](https://reference.aspose.com/tasks/net/).

## 네임스페이스 가져오기

예제를 살펴보기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;


```

## 1단계: 새 프로젝트 만들기

먼저 새 프로젝트 개체를 만들어 보겠습니다.

```csharp
var project = new Project();
```

## 2단계: 작업 추가

이제 프로젝트에 작업을 추가해 보겠습니다.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 3단계: 확장 속성에 대한 계산 유형 정의

계산 유형을 수식으로 설정하여 확장된 속성 정의를 생성하겠습니다.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 4단계: 요약 행에 대한 계산 유형 정의

다음으로 요약 작업의 값이 평균 롤업 유형을 사용하여 계산되는 또 다른 확장된 특성 정의를 만듭니다.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 계산 유형을 사용하여 작업하는 방법을 살펴보았습니다. 확장된 속성에 대한 계산 유형을 정의함으로써 프로젝트 내의 작업 및 요약 작업에 대한 값이 계산되는 방식을 사용자 정의하여 유연성과 제어력을 높일 수 있습니다.

## FAQ

### Q1: Aspose.Tasks의 계산 유형은 무엇입니까?

A1: Aspose.Tasks의 계산 유형은 프로젝트 내의 작업 및 요약 작업에 대한 값이 계산되는 방법을 결정하고 수식 및 롤업과 같은 옵션을 제공합니다.

### Q2: 확장 속성에 대한 계산 유형을 어떻게 설정합니까?

대답 2: 그에 따라 CalculationType 속성을 정의하여 확장 특성에 대한 계산 유형을 설정할 수 있습니다.

### Q3: 프로젝트의 요약 행에 대한 계산 유형을 사용자 지정할 수 있습니까?

A3: 예, Aspose.Tasks를 사용하면 요약 행에 대한 계산 유형을 지정할 수 있으므로 요구 사항에 따라 값 계산을 맞춤화할 수 있습니다.

### Q4: 요약 작업 계산에 사용할 수 있는 다양한 롤업 유형이 있습니까?

A4: 예, Aspose.Tasks는 요약 작업의 값을 계산하기 위해 평균, 합계 및 개수와 같은 다양한 롤업 유형을 제공합니다.

### Q5: Aspose.Tasks for .NET에 대한 추가 리소스는 어디서 찾을 수 있나요?

 A5: 다음에서 제공되는 문서 및 커뮤니티 지원 포럼을 탐색할 수 있습니다.[.NET용 Aspose.Tasks](https://reference.aspose.com/tasks/net/) 포괄적인 지도와 지원을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
