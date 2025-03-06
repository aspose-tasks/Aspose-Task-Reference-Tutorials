---
title: Aspose.Tasks에 대한 MS 프로젝트의 글꼴 조작
linktitle: Aspose.Tasks의 글꼴 저장 인수
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 글꼴을 조작하는 방법을 알아보세요. 개발자를 위한 단계별 가이드.
weight: 19
url: /ko/net/tasks-project-management/font-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 대한 MS 프로젝트의 글꼴 조작

## 소개
MS 프로젝트 문서의 글꼴을 조작하기 위해 .NET용 Aspose.Tasks를 사용하는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Tasks는 개발자가 프로그래밍 방식으로 Microsoft Project 파일을 사용하여 프로젝트 데이터 읽기, 쓰기 및 수정과 같은 작업에 대한 광범위한 기능을 사용할 수 있도록 하는 강력한 라이브러리입니다.
이 튜토리얼에서는 특히 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에 글꼴을 저장하는 방법에 중점을 둘 것입니다. 프로세스를 따라하기 쉬운 단계로 나누어 글꼴 저장 기능을 .NET 애플리케이션에 원활하게 통합할 수 있도록 하겠습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 설정되어 있는지 확인하세요.
1. 개발 환경: Visual Studio 및 .NET이 설치된 개발 환경이 설치되어 있는지 확인하세요.
2.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/net/).
3.  라이선스: Aspose.Tasks for .NET 라이선스를 취득하세요. 아직 라이센스가 없다면 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
4. C#의 기본 이해: C# 프로그래밍 언어 기본 사항에 익숙해집니다.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져옵니다. 이러한 네임스페이스는 Aspose.Tasks 기능을 사용하는 데 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.
## 1단계: C# 프로젝트 열기
Visual Studio 또는 기타 선호하는 IDE에서 C# 프로젝트를 엽니다.
## 2단계: Aspose.Tasks 네임스페이스 가져오기
 다음을 추가하세요`using` Aspose.Tasks 네임스페이스를 가져오려면 C# 파일 시작 부분에 지시문을 추가하세요.
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

이제 프로젝트를 설정하고 필요한 네임스페이스를 가져왔으므로 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에 글꼴을 저장하는 과정을 살펴보겠습니다.
## 1단계: 문서 디렉터리 정의
MS 프로젝트 파일이 있는 문서 디렉터리의 경로를 설정합니다.
```csharp
String DataDir = "Your Document Directory";
```
## 2단계: FileStream 생성
글꼴 데이터를 쓰기 위해 FileStream을 만듭니다.
```csharp
var stream = new FileStream(DataDir + "fonts/" + args.FileName, FileMode.Create);
```
## 3단계: Args에 FileStream 할당
 생성된 FileStream을`Stream` 글꼴 저장 인수의 속성:
```csharp
args.Stream = stream;
```
## 4단계: 파일 URI 지정
프로젝트 디렉터리 내에서 글꼴 파일의 URI를 설정합니다.
```csharp
args.Uri = DataDir + "fonts/" + args.FileName;
```
## 5단계: 사용 후 FileStream 닫기
시스템 리소스를 해제하기 위해 사용 후 FileStream이 닫혀 있는지 확인하십시오.
```csharp
args.KeepStreamOpen = false;
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에 글꼴을 저장하는 과정을 다루었습니다. 위에 설명된 단계를 수행하면 글꼴 저장 기능을 .NET 애플리케이션에 원활하게 통합하여 프로젝트 관리 작업 흐름을 향상시킬 수 있습니다.
## FAQ
### 라이선스 없이 .NET용 Aspose.Tasks를 사용할 수 있나요?
아니요, 애플리케이션에서 Aspose.Tasks for .NET을 사용하려면 유효한 라이선스가 필요합니다. 그러나 평가 목적으로 임시 라이센스를 얻을 수 있습니다.
### Aspose.Tasks for .NET은 모든 버전의 Microsoft Project 파일과 호환됩니까?
.NET용 Aspose.Tasks는 MPP, XML 및 MPX 형식을 포함하여 2003년부터 Microsoft Project 파일 형식을 지원합니다.
### .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 다른 측면을 조작할 수 있습니까?
예, Aspose.Tasks for .NET은 작업, 리소스, 달력 등 MS 프로젝트 파일의 다양한 측면을 읽고, 쓰고, 수정할 수 있는 광범위한 기능을 제공합니다.
### Aspose.Tasks for .NET은 데스크탑과 웹 애플리케이션 모두에 적합합니까?
예, .NET용 Aspose.Tasks는 .NET 프레임워크를 사용하여 개발된 데스크톱 및 웹 애플리케이션 모두에서 사용할 수 있습니다.
### .NET용 Aspose.Tasks에 대한 추가 지원과 리소스는 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원을 받으려면[문서 페이지](https://reference.aspose.com/tasks/net/), Aspose.Tasks 웹사이트에서 튜토리얼과 예제를 살펴보세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
