---
date: 2026-04-06
description: Aspose.Tasks for .NET를 사용하여 프로젝트에 리소스를 추가하고 리소스 가용 기간을 설정하는 방법을 배웁니다.
  리소스 캘린더 관리에 대한 단계별 가이드.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Aspose.Tasks에서 가용 기간 작업하기
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 프로젝트에 리소스 추가 및 가용성 설정
url: /ko/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트에 리소스 추가 및 Aspose.Tasks에서 가용성 설정

## 소개

이 튜토리얼에서는 **프로젝트에 리소스를 추가하는 방법**을 배우고, Aspose.Tasks .NET 라이브러리를 사용하여 해당 리소스의 가용 기간을 정의하는 방법을 배웁니다. 리소스 캘린더를 관리하는 것은 현실적인 프로젝트 일정에 필수적이며, 아래 단계에서는 프로젝트 인스턴스를 생성하고 각 기간의 세부 정보를 출력하는 전체 과정을 안내합니다.

## 빠른 답변
- **주요 목표는 무엇인가요?** 프로젝트에 리소스를 추가하고 가용 기간을 구성합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for .NET.  
- **프로덕션에 라이선스가 필요합니까?** 예, 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **구현 시간은?** 기본 시나리오의 경우 일반적으로 15분 미만입니다.

## “프로젝트에 리소스 추가”란 무엇인가요?

프로젝트에 리소스를 추가하면 작업에 할당할 수 있는 사람, 장비 또는 자재에 대한 자리표시자가 생성됩니다. 리소스가 생성되면 **리소스 가용성 설정**을 하고 작업 캘린더를 정의하여 스케줄러가 해당 제약 조건을 준수하도록 할 수 있습니다.

## 작업 일정 및 가용 기간을 구성해야 하는 이유

- **정확한 계획:** 리소스가 실제로 비어 있을 때만 작업이 일정에 배정됩니다.
- **비용 관리:** 가용성 단위는 파트타임 작업량을 나타내어 인건비를 정확히 계산하는 데 도움이 됩니다.
- **리소스 레벨링:** 엔진은 각 리소스의 캘린더를 알면 과다 할당을 자동으로 레벨링할 수 있습니다.

## 전제 조건

1. Visual Studio (또는 .NET 호환 IDE).  
2. Aspose.Tasks for .NET – [here](https://releases.aspose.com/tasks/net/)에서 다운로드.  
3. 기본 C# 지식.

## 네임스페이스 가져오기

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 프로젝트에 리소스를 추가하는 방법

### 단계 1: 새로운 `Project` 인스턴스 만들기

```csharp
var project = new Project();
```

이 객체는 메모리 내 전체 프로젝트 파일을 나타냅니다.

### 단계 2: 프로젝트에 리소스 추가

```csharp
var resource = project.Resources.Add("Work Resource");
```

이 호출은 *Work Resource*라는 **리소스**를 생성하며, 이후 작업에 연결할 수 있습니다.

### 단계 3: 가용 기간 정의

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()`는 구현이 표시되지 않은 헬퍼 메서드로, `AvailabilityPeriod` 객체 컬렉션을 반환합니다. 각 기간은 시작 날짜, 종료 날짜 및 리소스가 가용한 단위(전체 시간 대비 비율)를 지정합니다.

### 단계 4: 기간을 리소스에 추가

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

여기서는 컬렉션을 순회하면서 각 기간을 리소스 캘린더에 추가하여 **리소스 가용성 설정**을 수행합니다.

### 단계 5: 가용성 세부 정보 표시

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

콘솔 출력으로 기간이 올바르게 저장되었는지 확인할 수 있습니다.

## 일반적인 함정 및 팁

- **날짜 정밀도:** `AvailableFrom` 및 `AvailableTo`는 `DateTime` 값이며, 전체 일 기간을 원한다면 자정을 기준으로 설정해야 합니다.
- **단위 범위:** 유효 값은 0‑100 %이며, 이 범위를 벗어나면 예외가 발생합니다.
- **중복 기간:** 중복된 기간은 자동으로 병합되지만, 구분해서 유지하는 것이 명확합니다.

## 자주 묻는 질문

### Q1: Aspose.Tasks for .NET를 상업 프로젝트에 사용할 수 있나요?
A1: 예, Aspose.Tasks for .NET는 상업 프로젝트에 사용할 수 있습니다. 라이선스는 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

### Q2: Aspose.Tasks for .NET에 대한 무료 체험이 있나요?
A2: 예, Aspose.Tasks for .NET의 무료 체험을 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

### Q3: Aspose.Tasks for .NET 문서는 어디에서 찾을 수 있나요?
A3: 문서는 [here](https://reference.aspose.com/tasks/net/)에서 확인할 수 있습니다.

### Q4: Aspose.Tasks for .NET에 대한 지원은 어떻게 받을 수 있나요?
A4: 커뮤니티 포럼 [here](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

### Q5: Aspose.Tasks for .NET에 대한 임시 라이선스를 제공하나요?
A5: 예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 이용할 수 있습니다.

---

**마지막 업데이트:** 2026-04-06  
**테스트 환경:** Aspose.Tasks for .NET (latest stable release)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}