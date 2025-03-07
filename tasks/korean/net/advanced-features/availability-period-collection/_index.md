---
title: Aspose.Tasks의 가용성 기간 수집
linktitle: Aspose.Tasks의 가용성 기간 수집
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 리소스의 가용성 기간을 관리하는 방법을 알아보세요. 이 단계별 튜토리얼은 가용성 기간을 추가, 업데이트, 제거하는 과정을 안내하여 효과적인 프로젝트 자원 계획을 보장합니다.
weight: 18
url: /ko/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 가용성 기간 수집

## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET에서 리소스의 가용성 기간 컬렉션을 사용하여 작업하는 방법을 살펴보겠습니다. 가용성 기간 관리는 프로젝트 관리에 매우 중요하므로 프로젝트 내 작업에 리소스를 사용할 수 있는 시기를 정의할 수 있습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. 기본 이해: C# 및 .NET 프레임워크에 대한 지식.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 프로젝트로 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

예제 코드를 여러 단계로 나누어 각 부분을 이해해 보겠습니다.

## 1단계: 프로젝트 및 리소스 초기화

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

여기서는 프로젝트 파일을 로드하고 해당 ID로 특정 리소스를 가져옵니다.

## 2단계: 기존 가용성 기간 지우기

```csharp
resource.AvailabilityPeriods.Clear();
```

리소스와 관련된 기존 가용성 기간을 모두 지웁니다.

## 3단계: 가용성 기간 추가

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

가용성 기간 모음을 반복하여 리소스에 추가합니다.

## 4단계: 새 가용성 기간 삽입

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

2013년에 대한 새로운 가용성 기간을 생성하고 이를 컬렉션에 삽입합니다.

## 5단계: 사용 가능 기간 표시

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

리소스와 관련된 각 가용성 기간의 개수와 세부 정보를 인쇄합니다.

## 6단계: 가용성 기간을 다른 리소스에 복사

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

한 리소스에서 다른 리소스로 가용성 기간을 복사합니다.

## 7단계: 가용성 기간 업데이트 및 제거

```csharp
// 특정 기간 동안 사용 가능한 단위 업데이트
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// 특정 기간 삭제
otherResource.AvailabilityPeriods.Remove(period2013);
```

특정 기간에 사용 가능한 단위를 업데이트하고 컬렉션에서 특정 기간을 제거합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 가용성 기간 컬렉션을 사용하는 방법을 배웠습니다. 효과적인 프로젝트 계획 및 실행을 위해서는 자원 가용성 관리가 필수적입니다.

## FAQ

### Q1: 가용성 기간에 사용자 정의 필드를 추가할 수 있습니까?

A1: 아니요, Aspose.Tasks for .NET의 가용성 기간은 사용자 정의 필드를 지원하지 않습니다.

### Q2: 가용성 기간이 특정 작업과 연결되어 있습니까?

A2: 아니요, 가용성 기간은 리소스와 연관되어 있으며 일반적으로 작업에 사용할 수 있는 시기를 정의합니다.

### Q3: 외부 소스에서 가용성 기간을 가져올 수 있나요?

A3: 예, .NET API용 Aspose.Tasks를 사용하여 다양한 데이터 소스에서 가용성 기간을 가져올 수 있습니다.

### Q4: 중복되는 가용성 기간을 어떻게 처리합니까?

A4: .NET용 Aspose.Tasks는 겹치는 기간을 처리하는 기본 제공 메커니즘을 제공하지 않습니다. 이러한 시나리오를 관리하려면 사용자 지정 논리를 구현해야 할 수도 있습니다.

### Q5: 리소스가 가질 수 있는 가용성 기간에 제한이 있습니까?

대답 5: 리소스가 가질 수 있는 가용성 기간 수에는 미리 정의된 제한이 없지만 기간이 많으면 성능이 저하될 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
