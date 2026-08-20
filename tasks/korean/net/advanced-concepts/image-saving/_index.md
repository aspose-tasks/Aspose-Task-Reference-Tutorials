---
date: 2026-03-05
description: Aspose.Tasks for .NET을 사용하여 이미지를 저장하고, 이미지를 포함한 HTML을 생성하며, 이미지 내보내기를
  사용자 지정하는 방법을 배웁니다. 프로젝트를 HTML로 저장하는 단계별 가이드.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET을 사용하여 이미지 저장하는 방법
url: /ko/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET로 이미지 저장하는 방법

## 소개

이 튜토리얼에서는 **Microsoft Project 파일에서 이미지를 저장하는 방법**을 Aspose.Tasks API for .NET을 사용해 알아봅니다. 차트를 보고서에 삽입하거나, 프로젝트 시각화가 포함된 HTML 페이지를 생성하거나, 단순히 다이어그램 리소스를 내보내야 할 때, 아래 단계가 프로젝트 객체 설정부터 이미지‑내보내기 콜백 커스터마이징까지 전체 과정을 안내합니다.

## 빠른 답변
- **Aspose.Tasks에서 “이미지 저장”이란 무엇인가요?**  
  `IImageSavingCallback` 인터페이스를 사용해 시각 리소스가 디스크에 기록되는 위치와 방식을 제어하는 것을 의미합니다.
- **이미지가 포함된 HTML로 프로젝트를 저장할 수 있나요?**  
  예, `HtmlSaveOptions`와 이미지 저장 콜백을 함께 사용하면 **이미지가 포함된 HTML**을 **프로젝트를 HTML로 저장**할 수 있습니다.
- **이미지 내보내기에 라이선스가 필요합니까?**  
  테스트용 임시 평가 라이선스로 가능하지만, 실제 운영 환경에서는 정식 라이선스가 필요합니다.
- **지원되는 .NET 버전은 무엇인가요?**  
  Aspose.Tasks for .NET은 .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+를 지원합니다.
- **이미지 내보내기(포맷, 폴더, 파일명)를 커스터마이징할 수 있나요?**  
  물론입니다 – 콜백을 통해 파일명, 포맷, 저장 위치를 완전히 제어할 수 있습니다.

## Aspose.Tasks 컨텍스트에서 “이미지 저장”이란?
이미지 저장은 프로젝트 파일에서 시각 요소(차트, 간트 바, 리소스 그래픽 등)를 추출하여 이미지 파일(PNG, JPEG 등)로 기록하는 것을 의미합니다. Aspose.Tasks는 정확한 위치, 파일명 규칙, 이미지 포맷 등을 지정할 수 있는 유연한 콜백 메커니즘을 제공합니다.

## Aspose.Tasks로 이미지를 저장해야 하는 이유
- **전체 프로그래밍 제어** – UI를 직접 조작할 필요가 없습니다.  
- **크로스‑플랫폼** – .NET Core를 통해 Windows, Linux, macOS에서 동작합니다.  
- **고품질 렌더링** – 이미지가 원본 Project 뷰와 동일한 품질을 유지합니다.  
- **쉬운 HTML 생성** – `HtmlSaveOptions`와 이미지 콜백을 결합하면 **이미지가 포함된 HTML**을 자동으로 **생성**할 수 있습니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있어야 합니다:

1. 개발 머신에 Visual Studio가 설치되어 있어야 합니다.  
2. [여기](https://releases.aspose.com/tasks/net/)에서 Aspose.Tasks for .NET을 다운로드합니다.  
3. C# 및 .NET 프로젝트 구조에 대한 기본 지식이 필요합니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 소스 파일에 추가합니다:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1단계: Project 객체 생성

작업하려는 Microsoft Project 파일을 로드합니다:

```csharp
var project = new Project("Project1.mpp");
```

## 2단계: 저장 옵션 정의

이미지‑저장 콜백을 포함할 HTML 저장 옵션을 생성합니다:

```csharp
var options = GetSaveOptions(1);
```

## 3단계: 프로젝트를 HTML로 저장 (save project as html)

이제 프로젝트를 HTML 파일로 내보냅니다. HTML에서 참조되는 이미지는 다음 단계에서 정의할 콜백에 의해 생성됩니다:

```csharp
project.Save("document_out.html", options);
```

## 4단계: 이미지 저장 콜백 구현 (customize image export)

`IImageSavingCallback` 인터페이스를 구현합니다. 여기서 **이미지 내보내기** 동작을 **커스터마이징**합니다:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## 5단계: 지정된 디렉터리에 이미지 저장

`ImageSaving` 메서드 내부에서 각 이미지가 저장될 위치를 결정합니다. 아래 예시는 PNG 리소스를 다른 포맷과 구분합니다:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## 6단계: 저장 옵션 지정 (콜백 포함)

폰트, CSS, 이미지에 대한 콜백을 연결합니다. 이를 통해 모든 시각 요소가 일관되게 처리됩니다:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 일반적인 문제와 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| 생성된 HTML에 이미지가 표시되지 않음 | 콜백이 유효한 파일 경로를 지정하지 않음 | `args.Path`가 쓰기 가능한 폴더를 가리키는지 확인하고 `args.ImageStream`을 올바르게 설정합니다. |
| PNG 파일이 잘못된 확장자로 저장됨 | 조건문이 “png” 접미사만 확인함 | `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)`를 사용해 견고하게 감지합니다. |
| 파일을 이동한 후 HTML 참조가 깨짐 | 상대 경로가 이동 후 변경됨 | HTML과 이미지 폴더를 함께 두거나 `options.ImageFolder`를 적절히 업데이트합니다. |

## 결론

이 단계를 따라 하면 **프로젝트 파일에서 이미지를 저장하는 방법**, **프로젝트를 HTML로 저장하는 방법**, 그리고 **애플리케이션 폴더 구조에 맞게 이미지 내보내기를 커스터마이징하는 방법**을 알게 됩니다. 이를 통해 **이미지가 포함된 HTML**을 보고서, 문서 포털, 웹 대시보드 등에 손쉽게 삽입할 수 있습니다.

## 자주 묻는 질문

**Q1: Aspose.Tasks를 사용해 HTML 외의 다른 포맷으로 프로젝트 파일을 조작할 수 있나요?**  
A1: 예, Aspose.Tasks는 PDF, XLSX, MPP 등 다양한 포맷을 지원합니다.

**Q2: Aspose.Tasks가 클라우드 스토리지 연동을 지원하나요?**  
A2: 예, Aspose.Tasks는 Amazon S3, Google Drive 등 인기 있는 클라우드 스토리지 서비스와 연동할 수 있는 API를 제공합니다.

**Q3: Aspose.Tasks가 .NET Core와 호환되나요?**  
A3: 예, Aspose.Tasks는 .NET Core와 호환되어 크로스‑플랫폼 애플리케이션 개발이 가능합니다.

**Q4: 저장된 이미지의 외관을 커스터마이징할 수 있나요?**  
A4: 예, 콜백 메서드 내에서 이미지 저장 로직을 수정하여 이미지의 외관을 자유롭게 조정할 수 있습니다.

**Q5: 평가용 체험판을 제공하나요?**  
A5: 예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks의 무료 체험판을 받을 수 있습니다.

---

**마지막 업데이트:** 2026-03-05  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}