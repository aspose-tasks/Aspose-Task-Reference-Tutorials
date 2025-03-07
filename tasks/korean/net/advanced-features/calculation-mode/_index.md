---
title: Aspose.Tasks의 계산 모드
linktitle: Aspose.Tasks의 계산 모드
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 계산 모드를 효과적으로 관리하여 프로젝트 일정 및 작업 종속성을 간소화하는 방법을 알아보세요.
weight: 29
url: /ko/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 계산 모드

## 소개

Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있게 해주는 강력한 API입니다. 프로젝트 파일 작업의 중요한 측면 중 하나는 작업 및 프로젝트 일정이 계산되고 업데이트되는 방식을 결정하는 계산 모드를 관리하는 것입니다. 이 튜토리얼에서는 Aspose.Tasks for .NET에서 지원하는 다양한 계산 모드를 살펴보고 이를 효과적으로 사용하는 방법을 보여줍니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C# 프로그래밍에 대한 기본 이해: C# 프로그래밍 개념을 숙지하세요.

## 네임스페이스 가져오기

.NET용 Aspose.Tasks 작업을 시작하기 전에 필요한 네임스페이스를 가져와 보겠습니다.

```csharp
using Aspose.Tasks;
using System;


```

## 자동 계산 모드 적용

### 1단계: 새 프로젝트 인스턴스 만들기

 새로 초기화`Project` 개체를 설정하고`CalculationMode` 재산`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### 2단계: 프로젝트 시작 날짜 설정 및 작업 추가

프로젝트 시작 날짜를 정의하고 작업을 추가하세요.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3단계: 작업 연결

작업 간의 종속성을 설정합니다.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 4단계: 다시 계산된 날짜 확인

날짜가 자동으로 다시 계산되었는지 확인하세요.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// 필요에 따라 더 많은 확인을 추가하세요.
```

## 수동 계산 모드 적용

### 1단계: 새 프로젝트 인스턴스 만들기

 새로 초기화`Project` 개체를 설정하고`CalculationMode` 재산`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### 2단계: 프로젝트 시작 날짜 설정 및 작업 추가

프로젝트 시작 날짜를 정의하고 작업을 추가하세요.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 3단계: 작업 속성 확인

수동 모드에서 작업 속성이 올바르게 설정되었는지 확인하세요.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// 필요에 따라 더 많은 확인을 추가하세요.
```

### 4단계: 작업 연결 및 날짜 확인

작업을 서로 연결하고 날짜가 다시 계산되지 않는지 확인하세요.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## 없음 계산 모드 적용

### 1단계: 새 프로젝트 인스턴스 만들기

 새로 초기화`Project` 개체를 설정하고`CalculationMode` 재산`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### 2단계: 새 작업 추가

프로젝트에 새 작업을 추가합니다.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### 3단계: 작업 속성 확인

작업 속성이 자동으로 계산되지 않는지 확인하세요.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// 필요에 따라 더 많은 확인을 추가하세요.
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 사용할 수 있는 계산 모드를 살펴보고 이를 실제 시나리오에 적용하는 방법을 배웠습니다. 자동, 수동 또는 계산 없음 모드가 필요한지 여부에 관계없이 Aspose.Tasks는 프로젝트 요구 사항에 맞는 유연성을 제공합니다.

## FAQ

### Q1: 런타임 중에 계산 모드를 동적으로 변경할 수 있습니까?

A1: 예, 런타임 중 언제든지 다음을 수정하여 프로젝트의 계산 모드를 변경할 수 있습니다.`CalculationMode` 재산.

### Q2: Aspose.Tasks는 Microsoft Project 외에 다른 프로젝트 관리 파일 형식을 지원합니까?

A2: Aspose.Tasks는 주로 Microsoft Project 파일 형식에 중점을 두고 있지만 Primavera P6 XML, Primavera DB 및 Asta Powerproject XML과 같은 다른 형식도 지원합니다.

### Q3: Aspose.Tasks는 소규모 및 기업 수준 프로젝트 모두에 적합합니까?

A3: 물론이죠! Aspose.Tasks는 포괄적인 기능과 강력한 API를 통해 소규모 및 기업 수준 프로젝트의 요구 사항을 모두 충족하도록 설계되었습니다.

### Q4: Aspose.Tasks를 다른 .NET 라이브러리 및 프레임워크와 통합할 수 있습니까?

A4: 예, Aspose.Tasks를 다른 .NET 라이브러리 및 프레임워크와 원활하게 통합하여 애플리케이션의 기능을 향상시킬 수 있습니다.

### Q5: Aspose.Tasks 사용자가 사용할 수 있는 커뮤니티 포럼이나 지원 채널이 있습니까?

 A5: 네, 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
