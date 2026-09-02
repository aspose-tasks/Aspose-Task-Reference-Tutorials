---
date: 2026-04-30
description: Aspose.Tasks for .NET를 사용하여 기준선을 설정하고 프로젝트 기준선을 효율적으로 조작하는 방법을 배우세요.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Aspose.Tasks의 다양한 기준선 유형
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 기준선 설정 방법 – 다양한 기준선 유형
url: /ko/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 다양한 베이스라인 유형

## 소개

프로젝트 관리에서 **베이스라인 설정 방법**을 올바르게 하는 것은 프로젝트가 순조롭게 진행되는지 아니면 통제 불능으로 빠지는지를 가르는 중요한 요소입니다. Aspose.Tasks for .NET은 베이스라인을 생성, 업데이트 및 비교할 수 있는 완전한 API를 제공하여 원래 계획에 대비해 **프로젝트 진행 상황을 추적**할 수 있게 합니다. 이 튜토리얼에서는 베이스라인을 설정하는 방법, 여러 베이스라인 유형을 다루는 방법, 그리고 데이터를 사용해 프로젝트의 **베이스라인 대비 실제 일정**을 분석하는 방법을 배웁니다.

## 빠른 답변
- **베이스라인이란?** 프로젝트의 특정 시점에 촬영한 일정, 비용 및 작업 데이터의 스냅샷입니다.  
- **Aspose.Tasks가 저장할 수 있는 베이스라인 수는?** 프로젝트당 최대 11개의 서로 다른 베이스라인을 저장할 수 있습니다.  
- **왜 베이스라인을 설정하나요?** 실제 성과를 원래 계획과 비교하고 차이를 식별하기 위해서입니다.  
- **이것을 사용하려면 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 실제 운영에는 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Tasks에서 “베이스라인 설정 방법”이란?
베이스라인을 설정한다는 것은 `Project` 객체에서 `SetBaseline` 메서드를 호출하는 것을 의미합니다. API는 여러 `BaselineType` 값(Baseline, Baseline1 … Baseline10) 중에서 선택할 수 있게 하여 프로젝트가 진행됨에 따라 과거 스냅샷을 유지할 수 있습니다.

## 프로젝트 베이스라인을 관리하는 이유
- **편차 측정:** 작업이 일정에 앞서 있는지 뒤처지는지를 빠르게 확인합니다.  
- **비용 관리:** 베이스라인 비용과 실제 지출을 비교합니다.  
- **이해관계자 보고:** 베이스라인 데이터를 PDF, XLSX 등 다양한 형식으로 내보내어 명확하게 전달합니다.  
- **시나리오 계획:** 여러 베이스라인을 저장해 “what‑if” 일정 평가에 활용합니다.

## 전제 조건

### 1. C# 및 .NET Framework에 대한 친숙함
C# 클래스, 메서드 및 객체 지향 개념에 대한 기본적인 이해가 필요합니다.

### 2. Aspose.Tasks for .NET 설치
라이브러리가 프로젝트에 추가되었는지 확인하십시오. [Aspose.Tasks 웹사이트](https://releases.aspose.com/tasks/net/)에서 다운로드하거나 NuGet을 통해 설치할 수 있습니다.

### 3. 통합 개발 환경 (IDE)
C# 코드를 작성, 컴파일 및 디버깅하기 위해 Visual Studio(또는 호환 가능한 IDE)를 사용하는 것이 권장됩니다.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.Tasks를 사용하기 전에 필요한 클래스와 메서드에 접근하기 위해 필수 네임스페이스를 가져와야 합니다. 다음 단계를 따르세요:

```csharp

```

이제 전제 조건을 설정하고 필요한 네임스페이스를 가져왔으니, Aspose.Tasks for .NET을 사용하여 다양한 유형의 베이스라인을 설정해 보겠습니다. 이해를 돕기 위해 각 예제를 여러 단계로 나누어 설명하겠습니다.

## Aspose.Tasks에서 베이스라인 설정 방법

### 단계 1: 프로젝트 파일 로드
먼저, 베이스라인을 설정하려는 프로젝트 파일을 로드해야 합니다. 이 단계에서는 `Project` 객체를 초기화하고 프로젝트 파일을 로드합니다. 아래와 같이 수행할 수 있습니다:

```csharp
var project = new Project("Project2.mpp");
```

### 단계 2: 베이스라인 설정
프로젝트가 로드되면 베이스라인을 설정할 수 있습니다. 베이스라인은 프로젝트 초기 일정의 스냅샷을 제공하여 진행 중에 비교 기준점으로 활용됩니다. `SetBaseline` 메서드를 사용해 베이스라인을 설정합니다. 예를 들어, 전체 프로젝트에 베이스라인을 설정하려면 `BaselineType.Baseline` 열거형을 사용합니다:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### 단계 3: 프로젝트 베이스라인 작업
베이스라인을 설정한 후에는 다양한 프로젝트 베이스라인 필드를 활용해 프로젝트 진행 상황을 정확히 분석하고 추적할 수 있습니다. 이 단계에서는 시작일, 종료일, 기간, 비용 등 베이스라인 데이터를 접근합니다. 여기서 Aspose.Tasks가 제공하는 풍부한 기능을 활용해 요구에 맞게 베이스라인 데이터를 조작할 수 있습니다.

## 일반적인 문제 및 해결책
- **베이스라인이 적용되지 않음:** `SetBaseline` 호출 후 프로젝트 파일을 저장했는지 확인하십시오. 변경 사항을 유지하려면 `project.Save("output.mpp");`를 사용합니다.  
- **다중 베이스라인 충돌:** 하나 이상의 베이스라인을 설정할 때는 올바른 `BaselineType`(예: `Baseline1`, `Baseline2`)을 지정하십시오.  
- **버전 불일치:** Aspose.Tasks DLL 버전이 대상 .NET 런타임과 일치하는지 확인하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks for .NET을 사용하여 단일 프로젝트에 여러 베이스라인을 설정할 수 있나요?**  
A: 네, Aspose.Tasks는 프로젝트당 최대 11개의 베이스라인을 설정할 수 있어 포괄적인 추적 기능을 제공합니다.

**Q: Aspose.Tasks가 다양한 프로젝트 파일 형식과 호환되나요?**  
A: 물론입니다! Aspose.Tasks는 MPP, XML, MPX 등 다양한 프로젝트 파일 형식을 지원하여 여러 플랫폼 간 호환성을 보장합니다.

**Q: 프로젝트에서 베이스라인 데이터를 시각화하려면 어떻게 해야 하나요?**  
A: Aspose.Tasks를 사용해 프로젝트 데이터를 PDF나 XLSX와 같은 일반적인 파일 형식으로 내보내면 베이스라인 정보를 쉽게 시각화하고 공유할 수 있습니다.

**Q: Aspose.Tasks는 프로젝트 관리 도구와의 통합을 지원하나요?**  
A: Aspose.Tasks는 풍부한 문서와 지원 포럼을 제공하여 개발자가 인기 있는 프로젝트 관리 도구 및 플랫폼과 기능을 원활히 통합할 수 있도록 돕습니다.

**Q: 구매 전에 Aspose.Tasks를 체험해 볼 수 있나요?**  
A: 네, 웹사이트에서 제공하는 무료 체험판을 통해 Aspose.Tasks를 직접 사용해 볼 수 있습니다.

**마지막 업데이트:** 2026-04-30  
**테스트 환경:** Aspose.Tasks for .NET (최신 안정 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}