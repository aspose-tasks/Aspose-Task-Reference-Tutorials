---
title: Aspose.Tasks에서 MS 프로젝트 자원 사용량 보기 구성
linktitle: Aspose.Tasks에서 리소스 사용량 보기 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS Project 리소스 사용량 보기를 구성하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 15
url: /ko/net/resource-risk-analysis/resource-usage-views/
---
## 소개
Microsoft Project(MS Project)는 프로젝트 관리를 위한 강력한 도구로, 사용자가 프로젝트를 효율적으로 계획, 실행 및 추적할 수 있도록 해줍니다. .NET용 Aspose.Tasks는 MS 프로젝트 파일과의 원활한 통합을 제공하여 개발자가 프로그래밍 방식으로 프로젝트 데이터를 조작할 수 있도록 합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 리소스 사용량 보기를 구성하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks: 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 파일: Microsoft Project 파일(`.mpp`) 작업하려는 프로젝트 데이터가 포함되어 있습니다.

## 네임스페이스 가져오기
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 1단계: 프로젝트 파일 로드
먼저 Aspose.Tasks를 사용하여 MS 프로젝트 파일을 로드합니다.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## 2단계: 저장 옵션 정의
필요한 기간 설정 및 프레젠테이션 형식을 지정하는 저장 옵션을 정의합니다.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## 3단계: 자원 사용량 보기를 사용하여 프로젝트 저장
구성된 리소스 사용량 보기가 포함된 프로젝트를 PDF 파일로 저장합니다.
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 리소스 사용량 보기를 구성하는 방법을 배웠습니다. 제공된 단계에 따라 개발자는 Aspose.Tasks를 .NET 애플리케이션에 원활하게 통합하여 프로젝트 데이터를 효율적으로 조작할 수 있습니다.

## FAQ
### Q: Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks는 .mpp, .mpt, .xml 및 .mpx를 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: 시간 척도 설정과 프레젠테이션 형식을 추가로 사용자 정의할 수 있나요?
A: 물론 Aspose.Tasks는 요구 사항에 따라 시간 척도 설정 및 프레젠테이션 형식을 사용자 정의할 수 있는 유연성을 제공합니다.
### Q: Aspose.Tasks는 PDF 외에 다른 출력 형식을 지원합니까?
A: 예, Aspose.Tasks는 XLSX, MPP, XML, HTML 등을 포함한 다양한 출력 형식을 지원합니다.
### Q: Aspose.Tasks 지원을 위한 커뮤니티나 포럼이 있나요?
 A: 네, 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 질문, 토론 또는 지원이 필요한 경우.
### Q: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 물론 무료 평가판을 통해 Aspose.Tasks를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).