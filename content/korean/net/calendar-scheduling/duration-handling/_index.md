---
title: Aspose.Tasks의 기간 처리
linktitle: Aspose.Tasks의 기간 처리
second_title: Aspose.태스크 .NET API
description: 단계별 튜토리얼을 통해 Aspose.Tasks for .NET에서 기간을 효과적으로 처리하는 방법을 알아보세요.
type: docs
weight: 30
url: /ko/net/calendar-scheduling/duration-handling/
---
## 소개

프로젝트 관리 애플리케이션에서는 기간을 효과적으로 처리하는 것이 중요합니다. Aspose.Tasks for .NET은 기간을 효율적으로 관리하기 위한 강력한 기능을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 기간 처리의 다양한 측면을 살펴보겠습니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. C#에 대한 기본 지식: 예제를 이해하고 구현하려면 C# 프로그래밍 언어에 대한 지식이 필수적입니다.
2. Visual Studio: Visual Studio IDE를 설치하여 .NET 애플리케이션을 만들고 실행합니다.
3.  .NET용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기

먼저 Aspose.Tasks 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.

## 작업 기간 업데이트

### 1단계: 프로젝트 파일 로드

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2단계: 작업 및 기간 가져오기

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 3단계: 업데이트 기간

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 4단계: 업데이트된 기간 표시

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 작업 기간 빼기

### 1단계: 프로젝트 파일 로드

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2단계: 작업 및 기간 가져오기

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 3단계: 기간 빼기

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 4단계: 업데이트된 기간 표시

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 기간을 TimeSpan으로 변환

### 1단계: 프로젝트 파일 로드

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2단계: 작업 및 기간 가져오기

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3단계: 기간을 TimeSpan으로 변환

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## 기간을 문자열로 변환

### 1단계: 프로젝트 파일 로드

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 2단계: 작업 및 기간 가져오기

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 3단계: 기간을 문자열로 변환

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 기간 처리의 다양한 측면을 다루었습니다. 성공적인 프로젝트 관리를 위해서는 기간을 이해하고 효과적으로 관리하는 것이 중요합니다. Aspose.Tasks는 .NET 애플리케이션에서 기간 관리 작업을 단순화하는 포괄적인 기능을 제공합니다.

## FAQ

### Q1: .NET용 Aspose.Tasks란 무엇입니까?

A1: Aspose.Tasks for .NET은 .NET 애플리케이션에서 Microsoft Project 파일 작업을 위한 강력한 라이브러리입니다.

### Q2: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?

A2: 예, Aspose.Tasks는 조작을 위한 광범위한 API를 제공하여 복잡한 프로젝트 구조를 쉽게 처리할 수 있습니다.

### Q3: .NET용 Aspose.Tasks는 .NET Core와 호환됩니까?

A3: 예, .NET용 Aspose.Tasks는 .NET Core와 호환되므로 크로스 플랫폼 애플리케이션에서 사용할 수 있습니다.

### Q4: Aspose.Tasks는 Microsoft Project 파일 읽기 및 쓰기를 지원합니까?

A4: 예, Aspose.Tasks는 MPP, XML 및 MPX를 포함한 다양한 형식의 Microsoft Project 파일 읽기 및 쓰기를 지원합니다.

### Q5: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?

 A5: 예, 다음 사이트에서 Aspose.Tasks for .NET 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).