---
title: Aspose.Tasks에 대한 이미지 저장 MS 프로젝트 옵션
linktitle: Aspose.Tasks의 이미지 저장 옵션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 옵션을 이미지로 저장하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 11
url: /ko/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 대한 이미지 저장 MS 프로젝트 옵션


## 소개
소프트웨어 개발 세계에서는 프로젝트 작업을 효율적으로 처리하는 것이 성공적인 프로젝트 관리에 매우 중요합니다. Aspose.Tasks for .NET은 Microsoft Project 파일로 작업하는 개발자를 위한 강력한 솔루션을 제공하여 .NET 애플리케이션 내에서 프로젝트 작업을 원활하게 조작, 변환 및 관리할 수 있도록 해줍니다.
## 전제조건
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 옵션을 이미지로 저장하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
시작하려면 개발 환경에 Aspose.Tasks for .NET이 설치되어 있어야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/net/) 제공된 설치 지침을 따르십시오.
### 2. 라이센스 취득(선택)
 Aspose.Tasks for .NET은 평가 모드에서 라이선스 없이 사용할 수 있지만, 전체 기능을 사용하고 평가 제한 사항을 제거하려면 라이선스를 취득하는 것이 좋습니다. 에서 라이센스를 취득할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy) 또는 다음을 선택하세요.[임시면허](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.
### 3. C# 및 .NET 개발에 대한 기본 지식
예제를 따라가고 Aspose.Tasks 기능을 애플리케이션에 효과적으로 통합하려면 C# 프로그래밍 언어와 .NET 프레임워크에 대한 기본적인 이해가 필요합니다.
## 네임스페이스 가져오기
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트 옵션을 이미지로 저장하기 전에 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1단계: 문서 디렉터리 경로 설정
문서에 대해 지정된 디렉토리가 있는지 확인하고 이에 따라 경로를 설정하십시오.
```csharp
String DataDir = "Your Document Directory";
```
## 2단계: MS 프로젝트 파일 로드
 새로 초기화`Project` MS 프로젝트 파일을 로드하여 개체:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 3단계: 이미지 저장 옵션 정의
 인스턴스 만들기`ImageSaveOptions`원하는 설정을 지정합니다.
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## 4단계: 저장할 페이지 지정
필요한 경우 저장할 페이지를 지정하세요. 이 예에서는 2페이지를 추가합니다.
```csharp
options.Pages.Add(2);
```
## 5단계: 이미지 저장
마지막으로 선택한 페이지를 지정된 옵션을 사용하여 이미지로 저장합니다.
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## 결론
.NET용 Aspose.Tasks는 MS 프로젝트 파일 작업 프로세스를 단순화하여 개발자가 프로젝트 작업을 쉽게 조작할 수 있도록 해줍니다. 이 튜토리얼에 설명된 단계를 따르면 MS 프로젝트 옵션을 .NET 애플리케이션 내의 이미지로 효율적으로 저장할 수 있습니다.
## FAQ
### Q1: 라이선스 없이 .NET용 Aspose.Tasks를 사용할 수 있나요?
A: 예, 평가 모드에서는 라이선스 없이 .NET용 Aspose.Tasks를 사용할 수 있습니다. 그러나 전체 기능을 사용하려면 라이센스를 취득하고 평가 제한 사항을 제거하는 것이 좋습니다.
### Q2: 테스트용 임시 라이센스를 어떻게 얻을 수 있나요?
 A: 테스트 목적으로 임시 라이센스를 얻을 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
### Q3: Aspose.Tasks for .NET은 다른 .NET 프레임워크와 호환됩니까?
A: 예, Aspose.Tasks for .NET은 .NET Core 및 .NET Standard를 포함한 다양한 .NET 프레임워크와 호환됩니다.
### Q4: 이미지 저장 옵션을 추가로 사용자 정의할 수 있나요?
A: 예, 페이지 크기, 해상도 또는 출력 형식 조정과 같은 특정 요구 사항에 따라 이미지 저장 옵션을 사용자 정의할 수 있습니다.
### Q5: .NET용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 A: Aspose.Tasks for .NET에 대한 지원 및 지원은 다음 사이트에서 찾을 수 있습니다.[법정](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
