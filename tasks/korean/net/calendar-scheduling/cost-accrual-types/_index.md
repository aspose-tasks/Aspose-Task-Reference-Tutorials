---
title: Aspose.Tasks의 비용 발생 유형
linktitle: Aspose.Tasks의 비용 발생 유형
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 프로젝트 비용을 효과적으로 관리하는 방법을 알아보세요. 정확한 예산 추적을 위해 비용 발생 유형을 정의합니다.
weight: 19
url: /ko/net/calendar-scheduling/cost-accrual-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 비용 발생 유형

## 소개

프로젝트 관리에서 비용을 정확하게 추적하는 것은 예산 통제를 유지하고 프로젝트 성공을 보장하는 데 중요합니다. Aspose.Tasks for .NET은 다양한 비용 발생 유형을 정의하는 기능을 포함하여 프로젝트 비용을 관리하기 위한 강력한 도구 세트를 제공합니다. 이 튜토리얼은 Aspose.Tasks for .NET을 사용하여 비용 발생 유형을 이해하고 구현하는 과정을 안내합니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET용 Aspose.Tasks 설치

 시작하려면 개발 환경에 Aspose.Tasks for .NET을 설치해야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/tasks/net/) 제공된 설치 지침을 따르십시오.

### 2. .NET Framework에 대한 지식

이 튜토리얼의 예제를 따라하려면 .NET 프레임워크 및 C# 프로그래밍 언어에 대한 기본 지식이 필요합니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작해 보겠습니다.

```csharp

```

이제 전제 조건을 다루고 필수 네임스페이스를 가져왔으므로 각 예제를 여러 단계로 나누어 살펴보겠습니다.

## 1단계: 프로젝트 파일 로드

```csharp
var project = new Project("Project2.mpp");
```

 먼저 프로젝트 파일을 애플리케이션에 로드해야 합니다. 우리는 새로운 것을 만듭니다`Project` 개체를 만들고 프로젝트 파일의 경로로 초기화합니다.

## 2단계: 리소스 액세스

```csharp
var resource = project.Resources.GetById(1);
```

 다음으로 비용 발생 유형을 적용하려는 리소스에 액세스합니다. 우리는`GetById` 의 방법`Resources` 수집하고 리소스 ID를 인수로 전달합니다.

## 3단계: 비용 발생 유형 설정

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

여기서는 리소스에 대한 비용 발생 유형을 설정합니다. 이 예에서는 다음과 같이 설정합니다.`CostAccrualType.End`즉, 남은 작업 시간이 0이 될 때까지 비용이 발생하지 않는다는 의미입니다.

## 4단계: 프로젝트 작업

비용 발생 유형을 설정한 후 필요에 따라 프로젝트 작업을 계속하고 추가 작업이나 계산을 수행할 수 있습니다.

## 결론

효과적인 프로젝트 비용 관리를 위해서는 비용 발생 유형을 이해하고 구현하는 것이 필수적입니다. Aspose.Tasks for .NET을 사용하면 프로젝트 요구 사항에 따라 비용 발생 유형을 쉽게 정의하고 사용자 정의할 수 있으므로 프로젝트 수명 주기 전반에 걸쳐 정확한 비용 추적 및 예산 제어가 보장됩니다.

## FAQ

### Q1: 여러 자원에 대한 비용 발생 유형을 동시에 변경할 수 있습니까?

A1: 예, 리소스 수집을 반복하고 각 리소스에 대한 비용 발생 유형을 개별적으로 설정할 수 있습니다.

### Q2: '종료' 외에 사용 가능한 비용 발생 유형은 무엇입니까?

A2: .NET용 Aspose.Tasks는 다음과 같은 몇 가지 다른 비용 발생 유형을 제공합니다.`Start`, `Prorated` , 그리고`Duration`.

### Q3: 자원의 현재 비용 발생 유형을 어떻게 확인할 수 있습니까?

 A3: 다음을 사용하여 현재 비용 발생 유형을 검색할 수 있습니다.`Get` 리소스 개체에 대한 메서드입니다.

### Q4: 동일한 프로젝트 내의 다양한 작업에 다양한 비용 발생 유형을 적용할 수 있나요?

A4: 예, 프로젝트의 각 작업 및 자원에 대해 독립적으로 비용 발생 유형을 설정할 수 있습니다.

### Q5: .NET용 Aspose.Tasks는 사용자 지정 비용 발생 유형을 지원합니까?

A5: 최신 버전부터 Aspose.Tasks for .NET은 사용자 정의 비용 발생 유형 정의를 지원하지 않습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
