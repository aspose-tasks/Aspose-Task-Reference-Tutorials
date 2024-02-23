---
title: Aspose.Tasks에서 MS 프로젝트 파일 정보 검색
linktitle: Aspose.Tasks에서 프로젝트 파일 정보 검색
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일 정보를 검색하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 19
url: /ko/net/project-management-integration/project-file-information/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일 정보를 검색하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Tasks는 .NET 개발자가 프로그래밍 방식으로 Microsoft Project 파일을 사용하여 프로젝트 데이터 읽기, 쓰기 및 조작과 같은 작업을 수행할 수 있도록 하는 강력한 라이브러리입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. C# 및 .NET에 대한 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍 언어 및 .NET 프레임워크에 대한 기본 지식을 가지고 있다고 가정합니다.
2. Visual Studio: Visual Studio 또는 .NET 개발과 호환되는 기타 IDE를 설치합니다.
3.  .NET 라이브러리용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
4. Microsoft Project 파일: 테스트 목적으로 Microsoft Project 파일(이 예에서는 XML 형식)을 준비합니다.

## 네임스페이스 가져오기
먼저 Aspose.Tasks를 사용하려면 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.
## 1단계: Aspose.Tasks 네임스페이스 가져오기
```csharp
using Aspose.Tasks;
using System;

```
## MS 프로젝트 파일 정보 검색
이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 2단계: 문서 디렉터리 설정
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` MS 프로젝트 파일이 포함된 디렉터리 경로를 사용하세요.
## 3단계: 프로젝트 파일 정보 검색
```csharp
var info = Project.GetProjectFileInfo(dataDir + "Project.xml");
```
 이 코드 줄은 지정된 프로젝트 파일에 대한 정보를 검색합니다. 바꾸다`"Project.xml"` MS 프로젝트 파일 이름으로.
## 4단계: 프로젝트 정보 표시
```csharp
Console.WriteLine("CanRead: " + info.CanRead);
Console.WriteLine("ProjectApplicationInfo: " + info.ProjectApplicationInfo);
Console.WriteLine("ProjectFileFormat: " + info.ProjectFileFormat);
```
이 코드 줄은 가독성, 응용 프로그램 정보 및 파일 형식과 같은 MS 프로젝트 파일에 대한 다양한 정보를 표시합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일 정보를 검색하는 방법을 배웠습니다. 이러한 간단한 단계를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 MS 프로젝트 파일을 효율적으로 작업할 수 있습니다.
## FAQ
### Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 처리할 수 있나요?
예, Aspose.Tasks는 MPP 및 XML 형식을 포함하여 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Aspose.Tasks는 .NET Core와 호환됩니까?
예, Aspose.Tasks는 .NET Framework 및 .NET Core와 모두 호환됩니다.
### Aspose.Tasks를 사용하여 프로젝트 데이터를 조작할 수 있나요?
물론 Aspose.Tasks는 프로젝트 데이터를 프로그래밍 방식으로 읽고, 쓰고, 조작할 수 있는 광범위한 기능을 제공합니다.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, Aspose.Tasks의 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 Aspose.Tasks에 대한 지원은 다음을 통해 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).## 완전한 소스 코드