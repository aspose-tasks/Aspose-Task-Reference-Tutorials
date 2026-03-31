---
date: 2026-03-21
description: Aspose.Tasks for .NET를 사용하여 리소스의 가용 기간을 관리하고 효과적인 프로젝트 리소스 가용성을 달성하는
  방법을 배웁니다. 이 단계별 가이드는 가용 기간을 추가, 업데이트 및 제거하는 방법을 보여줍니다.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 프로젝트 리소스 가용성 – Aspose.Tasks에서 가용 기간 관리
url: /ko/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 리소스 가용성: Aspose.Tasks에서 가용 기간 컬렉션

**프로젝트 리소스 가용성**을 관리하는 것은 성공적인 프로젝트 계획의 핵심 요소입니다. 이 튜토리얼에서는 Aspose.Tasks for .NET API를 사용하여 프로젝트를 로드하고 리소스 간 기간을 복사하는 단계별 방법으로 **가용성을 관리하는 방법**을 배웁니다.

## Quick Answers
- **가용 기간의 주요 클래스는 무엇인가요?** `AvailabilityPeriod` ( `Aspose.Tasks` 네임스페이스).  
- **기존 기간을 삭제할 수 있나요?** 예, `resource.AvailabilityPeriods.Clear()`를 호출하면 됩니다.  
- **새 기간을 추가하려면 어떻게 하나요?** `AvailabilityPeriod` 객체를 생성하고 `Add` 또는 `Insert`를 사용합니다.  
- **다른 리소스로 기간을 복사할 수 있나요?** 물론입니다 – `CopyTo`를 사용한 뒤 각 항목을 대상 리소스에 추가하면 됩니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 예, 비시험 배포에는 상용 Aspose.Tasks 라이선스가 필요합니다.

## 프로젝트 리소스 가용성이란?
프로젝트 리소스 가용성은 리소스가 작업에 할당될 수 있는 날짜와 단위(용량 비율)를 정의합니다. 이러한 기간을 제어함으로써 과다 할당을 방지하고 일정 정확성을 높일 수 있습니다.

## 왜 Aspose.Tasks를 사용해 가용 기간을 관리해야 할까요?
- **전체 .NET 통합** – COM 인터옵 없이 순수 관리 코드.  
- **세밀한 제어** – 정확한 시작/종료 날짜와 소수 단위를 설정 가능.  
- **간편한 복사** – 수동 파싱 없이 리소스 간 가용 데이터 이동.  
- **성능 최적화** – 대용량 MPP 파일도 효율적으로 처리.

## Prerequisites
1. **Visual Studio** – 최신 버전(2019, 2022 등) 중 하나.  
2. **Aspose.Tasks for .NET** – [여기](https://releases.aspose.com/tasks/net/)에서 다운로드.  
3. **Basic C# knowledge** – 클래스, 컬렉션, LINQ에 익숙해야 합니다.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

우리는 핵심 Aspose.Tasks 네임스페이스와 이후에 필요할 표준 .NET 컬렉션을 가져옵니다.

## Step 1: Initialize the Project and Resource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

여기서는 기존 MPP 파일을 로드하고 가용성을 편집하려는 리소스(ID = 1)를 가져옵니다.

## Step 2: Clear Existing Availability Periods

```csharp
resource.AvailabilityPeriods.Clear();
```

클리어 작업은 이전에 정의된 모든 기간을 제거하여 깨끗한 상태로 만듭니다.

## Step 3: Add Availability Periods

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

`AvailabilityPeriod` 객체 컬렉션을 가져온 뒤(`GetPeriods` 헬퍼는 별도로 정의된 것으로 가정) 각각을 추가합니다. 컬렉션이 쓰기 가능한지 확인합니다.

## Step 4: Insert a New Availability Period

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

이 코드는 2013년을 위한 사용자 정의 기간을 생성하고, 이미 존재하지 않을 경우 위치 1(두 번째 슬롯)에 삽입합니다.

## Step 5: Display Availability Periods

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

간단한 콘솔 출력으로 전체 개수와 각 기간의 상세 정보를 표시합니다 – 디버깅이나 검증에 유용합니다.

## Step 6: Copy Availability Periods to Another Resource

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

전체 컬렉션을 배열로 복사하고, 대상 리소스의 기간을 클리어한 뒤 다시 채웁니다. 이는 리소스 간 가용 데이터를 복제하는 방법을 보여줍니다.

## Step 7: Update and Remove Availability Periods

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

여기서는 마지막에서 두 번째 기간의 `AvailableUnits`를 조정하고, 앞서 추가한 2013년 기간을 삭제합니다.

## Common Issues and Solutions
- **Read‑only collection error** – 프로젝트가 읽기 전용 모드로 열려 있지 않은지 확인하거나 새 항목을 추가하기 전에 `resource.AvailabilityPeriods.Clear()`를 호출했는지 확인하세요.  
- **Overlapping periods** – Aspose.Tasks는 겹치는 기간을 자동으로 병합하지 않으므로, 겹침을 감지하고 해결하는 사용자 정의 로직을 작성해야 할 수 있습니다.  
- **Incorrect date format** – 항상 `DateTime` 객체를 사용하세요; 문자열 파싱은 로케일에 따라 버그를 일으킬 수 있습니다.

## Frequently Asked Questions

**Q: 가용 기간에 사용자 정의 필드를 추가할 수 있나요?**  
A: 아니요, Aspose.Tasks for .NET의 가용 기간은 사용자 정의 필드를 지원하지 않습니다.

**Q: 가용 기간이 특정 작업에 연결되어 있나요?**  
A: 아니요, 가용 기간은 리소스에 연결되며 리소스가 일반적으로 작업에 할당될 수 있는 시점을 정의합니다.

**Q: 외부 소스에서 가용 기간을 가져올 수 있나요?**  
A: 예, CSV, XML 또는 데이터베이스에서 `AvailabilityPeriod` 객체를 생성하고 컬렉션에 추가하면 됩니다.

**Q: 겹치는 가용 기간을 어떻게 처리하나요?**  
A: 겹침은 자동으로 해결되지 않으므로, 충돌 기간을 병합하거나 거부하는 사용자 정의 검증 로직을 구현해야 합니다.

**Q: 리소스가 가질 수 있는 가용 기간 수에 제한이 있나요?**  
A: 하드코딩된 제한은 없지만, 매우 큰 컬렉션은 성능에 영향을 줄 수 있으므로 가능한 경우 기간을 통합하는 것이 좋습니다.

## Conclusion

이 가이드에서는 Aspose.Tasks for .NET을 사용하여 **프로젝트 리소스 가용성**을 관리하는 모든 방법을 다루었습니다—프로젝트 초기화 및 기존 데이터 정리부터 기간 추가, 삽입, 복사, 업데이트 및 삭제까지. 이러한 단계를 마스터하면 리소스 캘린더를 정확하게 유지하고 프로젝트 일정의 현실성을 높일 수 있습니다.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}