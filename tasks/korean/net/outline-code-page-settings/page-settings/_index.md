---
title: Aspose.Tasks를 사용하여 MS 프로젝트 페이지 설정 구성
linktitle: Aspose.Tasks에서 페이지 설정 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 페이지 설정을 구성하는 방법을 알아보세요. 간단한 단계를 통해 방향, 크기 등을 맞춤설정하세요.
type: docs
weight: 20
url: /ko/net/outline-code-page-settings/page-settings/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 페이지 설정을 구성하는 과정을 안내합니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks: .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: Visual Studio 또는 .NET 개발을 위해 선호하는 기타 IDE를 사용하여 개발 환경을 설정합니다.

## 네임스페이스 가져오기
시작하려면 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 MS 프로젝트 파일을 조작하는 데 필요한 Aspose.Tasks 클래스 및 메서드에 대한 액세스를 제공합니다.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1단계: 프로젝트 파일 로드
먼저 페이지 설정을 구성하려는 MS 프로젝트 파일을 로드해야 합니다.
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## 2단계: 페이지 설정에 액세스
다음으로 프로젝트 파일의 페이지 설정에 액세스합니다.
```csharp
// 설정 가져오기
var settings = project.DefaultView.PageInfo.PageSettings;
```
## 3단계: 페이지 설정 구성
이제 요구 사항에 따라 페이지 설정의 다양한 속성을 구성해 보겠습니다.
```csharp
// 페이지 방향을 세로로 설정
settings.IsPortrait = true;
// 인쇄할 페이지 너비 설정
settings.PagesInWidth = 5;
// 인쇄할 페이지 높이 설정
settings.PagesInHeight = 7;
// 인쇄를 조정할 일반 크기의 비율을 설정합니다.
settings.PercentOfNormalSize = 200;
// 용지 크기 설정
settings.PaperSize = PrinterPaperSize.PaperB4;
// 인쇄할 첫 번째 페이지 번호 설정
settings.FirstPageNumber = 3;
```
## 4단계: 프로젝트 파일 저장
마지막으로 업데이트된 페이지 설정으로 프로젝트 파일을 저장합니다.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 페이지 설정을 구성하는 방법을 배웠습니다. 다음 단계를 수행하면 요구 사항에 따라 페이지 방향, 크기 및 기타 인쇄 옵션을 쉽게 사용자 정의할 수 있습니다.

## FAQ
### Q: 여러 MS 프로젝트 파일에 대한 페이지 설정을 동시에 구성할 수 있습니까?
A: 예, 여러 프로젝트 파일을 반복하여 각 파일에 동일한 페이지 설정을 적용할 수 있습니다.
### Q: 페이지 설정을 기본값으로 되돌릴 수 있나요?
A: 물론입니다. 간단히 구성 단계를 생략하거나 설정을 기본값으로 재설정할 수 있습니다.
### Q: 지원되는 용지 크기에 제한이 있나요?
A: Aspose.Tasks는 표준 및 사용자 정의 크기를 포함하여 광범위한 용지 크기를 지원합니다.
### Q: 페이지 설정 구성 프로세스를 자동화할 수 있습니까?
A: 물론 이 기능을 애플리케이션의 작업 흐름에 통합하여 페이지 설정 구성을 자동화할 수 있습니다.
### Q: Aspose.Tasks는 .mpp 외에 다른 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 XML, MPT, HTML 등 다양한 파일 형식을 지원합니다.