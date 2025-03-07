---
title: Aspose.Tasks의 다양한 기준선 유형
linktitle: Aspose.Tasks의 다양한 기준선 유형
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로젝트 기준선을 효율적으로 설정하고 조작하는 방법을 알아보세요.
weight: 21
url: /ko/net/advanced-features/baseline-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 다양한 기준선 유형

## 소개

프로젝트 관리 영역에서는 정확성과 예측이 가장 중요합니다. Aspose.Tasks for .NET은 프로젝트 데이터를 효율적으로 관리하기 위한 강력한 툴킷을 제공하여 사용자가 프로젝트 계획, 추적 및 실행의 다양한 측면을 탐구할 수 있도록 합니다. Aspose.Tasks가 제공하는 중요한 기능 중 하나는 초기 계획과 비교하여 프로젝트 진행 상황을 측정하기 위한 기준점 역할을 하는 기준선을 설정하는 기능입니다.

## 전제조건

.NET용 Aspose.Tasks를 사용하여 기준선의 세계로 뛰어들기 전에 다음 전제 조건이 있는지 확인하세요.

### 1. C# 및 .NET Framework에 대한 지식

Aspose.Tasks의 강력한 기능을 활용하려면 C# 프로그래밍 언어와 .NET 프레임워크에 대한 기본적인 이해가 필수적입니다. 여기에는 클래스, 메소드 및 객체 지향 프로그래밍 개념에 대한 지식이 포함됩니다.

### 2. .NET용 Aspose.Tasks 설치

개발 환경에 Aspose.Tasks for .NET 라이브러리를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Tasks 웹사이트](https://releases.aspose.com/tasks/net/) 또는 NuGet 패키지 관리자를 통해.

### 3. 통합 개발 환경(IDE)

C# 코드를 원활하게 작성, 컴파일 및 디버깅하려면 시스템에 Visual Studio와 같은 IDE를 설치하십시오.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.Tasks 작업을 시작하기 전에 필요한 클래스와 메서드에 액세스하기 위해 필요한 네임스페이스를 가져와야 합니다. 다음과 같이하세요:

```csharp

```

이제 전제 조건을 설정하고 필요한 네임스페이스를 가져왔으므로 .NET용 Aspose.Tasks를 사용하여 다양한 유형의 기준선을 설정하는 방법을 살펴보겠습니다. 명확성과 이해의 용이성을 위해 각 예를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 파일 로드

 먼저 기준선을 설정하려는 프로젝트 파일을 로드해야 합니다. 이 단계에는`Project` 개체를 생성하고 프로젝트 파일을 로드합니다. 방법은 다음과 같습니다.

```csharp
var project = new Project("Project2.mpp");
```

## 2단계: 기준선 설정

프로젝트가 로드되면 기준선 설정을 진행할 수 있습니다. 기준선은 프로젝트가 진행됨에 따라 비교를 위한 참조 지점 역할을 하는 프로젝트 초기 일정의 스냅샷을 제공합니다. 사용`SetBaseline` 기준선을 설정하는 방법입니다. 예를 들어 전체 프로젝트의 기준선을 설정하려면`BaselineType.Baseline` 열거:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

## 3단계: 프로젝트 기준선 작업

기준선을 설정한 후 다양한 프로젝트 기준선 필드를 사용하여 프로젝트 진행 상황을 정확하게 분석하고 추적할 수 있습니다. 이 단계에는 시작 날짜, 완료 날짜, 기간 및 비용과 같은 기준 데이터에 액세스하는 작업이 포함됩니다. 여기에서 Aspose.Tasks가 제공하는 풍부한 기능 세트를 활용하여 요구 사항에 따라 기준 데이터를 조작할 수 있습니다.

## 결론

결론적으로 Aspose.Tasks for .NET은 개발자에게 프로젝트 기준선을 효과적으로 관리하기 위한 강력한 도구를 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 다양한 유형의 기준선을 원활하게 설정하고 조작하여 프로젝트 진행 상황을 정확하고 민첩하게 모니터링할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks for .NET을 사용하여 단일 프로젝트에 대해 여러 기준선을 설정할 수 있습니까?

A1: 예, Aspose.Tasks를 사용하면 프로젝트에 대해 최대 11개의 기준선을 설정하여 포괄적인 추적 기능을 제공할 수 있습니다.

### Q2: Aspose.Tasks는 다른 프로젝트 파일 형식과 호환됩니까?

A2: 물론이죠! Aspose.Tasks는 MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.

### Q3: 내 프로젝트의 기준 데이터를 어떻게 시각화할 수 있나요?

A3: Aspose.Tasks를 활용하여 프로젝트 데이터를 PDF 또는 XLSX와 같은 널리 사용되는 파일 형식으로 내보내 기본 정보를 쉽게 시각화하고 공유할 수 있습니다.

### Q4: Aspose.Tasks는 프로젝트 관리 도구와의 통합을 지원합니까?

A4: Aspose.Tasks는 개발자가 해당 기능을 널리 사용되는 프로젝트 관리 도구 및 플랫폼과 원활하게 통합할 수 있도록 광범위한 문서와 지원 포럼을 제공합니다.

### Q5: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?

A5: 예, 웹사이트에서 제공되는 무료 평가판을 통해 Aspose.Tasks를 탐색하여 해당 기능을 직접 경험할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
