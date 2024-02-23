---
title: Aspose.Tasks의 위험 항목에 대한 통계
linktitle: Aspose.Tasks의 위험 항목에 대한 통계
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 위험 분석 기능을 활용하세요. 손쉽게 통찰력을 얻고, 불확실성을 완화하고, 프로젝트 성공을 촉진하세요.
type: docs
weight: 21
url: /ko/net/resource-risk-analysis/risk-item-statistics/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 프로젝트 관리 능력을 향상시키고 싶으십니까? MS 프로젝트 파일의 위험 항목에 대한 통계를 얻는 방법에 대한 단계별 튜토리얼을 통해 위험 분석 영역을 탐구해 보세요. Aspose.Tasks의 강력한 기능을 활용하면 프로젝트 불확실성에 대한 귀중한 통찰력을 얻고 정보에 입각한 결정을 내려 위험을 효과적으로 완화할 수 있습니다.
## 전제조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 갖추어져 있는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.Tasks](https://reference.aspose.com/tasks/net/), 이 라이브러리는 MS 프로젝트 파일을 프로그래밍 방식으로 조작하기 위한 강력한 도구를 제공합니다.
2. .NET 개발 환경: Aspose.Tasks를 프로젝트에 원활하게 통합할 수 있도록 Visual Studio 또는 원하는 다른 IDE를 포함한 .NET 개발 환경을 설정하세요.

## 네임스페이스 가져오기
Aspose.Tasks의 기능을 활용하려면 필요한 네임스페이스를 프로젝트에 통합하세요.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## 1단계: 데이터 디렉터리 정의
```csharp
String DataDir = "Your Document Directory";
```
 교체를 확인하세요`"Your Document Directory"`MS 프로젝트 파일이 있는 문서 디렉토리의 경로를 사용하세요.
## 2단계: 위험 분석 설정 구성
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 조정하다`IterationsCount` 위험 분석의 정확성을 제어하기 위해 프로젝트 요구 사항을 기반으로 매개변수를 설정합니다.
## 3단계: MS 프로젝트 파일 로드
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 원하는 MS 프로젝트 파일을`project` 추가 분석을 위한 개체입니다.
## 4단계: 작업 정의 및 위험 패턴 초기화
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
위험 분석 작업을 지정하고 분포 유형, 낙관적 및 비관적 기간, 신뢰 수준과 같은 적절한 매개변수를 사용하여 위험 패턴을 구성합니다.
## 5단계: 프로젝트 위험 분석
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
정의된 설정과 프로젝트 데이터를 사용하여 위험 분석 프로세스를 시작합니다.
## 6단계: 통계 검색 및 표시
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
기대값, 표준편차, 백분위수, 최소값, 최대값 등 MS 프로젝트 파일의 위험 항목과 관련된 다양한 통계 지표를 검색하고 표시합니다.

## 결론
결론적으로 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 위험 분석을 마스터하면 프로젝트 관리자와 이해관계자에게 가능성의 영역이 열립니다. 당사의 포괄적인 튜토리얼을 따르면 불확실성을 자신있게 탐색하여 성공적인 프로젝트 결과를 보장할 수 있습니다.
## FAQ
### 확장된 기능을 위해 Aspose.Tasks를 다른 .NET 라이브러리와 통합할 수 있습니까?
전적으로! Aspose.Tasks는 다양한 .NET 라이브러리와 원활하게 통합되어 프로젝트 요구 사항에 따라 기능을 증폭시킬 수 있습니다.
### .NET용 Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?
 예, Aspose.Tasks에 액세스하여 기능을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 당사 웹사이트에서 이용 가능합니다.
### Aspose.Tasks에 대한 업데이트 및 개선 사항은 얼마나 자주 출시됩니까?
우리는 정기적으로 업데이트와 개선 사항을 출시하여 Aspose.Tasks를 지속적으로 개선하고 귀하가 항상 최신 기능과 최적화에 액세스할 수 있도록 노력하고 있습니다.
### Aspose.Tasks에 대한 기술 지원을 받을 수 있나요?
틀림없이! 우리의 전담 지원팀은 다음에서 쉽게 이용 가능합니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 구현 과정에서 발생할 수 있는 모든 질문이나 문제에 대해 도움을 드립니다.
### 단기 프로젝트에 임시 라이센스를 제공합니까?
 예, 단기 프로젝트를 위해 Aspose.Tasks가 필요한 경우 편리한 서비스를 이용하실 수 있습니다.[임시면허](https://purchase.aspose.com/temporary-license/) 장기적인 약정 없이 라이선스 요구 사항을 충족할 수 있는 옵션입니다.