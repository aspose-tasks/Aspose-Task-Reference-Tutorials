---
date: 2026-03-14
description: Aspose.Tasks for .NET에서 null 허용 부울을 사용하는 방법을 배우고, null 허용 부울 값을 변환하고
  null 허용 부울 속성을 설정하는 방법을 포함합니다.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 Nullable Boolean 사용 방법
url: /ko/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 Nullable Boolean 사용 방법

이 튜토리얼에서는 Aspose.Tasks .NET API를 사용할 때 **nullable** Boolean을 사용하는 방법을 보여줍니다. Nullable Boolean은 `true`, `false`, 또는 *undefined*의 세 가지 상태를 가질 수 있어, 명시적으로 지정되지 않을 수 있는 프로젝트 수준 설정에 특히 유용합니다. Nullable Boolean 값을 생성, 변환 및 **설정**하는 방법과, 이를 올바르게 처리하면 일정 관리 애플리케이션에서 예상치 못한 동작을 방지할 수 있는 이유를 확인하게 됩니다.

## Quick Answers
- **Nullable Boolean이란?** `true`, `false` 또는 정의되지 않음(undefined)을 가질 수 있는 타입입니다.  
- **Aspose.Tasks에서 Nullable Boolean을 사용하는 이유는?** 기본값을 추측하지 않고 선택적 프로젝트 속성을 표현할 수 있습니다.  
- **Nullable Boolean을 일반 bool로 변환하려면?** 암시적 변환을 사용하거나 먼저 `IsDefined`를 확인합니다.  
- **주요 클래스는?** `Aspose.Tasks` 네임스페이스의 `NullableBool`입니다.  
- **라이선스가 필요한가요?** 예, 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## Nullable Boolean이란?

Nullable Boolean(`NullableBool`)은 일반 `bool` 타입에 *IsDefined* 플래그를 추가한 형태입니다. `IsDefined`가 `false`이면 값이 정의되지 않은 것으로 간주되어 “false”와 “설정되지 않음”을 구분할 수 있습니다.

## 프로젝트 설정에서 Nullable Boolean을 처리해야 하는 이유

많은 프로젝트 옵션—예: **ActualsInSync** 또는 **HonorConstraints**—은 선택 사항입니다. 일반 `bool`을 사용하면 `true` 또는 `false` 중 하나를 선택해야 하므로 사용자의 의도를 무심코 덮어쓸 수 있습니다. **Nullable Boolean을 처리**함으로써 원래 상태를 보존하고 의도치 않은 구성 변경을 방지할 수 있습니다.

## Prerequisites

시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. **Visual Studio**(또는 .NET 호환 IDE).  
2. **Aspose.Tasks for .NET** – [여기](https://releases.aspose.com/tasks/net/)에서 다운로드합니다.

## Import Namespaces

먼저 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

이제 각 예제를 단계별로 살펴보겠습니다.

## Working with `NullableBool`

### Step 1: Create a new `Project` instance.

```csharp
var project = new Project();
```

### Step 2: Instantiate a `NullableBool` object with specified values.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Step 3: Check the value and defined status of the `NullableBool` object.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Step 4: **Set nullable boolean** on the project.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Step 5: Instantiate another `NullableBool` object with a single value.

```csharp
var honorConstraints = new NullableBool(true);
```

### Step 6: Display the string representation of the `NullableBool` object.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Step 7: Use the `NullableBool` instance by setting it in the project.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Comparing `NullableBool` Instances

### Step 1: Instantiate two `NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Step 2: Check the string representation of each `NullableBool` object.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Step 3: Implicit conversion to `bool` and print the result.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Step 4: Compare the two `NullableBool` objects for equality.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Getting the Hash Code of `NullableBool`

### Step 1: Instantiate two `NullableBool` objects.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Step 2: Print the hash code for each `NullableBool` object.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Common Pitfalls & Tips

- **Nullable Boolean이 정의되었다고 가정하지 마세요.** `Value`를 사용하기 전에 항상 `IsDefined`를 확인합니다.  
- **정의되지 않은 값을 일반 bool로 변환**하면 예외가 발생할 수 있습니다. 정의된 경우에만 암시적 변환을 사용하세요.  
- **프로젝트 속성을 설정할 때**는 필요에 따라 정의되지 않은 상태를 유지하기 위해 `NullableBool`을 사용해 `Set` 메서드를 호출합니다.

## Frequently Asked Questions

**Q: Nullable Boolean이란 무엇인가요?**  
A: Nullable Boolean은 `true`, `false`, 또는 정의되지 않은 상태를 나타낼 수 있어 세 가지 결과를 구분할 수 있습니다.

**Q: Nullable Boolean을 일반 bool로 안전하게 변환하려면 어떻게 해야 하나요?**  
A: 먼저 `IsDefined`를 확인한 뒤 `Value` 속성을 사용하거나, 정의된 경우에만 암시적 변환을 사용합니다.

**Q: Aspose.Tasks에서 일반 bool 대신 Nullable Boolean을 사용해야 하는 이유는?**  
A: 선택적 프로젝트 설정을 그대로 두어 의도치 않은 오버라이드를 방지할 수 있기 때문입니다.

**Q: Nullable Boolean을 undefined 상태로 설정할 수 있나요?**  
A: 예—정의 플래그만 받는 생성자를 사용합니다. 예: `new NullableBool(false, false)`.

**Q: Aspose.Tasks for .NET에 대한 추가 문서는 어디서 찾을 수 있나요?**  
A: 자세한 문서는 [여기](https://reference.aspose.com/tasks/net/)에서 확인할 수 있습니다.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}