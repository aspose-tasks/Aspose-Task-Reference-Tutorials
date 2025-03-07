---
title: Aspose.Tasks에서 MS 프로젝트 위험 항목 통계 수집
linktitle: Aspose.Tasks의 위험 항목 통계 수집
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 위험 항목 통계를 수집하는 방법을 알아보세요. 프로젝트 관리 역량을 강화하세요.
weight: 22
url: /ko/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 위험 항목 통계 수집

## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 MS 프로젝트 파일에서 위험 항목 통계를 수집하는 방법을 살펴보겠습니다. 이 라이브러리는 위험 평가 및 통계 분석을 포함하여 프로젝트 데이터를 분석하는 강력한 기능을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하고 설치하세요. 에서 받으실 수 있습니다.[다운로드 페이지](https://releases.aspose.com/tasks/net/).
2. 개발 환경: .NET 프로그래밍을 위한 개발 환경을 설정합니다.

## 네임스페이스 가져오기
코딩을 시작하기 전에 프로젝트에 필요한 네임스페이스를 가져와야 합니다.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## 1단계: 프로젝트 파일 로드
먼저 MS 프로젝트 파일을 애플리케이션에 로드해야 합니다. 이를 달성하는 방법은 다음과 같습니다.
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 2단계: 위험 분석 설정 정의
아래와 같이 반복 횟수를 포함한 위험 분석 설정을 초기화합니다.
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## 3단계: 위험 패턴 초기화
분포 유형, 낙관적 및 비관적 백분율, 신뢰 수준을 지정하여 분석을 위한 위험 패턴을 설정합니다.
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## 4단계: 위험 분석 수행
 인스턴스화`RiskAnalyzer` 수업을 듣고 프로젝트를 분석합니다.
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## 5단계: 통계 검색
분석 결과에서 조기 종료 등 위험 항목 통계를 검색합니다.
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## 6단계: 통계 인쇄
통계를 반복하고 세부정보를 인쇄합니다.
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //기타 관련 통계 인쇄...
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 활용하여 MS 프로젝트 파일에서 위험 항목 통계를 수집하는 방법을 배웠습니다. 이러한 단계를 수행하면 프로젝트 데이터를 효과적으로 분석하고 잠재적 위험을 평가하여 더 나은 의사 결정 및 프로젝트 관리에 도움이 될 수 있습니다.

## FAQ
### Q: Aspose.Tasks는 대용량 MS 프로젝트 파일을 처리할 수 있나요?
A: 예, Aspose.Tasks는 대용량 MS 프로젝트 파일을 효율적으로 처리할 수 있어 안정적인 성능과 확장성을 제공합니다.
### Q: Aspose.Tasks는 .mpp 외에 다른 프로젝트 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 XML 및 MPT를 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### Q: Aspose.Tasks는 기업 수준의 프로젝트 관리 애플리케이션에 적합합니까?
A: 물론 Aspose.Tasks는 강력한 기능과 광범위한 문서를 제공하여 엔터프라이즈 수준 프로젝트 관리 애플리케이션의 요구 사항을 충족하도록 설계되었습니다.
### Q: Aspose.Tasks에서 위험 분석 설정을 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks는 특정 프로젝트 요구 사항 및 시나리오에 맞게 위험 분석 설정을 구성하는 유연성을 제공합니다.
### Q: Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
 A: 예, Aspose.Tasks 사용자는 Aspose를 통해 기술 지원에 액세스할 수 있습니다.[포럼](https://forum.aspose.com/c/tasks/15)에서 질문하고, 문제를 보고하고, 커뮤니티와 상호 작용할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
