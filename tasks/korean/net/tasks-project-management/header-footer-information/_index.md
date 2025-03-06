---
title: Aspose.Tasks를 사용하여 머리글 및 바닥글 정보 추출
linktitle: Aspose.Tasks의 머리글 및 바닥글 정보
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 머리글 및 바닥글 정보를 추출하는 방법을 알아보세요. 쉽고 효율적이며 개발자 친화적인 솔루션입니다.
type: docs
weight: 29
url: /ko/net/tasks-project-management/header-footer-information/
---
## 소개
Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 쉽게 조작할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 머리글 및 바닥글 정보를 검색하는 방법을 알아봅니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙합니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다. 이를 통해 Aspose.Tasks 라이브러리에서 제공하는 클래스와 메서드에 액세스할 수 있습니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1단계: 프로젝트 개체 초기화
 시작하려면`Project` 기존 MS 프로젝트 파일을 로드하여 개체를 만듭니다.
```csharp
// 문서 디렉터리의 경로입니다.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## 2단계: 머리글 및 바닥글 정보 검색
 프로젝트 파일을 로드한 후에는 다음을 사용하여 머리글 및 바닥글 정보를 검색할 수 있습니다.`PageInfo` 재산.
```csharp
var info = project.DefaultView.PageInfo;
// 헤더 정보
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// 바닥글 정보
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
이러한 간단한 단계를 따르면 Aspose.Tasks for .NET을 사용하여 MS 프로젝트 파일에서 머리글 및 바닥글 정보를 쉽게 검색할 수 있습니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 머리글 및 바닥글 정보를 추출하는 방법을 살펴보았습니다. 이 강력한 라이브러리는 C# 애플리케이션에서 프로젝트 파일 작업을 단순화하여 개발자에게 강력한 조작 도구를 제공합니다.
### 자주 묻는 질문
### Aspose.Tasks를 사용하여 머리글과 바닥글 정보를 수정할 수 있나요?
예, .NET용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 머리글과 바닥글 정보를 수정할 수 있습니다.
### Aspose.Tasks는 MS Project 외에 다른 프로젝트 파일 형식을 지원합니까?
예, Aspose.Tasks는 MPP, XML 및 MPX를 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, 다음에서 Aspose.Tasks 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Tasks에 대한 문서는 어디에서 찾을 수 있나요?
 Aspose.Tasks에 대한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
### Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
 Aspose.Tasks에 대한 지원은 다음 사이트를 방문하여 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).