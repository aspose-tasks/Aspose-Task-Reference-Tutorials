---
title: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 사용량 측정
linktitle: Aspose.Tasks의 측정 사용량
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 사용을 효과적으로 모니터링하고 최적화하는 방법을 알아보세요. 효율적인 프로젝트 관리를 위한 단계별 가이드입니다.
weight: 17
url: /ko/net/license-management/metering-usage/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 사용량 측정

## 소개
Aspose.Tasks를 사용하여 MS 프로젝트 사용량을 효과적으로 관리하고 모니터링하고 싶으십니까? 측정 기능을 사용하면 사용량을 추적하고 프로젝트 관리 활동을 최적화할 수 있습니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 사용량을 측정하는 과정을 단계별로 안내합니다.
## 전제조건
MS 프로젝트 사용량 측정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/net/). 개발 환경에서 라이브러리를 설정하려면 설치 지침을 따르세요.
2.  공개 및 개인 키: Aspose에서 공개 및 개인 키를 얻습니다. 이러한 키는 사용량 측정에 필수적입니다. 아직 키가 없다면 Aspose에서 다음을 통해 요청할 수 있습니다.[임시면허](https://purchase.aspose.com/temporary-license/) 페이지.

## 네임스페이스 가져오기
계속하기 전에 필요한 네임스페이스를 프로젝트로 가져옵니다.
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## 1단계: 측정 설정
MS 프로젝트 사용량 측정을 시작하려면 공개 키와 개인 키를 제공하여 측정 환경을 설정하세요.
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
 바꾸다`"Your Document Directory"` 문서 디렉토리의 경로로 대체하십시오.`<public key>` 그리고`<private key>` Aspose에서 얻은 실제 키로.
## 2단계: MS 프로젝트 파일 로드
다음으로 Aspose.Tasks를 사용하여 MS 프로젝트 파일을 로드합니다.
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
이 단계에서는 지정된 디렉터리에서 "Project2.mpp"라는 MS 프로젝트 파일을 로드합니다. 파일 이름을 자신의 MS 프로젝트 파일로 바꿀 수 있습니다.
## 3단계: 프로젝트 작업
이제 프로젝트가 로드되었으므로 프로젝트 관리 작업에 필요한 다양한 작업을 수행할 수 있습니다.
```csharp
// 여기에서 프로젝트 관리 작업을 수행하세요.
```
## 4단계: 크레딧 및 바이트 소비 확인
사용 기간 동안 소비된 크레딧과 소비된 바이트를 확인할 수 있습니다.
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    // 여기서 예외를 처리하세요.
}
```
이 단계에서는 작업에 사용된 크레딧과 소비된 바이트를 검색하고 표시합니다. 이 프로세스 중에 발생할 수 있는 모든 예외를 처리합니다.
## 5단계: 측정 키 재설정
선택적으로 측정 키를 재설정하여 바이트 계산을 중지할 수 있습니다.
```csharp
metered.ResetMeteredKey();
```
이 단계에서는 측정 프로세스를 중지하고 측정된 키를 재설정합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 사용량을 측정하는 방법을 배웠습니다. 이러한 단계를 수행하면 효율적인 리소스 활용을 보장하면서 프로젝트 관리 노력을 효과적으로 모니터링하고 최적화할 수 있습니다.
### FAQ
### Q: 여러 MS 프로젝트 파일의 사용량을 측정할 수 있나요?
A: 예, 각 파일을 별도로 로드하고 그에 따라 사용량을 모니터링하여 여러 MS 프로젝트 파일의 사용량을 측정할 수 있습니다.
### Q: MS 프로젝트 사용량 측정은 .NET용 Aspose.Tasks의 모든 버전과 호환됩니까?
A: 예, MS 프로젝트 사용량 측정은 .NET용 Aspose.Tasks의 모든 버전에서 지원됩니다.
### Q: 사용량을 측정하려면 인터넷 연결이 필요합니까?
A: 네, 사용량 측정을 위해 Aspose 서버와 통신하려면 인터넷 연결이 필요합니다.
### Q: 실시간으로 사용량을 추적할 수 있나요?
A: 예, 주기적으로 사용된 크레딧과 소비된 바이트를 확인하여 실시간으로 사용량을 추적할 수 있습니다.
### Q: 평가판에서도 MS Project 사용량 측정이 가능합니까?
A: 예, MS 프로젝트 사용량 측정은 Aspose.Tasks for .NET의 평가판과 라이선스 버전 모두에서 사용할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
