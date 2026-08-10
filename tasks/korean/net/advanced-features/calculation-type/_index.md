---
date: 2026-03-24
description: Aspose.Tasks for .NET에서 계산 설정 방법을 배우고, 요약 값 계산, 계산식 정의 및 롤업 요약 구성을 예제로
  확인하세요.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 계산 유형 설정 방법
url: /ko/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 계산 유형 설정 방법

## 소개

Microsoft Project 파일에서 작업 및 요약 행에 대한 **계산 규칙**을 설정해야 하는 경우, 이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 정확히 어떻게 하는지 보여줍니다. 전체 **계산 유형 예제**를 단계별로 진행하고, **요약 값 계산** 방법을 시연하며, **계산 수식 정의**와 **확장 속성에 대한 롤업 요약 구성** 방법을 설명합니다. 마지막까지 진행하면 프로젝트에 작업을 추가하고, 사용자 지정 계산 로직을 설정하며, 롤업 동작을 자신 있게 제어할 수 있게 됩니다.

## 빠른 답변
- **주된 목적은 무엇인가요?** 프로젝트 파일에서 작업 및 요약 값이 어떻게 계산되는지를 제어하기 위함입니다.  
- **어떤 API 클래스를 사용하나요?** `ExtendedAttributeDefinition`와 `CalculationType`, `SummaryRowsCalculationType`을 함께 사용합니다.  
- **수식을 사용할 수 있나요?** 예, `CalculationType = CalculationType.Formula` 로 설정하고 수식 문자열을 제공하면 됩니다.  
- **요약 값을 롤업하려면 어떻게 하나요?** `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` 로 설정하고 `Average`와 같은 `RollupType`을 지정합니다.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## Calculation Type이란 무엇이며, 어떻게 설정하나요?

`CalculationType`은 Aspose.Tasks가 확장 속성의 값을 어떻게 계산할지를 지정합니다. 정적 값, 수식, 또는 하위 작업의 값을 롤업하는 옵션 중 하나를 선택할 수 있습니다. 프로젝트가 수동 업데이트 없이 맞춤 비즈니스 규칙을 반영하도록 하려면 계산 설정을 올바르게 하는 것이 중요합니다.

## 요약 값을 계산하기 위해 calculation type을 사용하는 이유는?

프로젝트에 요약 작업이 포함된 경우, 종종 요약 행에 집계 데이터(예: 총 비용, 평균 기간)를 표시해야 합니다. `SummaryRowsCalculationType`과 `RollupType`을 통해 **요약 값 계산**을 구성하면, 개별 작업을 수정할 때마다 Aspose.Tasks가 자동으로 해당 집계를 동기화합니다.

## 사전 요구 사항

시작하기 전에 다음을 준비하세요:

1. C# 및 .NET 프레임워크에 대한 기본 지식.  
2. 최신 버전의 Visual Studio가 설치된 컴퓨터.  
3. Aspose.Tasks for .NET 라이브러리 설치 – [여기](https://releases.aspose.com/tasks/net/)에서 다운로드할 수 있습니다.  
4. 공식 Aspose.Tasks for .NET 문서 – [여기](https://reference.aspose.com/tasks/net/)에서 확인하세요.

## 네임스페이스 가져오기

예제를 진행하기 전에 필요한 네임스페이스를 가져와야 합니다:

```csharp
using Aspose.Tasks;
using System;
```

## 1단계: 새 Project 만들기

먼저 작업 및 사용자 지정 속성을 보관할 빈 `Project` 객체를 생성합니다.

```csharp
var project = new Project();
```

## 2단계: 프로젝트에 작업 추가하기

이제 **작업 프로젝트** 데이터를 추가합니다. 간단한 작업을 만들고 시작 날짜를 설정한 뒤, 기간을 하루로 지정합니다.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 3단계: 확장 속성에 대한 Calculation Type 정의 (수식 예제)

여기서는 수식으로 값을 계산하는 확장 속성 정의를 생성합니다. 이는 **계산 유형 예제**를 보여주며 **계산 수식 정의** 방법을 설명합니다.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 4단계: 요약 행에 대한 Calculation Type 정의 (롤업 요약 구성)

다음으로, Aspose.Tasks가 *Average* 롤업 유형을 사용하도록 **롤업 요약 구성**을 지정하는 또 다른 확장 속성 정의를 만듭니다. 이는 비용, 작업량 또는 사용자 지정 필드에 대한 **요약 값 계산**의 일반적인 방법입니다.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 일반적인 문제 및 해결 방법

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 수식이 `null`을 반환 | 수식 내 필드 참조 오류 | 괄호 안의 필드 이름을 확인하세요(예: `[Start]`가 `[stARt]`가 아니어야 함). |
| 요약 행에 0이 표시 | `SummaryRowsCalculationType`이 설정되지 않았거나 잘못된 `RollupType` 사용 | `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup`을 설정하고 적절한 `RollupType`을 선택하세요. |
| 속성을 추가한 뒤 프로젝트 로드 실패 | 속성 정의와 작업 사용 간 불일치 | 속성을 **작업에 할당하기 전에** 먼저 정의하세요. |

## 결론

이 튜토리얼에서는 Aspose.Tasks for .NET에서 **계산 규칙 설정** 방법을 다루었습니다. 간단한 작업 생성부터 수식 기반 및 롤업 기반 계산 유형 정의까지 살펴보았습니다. 이러한 설정을 마스터하면 **요약 값 계산**을 정밀하게 제어할 수 있어, 수동 스프레드시트 작업 없이도 풍부한 프로젝트 분석이 가능합니다.

## FAQ

### Q1: Aspose.Tasks에서 Calculation Type이란 무엇인가요?

A1: Aspose.Tasks의 Calculation Type은 프로젝트 내 작업 및 요약 작업에 대한 값이 어떻게 계산되는지를 결정하며, Formula와 Rollup과 같은 옵션을 제공합니다.

### Q2: 확장 속성에 대한 Calculation Type을 어떻게 설정하나요?

A2: 해당 확장 속성의 `CalculationType` 속성을 적절히 지정하면 됩니다.

### Q3: 프로젝트의 요약 행에 대한 Calculation Type을 사용자 지정할 수 있나요?

A3: 예, Aspose.Tasks를 사용하면 요약 행에 대한 Calculation Type을 지정하여 요구 사항에 맞게 값 계산을 맞춤화할 수 있습니다.

### Q4: 요약 작업 계산을 위한 다양한 Rollup Type이 있나요?

A4: 예, Aspose.Tasks는 Average, Sum, Count 등 여러 Rollup Type을 제공하여 요약 작업의 값을 계산합니다.

### Q5: Aspose.Tasks for .NET에 대한 추가 자료는 어디서 찾을 수 있나요?

A5: 포괄적인 가이드와 지원을 위해 [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) 문서 및 커뮤니티 포럼을 확인하세요.

---

**마지막 업데이트:** 2026-03-24  
**테스트 환경:** Aspose.Tasks for .NET (최신 릴리스)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}