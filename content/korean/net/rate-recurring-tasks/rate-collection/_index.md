---
title: Aspose.Tasks를 사용한 마스터 MS 프로젝트 요금
linktitle: Aspose.Tasks의 요금 수집
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 요율을 관리하는 방법을 알아보세요. 효과적인 자원 관리를 위한 단계별 튜토리얼입니다.
type: docs
weight: 11
url: /ko/net/rate-recurring-tasks/rate-collection/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 요금을 관리하는 방법에 대한 튜토리얼에 오신 것을 환영합니다! 이 가이드에서는 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 요율 작업 과정을 안내합니다. 숙련된 개발자이든 이제 막 .NET 개발을 시작하는 개발자이든 이 튜토리얼에서는 프로젝트 내에서 속도를 효과적으로 처리하기 위한 단계별 지침을 제공합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. 비주얼 스튜디오 설치
시스템에 Visual Studio가 설치되어 있는지 확인하세요. 아직 다운로드하지 않으셨다면 웹사이트에서 다운로드하실 수 있습니다.
### 2. .NET용 Aspose.Tasks
 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
### 3. C# 및 .NET에 대한 기본 지식
이 자습서에서 제공되는 코드 예제를 더 잘 이해하려면 C# 프로그래밍 언어 및 .NET 프레임워크 기본 사항을 숙지하세요.
## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.Tasks 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
이제 각 예를 여러 단계로 나누어 보겠습니다.
## 1단계: MS 프로젝트 파일 로드
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 여기서는 새 항목을 만듭니다.`Project` 기존 MS 프로젝트 파일을 로드하여 개체를 만듭니다.
## 2단계: 리소스 추가 및 작업 시간 및 요율 설정
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
프로젝트에 새 자원을 추가하고 유형을 작업량, 작업량 및 표준 요율로 설정합니다.
## 3단계: 리소스에 요율 추가
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
시작일과 종료일, 표준 요율, 요율 형식을 지정하는 요율을 리소스에 추가합니다.
## 4단계: 요금 정보 인쇄
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
이 단계에서는 자원과 관련된 요율에 대한 정보를 인쇄합니다.
## 5단계: 요금 업데이트
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
특정 요율의 종료일을 업데이트합니다.
## 6단계: 요금 제거
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
이 단계에서는 특정 유형의 모든 요율을 제거합니다.
## 7단계: 나머지 비율에 대해 반복
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
마지막으로 제거 후 남은 비율을 반복합니다.
## 결론
결론적으로 이 튜토리얼은 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 요율 관리에 대한 포괄적인 가이드를 제공했습니다. 이 튜토리얼에 설명된 단계별 지침을 따르면 프로젝트 내에서 요금을 효율적으로 처리하여 정확한 리소스 관리를 보장할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET을 다른 프로젝트 관리 소프트웨어와 함께 사용할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 MS Project, Primavera 등을 포함한 다양한 프로젝트 관리 소프트웨어와의 통합을 지원합니다.
### Q: Aspose.Tasks for .NET은 다른 버전의 MS 프로젝트 파일과 호환됩니까?
A: 물론 Aspose.Tasks for .NET은 다양한 버전의 MS 프로젝트 파일 작업을 지원하여 유연성과 호환성을 보장합니다.
### Q: .NET용 Aspose.Tasks는 문서와 지원을 제공합니까?
 A: 예, Aspose.Tasks에서 포괄적인 문서와 지원 포럼에 대한 액세스를 찾을 수 있습니다.[웹사이트](https://reference.aspose.com/tasks/net/).
### Q: 구매하기 전에 .NET용 Aspose.Tasks를 사용해 볼 수 있나요?
A: 예, .NET용 Aspose.Tasks 무료 평가판을 사용하여 해당 기능과 요구 사항과의 호환성을 평가할 수 있습니다.
### Q: .NET용 Aspose.Tasks 라이선스를 어떻게 구매할 수 있나요?
 A: Aspose.Tasks for .NET 라이선스는 다음 사이트에서 구매할 수 있습니다.[웹사이트](https://purchase.aspose.com/temporary-license/)귀하의 필요에 맞는 유연한 라이센스 옵션을 제공합니다.