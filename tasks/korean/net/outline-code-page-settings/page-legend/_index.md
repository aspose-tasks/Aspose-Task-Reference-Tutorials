---
title: Aspose.Tasks에서 MS 프로젝트 범례 구성
linktitle: Aspose.Tasks에서 페이지 범례 구성
second_title: Aspose.태스크 .NET API
description: 효율적인 프로젝트 관리를 위해 Aspose.Tasks를 사용하여 .NET에서 MS 프로젝트 페이지 범례를 구성하는 방법을 알아보세요. 단계별 가이드가 제공됩니다.
weight: 18
url: /ko/net/outline-code-page-settings/page-legend/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 범례 구성

## 소개
.NET 개발 영역에서는 특히 프로젝트 관리를 다룰 때 작업을 효율적으로 관리하는 것이 중요합니다. Aspose.Tasks for .NET은 작업 관리 프로세스를 간소화하기 위한 다양한 기능을 제공하는 강력한 도구로 등장합니다. 그러한 기능 중 하나는 MS 프로젝트 페이지 범례를 구성하여 사용자에게 프로젝트 데이터 프레젠테이션에 대한 귀중한 통찰력을 제공하는 기능입니다.
## 전제조건
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 페이지 범례를 구성하기 전에 다음 전제 조건이 충족되는지 확인하세요.
1. 설치: 개발 환경에 Aspose.Tasks for .NET을 설치하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. .NET 기본 지식: 프로젝트 설정 및 네임스페이스 작업을 포함하여 .NET 개발의 기본 사항을 숙지합니다.
3. 개발 환경: 원활한 코딩 경험을 위해 Visual Studio와 같은 통합 개발 환경(IDE)을 사용합니다.
4. 프로젝트 파일: 실험을 위해 Microsoft Project 파일(MPP)을 준비합니다.

## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks for .NET에서 제공하는 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
1. 프로젝트 열기: 원하는 IDE에서 .NET 프로젝트를 시작합니다.
2. 네임스페이스 가져오기: 코드 파일 시작 부분에서 필수 네임스페이스를 가져옵니다.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 페이지 범례 구성을 포괄적으로 이해하기 위해 제공된 예제를 단계별 가이드 형식으로 분해해 보겠습니다.

## 1단계: 문서 디렉터리 지정
Microsoft Project 파일이 있는 문서 디렉터리의 경로를 설정합니다.

```csharp
String DataDir = "Your Document Directory";
```
## 2단계: 프로젝트 로드
 새 인스턴스를 초기화합니다.`Project` Microsoft Project 파일을 로드하여 클래스를 만들 수 있습니다.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## 3단계: 페이지 범례 정보 읽기
프로젝트의 기본 보기에서 페이지 범례 정보에 액세스합니다.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## 4단계: 범례 정보 표시
왼쪽 텍스트, 왼쪽 이미지, 가운데 텍스트, 가운데 이미지, 오른쪽 텍스트, 오른쪽 이미지, 범례 상태 및 너비와 같은 범례 세부 정보를 출력합니다.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## 5단계: 범례 수정
필요에 따라 범례를 수정합니다. 이 예에서는 왼쪽 텍스트를 변경합니다.

```csharp
legend.LeftText = "New Left Text";
```
## 6단계: 변경 사항 저장
프로젝트 파일에 대한 변경 사항을 저장합니다.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## 결론
결론적으로 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 페이지 범례 구성을 마스터하면 .NET 생태계 내에서 프로젝트 관리 기능을 크게 향상시킬 수 있습니다. 개략적인 단계와 전제 조건을 따르면 개발자는 이 기능을 프로젝트에 원활하게 통합하여 프로젝트 데이터의 시각화 및 해석을 향상시킬 수 있습니다.
## FAQ
### Q: 다른 .NET 프레임워크와 함께 .NET용 Aspose.Tasks를 사용할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 다양한 .NET 프레임워크와 호환되므로 다양한 프로젝트 요구 사항에 걸쳐 유연성과 적응성을 보장합니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/), 구매하기 전에 기능을 탐색할 수 있습니다.
### Q: Aspose.Tasks for .NET에 임시 라이선스를 사용할 때 제한 사항이 있나요?
A: 임시 라이선스는 .NET용 Aspose.Tasks 기능에 대한 전체 액세스를 제공하지만 시간이 제한됩니다. 단기 프로젝트나 평가 목적에 적합합니다.
### Q: 제공된 예를 넘어서 페이지 범례를 사용자 정의할 수 있습니까?
A: 물론 .NET용 Aspose.Tasks는 광범위한 사용자 정의 옵션을 제공하므로 특정 프로젝트 요구 사항에 따라 페이지 범례를 맞춤 설정할 수 있습니다.
### Q: .NET용 Aspose.Tasks에 대한 지원이나 커뮤니티 포럼은 어디에서 찾을 수 있나요?
 답변: 다음에서 지원을 구하고 커뮤니티에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 쿼리에 대한 답변을 찾고 동료 개발자와 상호 작용할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
