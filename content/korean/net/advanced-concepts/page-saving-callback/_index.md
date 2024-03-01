---
title: Aspose.Tasks에서 페이지 저장 콜백 구현
linktitle: Aspose.Tasks에서 페이지 저장 콜백 구현
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 페이지 저장 콜백을 구현하여 여러 페이지로 구성된 문서 출력 스트림을 사용자 정의 처리하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/net/advanced-concepts/page-saving-callback/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 페이지 저장 콜백을 구현하는 방법을 살펴보겠습니다. 이 기능을 사용하면 여러 페이지로 구성된 문서를 사용자 제공 스트림에 저장할 수 있어 출력 처리 시 유연성과 사용자 정의 기능을 제공할 수 있습니다.

## 전제 조건:

시작하기 전에 다음 사항이 있는지 확인하세요.

1. C# 프로그래밍 언어에 대한 지식: C# 구문과 개념에 대한 기본적인 이해가 있어야 합니다.
   
2.  .NET용 Aspose.Tasks 설치: 개발 환경에 Aspose.Tasks 라이브러리를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

3. 개발 환경 설정: Visual Studio와 같은 .NET 개발을 위해 선호하는 IDE를 설정합니다.

## 네임스페이스 가져오기:

시작하려면 C# 코드에서 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## 1단계: 프로젝트 객체 생성

 인스턴스화`Project` 기존 프로젝트 파일을 로드하여 객체를 생성합니다.

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 2단계: 이미지 저장 옵션 구성

 정의하다`ImageSaveOptions`다음을 설정하여 페이지 저장 동작을 사용자 정의합니다.`PageSavingCallback` 재산:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## 3단계: 콜백으로 프로젝트 저장

구성된 이미지 저장 옵션을 사용하여 프로젝트를 저장합니다.

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 4단계: 저장된 페이지 스트림 처리

콜백에서 제공하는 페이지 스트림을 반복하여 각 페이지를 개별적으로 처리합니다.

```csharp
foreach (var stream in callback.PageStreams)
{
    // 각 페이지 스트림 처리
}
```

## 5단계: 사용자 정의 페이지 저장 콜백 구현

 구현하는 클래스를 생성합니다.`IPageSavingCallback` 페이지 저장을 처리하는 인터페이스:

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // 정리 또는 마무리 수행
    }
}
```

## 결론:

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 페이지 저장 콜백을 구현하여 여러 페이지의 문서를 별도의 스트림에 저장할 수 있는 방법을 배웠습니다. 다음 단계를 수행하면 애플리케이션의 기능을 향상하고 사용자 정의된 출력 처리를 달성할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks의 페이지 저장 콜백이란 무엇입니까?

A1: 페이지 저장 콜백은 사용자가 각 페이지에 대한 스트림을 개별적으로 제공하여 다중 페이지 문서의 저장 프로세스를 사용자 정의할 수 있도록 하는 Aspose.Tasks의 기능입니다.

### Q2: 이 콜백을 사용하여 페이지를 저장하기 위해 다른 형식을 사용할 수 있습니까?

A2: 예, 콜백과 함께 페이지를 저장하기 위해 PNG, JPEG, PDF 등과 같은 Aspose.Tasks에서 지원하는 다양한 파일 형식을 활용할 수 있습니다.

### Q3: Aspose.Tasks는 .NET Core와 호환됩니까?

A3: 예, Aspose.Tasks는 .NET Core를 지원하므로 개발자는 크로스 플랫폼 애플리케이션에서 해당 기능을 사용할 수 있습니다.

### Q4: 페이지 저장 과정에서 발생하는 오류는 어떻게 처리하나요?

대답 4: 콜백 메서드 내에 오류 처리 메커니즘을 구현하여 예외를 관리하고 애플리케이션의 견고성을 보장할 수 있습니다.

### Q5: Aspose.Tasks에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?

 A5: 다음을 방문할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 도움이 필요한 경우 문서에 액세스하세요.[여기](https://reference.aspose.com/tasks/net/) , 또는 추가 기능 및 라이선스 옵션을 살펴보세요.[Aspose.Tasks 웹사이트](https://purchase.aspose.com/buy).