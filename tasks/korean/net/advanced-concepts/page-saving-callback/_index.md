---
date: 2026-03-16
description: Aspose.Tasks for .NET에서 페이지 저장 콜백을 구현하는 방법을 배우고, 다중 페이지 문서 출력 스트림을 맞춤형으로
  처리할 수 있습니다.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 페이지 저장 콜백 구현
url: /ko/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 페이지 저장 콜백 구현하기

## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 **페이지 저장 콜백을 구현**하는 방법을 배웁니다. 이 강력한 기능을 사용하면 다중 페이지 문서의 각 페이지를 원하는 스트림으로 전달할 수 있어 출력이 저장되거나 추가 처리되는 방식을 완전히 제어할 수 있습니다.

## 빠른 답변
- **페이지 저장 콜백은 무엇을 하나요?** 각 렌더링된 페이지를 별개의 스트림에 캡처하여 개별적으로 처리할 수 있게 합니다.  
- **어떤 형식으로 내보낼 수 있나요?** `ImageSaveOptions`에서 지원하는 모든 형식, 예: PNG, JPEG, PDF.  
- **라이선스가 필요합니까?** 실제 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **.NET Core와 함께 사용할 수 있나요?** 예, Aspose.Tasks는 .NET Core 및 .NET 5/6+를 완전히 지원합니다.  
- **콜백이 스레드 안전한가요?** 콜백은 렌더링을 수행하는 동일한 스레드에서 실행되므로 일반적인 스레드 안전 규칙이 적용됩니다.

## **페이지 저장 콜백 구현**이란?
**페이지 저장 콜백 구현** 패턴을 사용하면 Aspose.Tasks 저장 파이프라인에 사용자 정의 로직을 삽입할 수 있습니다. 파일에 직접 쓰는 대신 각 페이지에 대해 `Stream` 객체를 받아 메모리에 저장하거나 클라우드 스토리지에 업로드하거나 추가 처리를 수행할 수 있습니다.

## 콜백을 사용해 프로젝트를 PNG로 내보내는 이유는?
프로젝트를 PNG로 내보내면 각 Gantt 차트 페이지의 래스터 이미지가 생성되어 보고서, 이메일 또는 웹 페이지에 삽입하기에 이상적입니다. 콜백을 사용하면 디스크에 임시 파일을 만들지 않고 각 페이지를 별도의 `MemoryStream`에 보관할 수 있습니다.

## 사전 요구 사항

1. **C# 지식** – 클래스, 인터페이스 및 스트림에 대한 기본적인 이해.  
2. **Aspose.Tasks for .NET** – [여기](https://releases.aspose.com/tasks/net/)에서 다운로드하고 설치합니다.  
3. **IDE** – Visual Studio, Rider 또는 .NET 호환 편집기.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## 단계 1: Project 객체 생성

기존 MPP 파일을 `Project` 인스턴스로 로드합니다:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 단계 2: Image Save Options 구성

PNG 출력용 `ImageSaveOptions`를 설정하고 사용자 정의 콜백을 연결합니다:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **팁:** `RenderToSinglePage = false`로 설정하면 각 Gantt 차트 페이지가 별도로 렌더링되어 콜백이 개별 스트림을 받는 데 필수적입니다.

## 단계 3: 콜백으로 프로젝트 저장

실제 스트림은 콜백이 제공하므로 `Stream.Null`을 전달하면서 `Save` 메서드를 호출합니다:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 단계 4: 저장된 페이지 스트림 처리

저장 작업이 완료되면 콜백이 `MemoryStream` 객체 컬렉션(페이지당 하나)을 보유합니다. 이제 이를 순회할 수 있습니다:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## 단계 5: 사용자 정의 페이지 저장 콜백 구현

`IPageSavingCallback`을 구현하는 sealed 클래스를 생성합니다. 이 클래스는 각 페이지의 스트림을 캡처하여 나중에 사용할 리스트에 저장합니다.

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
        // Perform any cleanup or finalization
    }
}
```

## 일반적인 함정 및 문제 해결

| 문제 | 원인 | 해결책 |
|------|------|--------|
| **페이지가 반환되지 않음** | `RenderToSinglePage`가 `true`로 남아 있음. | 별도 페이지를 생성하려면 `RenderToSinglePage = false`로 설정하십시오. |
| **스트림이 비어 있음** | `KeepStreamOpen`이 `true`로 설정되었고 이후에 해제되지 않음. | `false`(기본값)로 유지하고 콜백이 스트림을 자동으로 닫도록 하십시오. |
| **메모리 부족 오류** | 매우 큰 프로젝트가 다수의 고해상도 PNG를 생성함. | 스트림을 하나씩 처리하거나 VM 메모리 제한을 늘리십시오. |

## 자주 묻는 질문

**Q1: Aspose.Tasks에서 페이지 저장 콜백이란?**  
A: 페이지 저장 콜백은 다중 페이지 문서의 각 페이지 저장 과정을 가로채어 해당 페이지에 대한 사용자 정의 `Stream`을 제공하게 합니다.

**Q2: 이 콜백을 사용해 페이지를 다른 형식으로 저장할 수 있나요?**  
A: 예. `SaveFileFormat`을 변경하면 PNG, JPEG, PDF, SVG 등으로 내보낼 수 있습니다.

**Q3: Aspose.Tasks가 .NET Core와 호환되나요?**  
A: 전적으로 지원합니다. Aspose.Tasks는 .NET Core, .NET 5 및 .NET 6을 지원합니다.

**Q4: 페이지 저장 과정에서 오류를 어떻게 처리할 수 있나요?**  
A: 콜백 로직을 try/catch 블록으로 감싸고 예외를 로그에 기록하십시오. `OnFinish` 메서드는 최종 정리 작업에 적합한 위치입니다.

**Q5: Aspose.Tasks에 대한 추가 자료와 지원을 어디서 찾을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 도움을 받을 수 있고, 문서는 [여기](https://reference.aspose.com/tasks/net/)에서 확인하거나, 추가 기능 및 라이선스 옵션은 [Aspose.Tasks 웹사이트](https://purchase.aspose.com/buy)에서 확인하십시오.

---

**마지막 업데이트:** 2026-03-16  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}