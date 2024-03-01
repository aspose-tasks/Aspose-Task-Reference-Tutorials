---
title: Aspose.Tasks를 사용하여 MS 프로젝트 확장 속성 조작
linktitle: Aspose.Tasks에서 확장 속성 작업
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS Project 확장 속성으로 작업하는 방법을 알아보세요. 프로그래밍 방식으로 작업 데이터를 쉽게 조작할 수 있습니다.
type: docs
weight: 11
url: /ko/net/tasks-project-management/working-with-extended-attributes/
---
## 소개
Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 이 라이브러리의 주요 기능 중 하나는 MS Project 확장 속성을 사용하는 기능입니다. 확장된 속성은 프로젝트의 작업에 대한 추가 사용자 정의 및 메타데이터를 제공하므로 사용자는 표준 작업 속성 이상의 특정 정보를 저장하고 관리할 수 있습니다.
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 확장 속성으로 작업하는 방법을 살펴보겠습니다. 전제 조건을 다루고, 네임스페이스를 가져오고, 단계별 가이드 형식으로 각 예를 여러 단계로 분류합니다. 이 자습서를 마치면 .NET 애플리케이션에서 확장된 특성을 활용하는 방법을 확실하게 이해하게 될 것입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. 비주얼 스튜디오 설치
시스템에 Visual Studio가 설치되어 있는지 확인하세요. 아직 다운로드하지 않으셨다면 웹사이트에서 다운로드하실 수 있습니다.
### 2. .NET 라이브러리용 Aspose.Tasks
 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).

## 네임스페이스 가져오기
.NET용 Aspose.Tasks 작업을 시작하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 다음과 같이하세요:
### 1단계: Visual Studio 열기
시스템에서 Visual Studio를 실행합니다.
### 2단계: 새 프로젝트 만들기
Aspose.Tasks를 사용하려는 새 프로젝트를 만들거나 기존 프로젝트를 엽니다.
### 3단계: 네임스페이스 가져오기
C# 파일 시작 부분에 다음 네임스페이스를 추가합니다.
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

이제 환경을 설정했으므로 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 확장 속성 작업에 대해 살펴보겠습니다.
## 1단계: 데이터 디렉터리 정의
MS 프로젝트 파일이 있는 디렉터리의 경로를 정의합니다.
```csharp
String DataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.
## 2단계: 프로젝트 파일 로드
 다음을 사용하여 MS 프로젝트 파일을 로드합니다.`Project` 수업:
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
 이 코드는`Project` 클래스, 지정된 MS 프로젝트 파일을 로드합니다.
## 3단계: 작업에 대한 확장된 속성 읽기
작업과 해당 확장 속성을 반복하여 정보를 읽습니다.
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        // 확장된 속성에 대한 일반 정보 읽기
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
이 코드 조각은 각 작업과 해당 확장 속성을 반복하여 해당 정보를 콘솔에 인쇄합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 확장 속성으로 작업하는 방법을 배웠습니다. 위에 설명된 단계를 수행하면 .NET 애플리케이션에서 확장된 속성 데이터를 효율적으로 관리하고 조작할 수 있습니다.
## FAQ
### Aspose.Tasks for .NET은 모든 버전의 Microsoft Project와 호환됩니까?
예, .NET용 Aspose.Tasks는 2003, 2007, 2010, 2013, 2016 및 2019를 포함한 다양한 버전의 Microsoft Project를 지원합니다.
### .NET용 Aspose.Tasks를 사용하여 새 MS 프로젝트 파일을 만들 수 있나요?
전적으로! Aspose.Tasks for .NET을 사용하면 프로그래밍 방식으로 MS 프로젝트 파일을 생성, 수정 및 조작할 수 있습니다.
### .NET용 Aspose.Tasks에는 상업용 라이선스가 필요합니까?
예, .NET용 Aspose.Tasks를 상업적으로 사용하려면 라이선스를 구입해야 합니다. 그러나 무료 평가판을 사용하여 기능을 평가할 수도 있습니다.
### 내 프로젝트 요구 사항에 따라 확장 속성을 사용자 정의할 수 있나요?
예, Aspose.Tasks for .NET은 프로젝트의 특정 요구 사항에 맞게 확장 속성을 사용자 정의할 수 있는 광범위한 기능을 제공합니다.
### .NET용 Aspose.Tasks를 사용하는 동안 문제가 발생하면 어디서 지원을 받을 수 있나요?
 Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).