---
date: 2026-03-21
description: Aspose.Tasks for .NET에서 프로젝트를 이미지로 저장할 때 이미지 내보내기와 BitmapInvalidSizeException
  처리 방법을 배웁니다. 프로젝트를 이미지로 저장하고 PNG로 내보내는 단계가 포함됩니다.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 이미지를 내보내는 방법 및 잘못된 크기 예외 처리
url: /ko/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 이미지 내보내기 – Aspose.Tasks에서 Bitmap의 잘못된 크기 예외 처리

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일에서 **이미지를 내보내는 방법**을 배우고, 더 중요한 것은 프로세스 중에 발생할 수 있는 `BitmapInvalidSizeException`을 잡는 방법을 배웁니다. 프로젝트를 이미지로 내보내는 것은 보고 대시보드, 문서화, 또는 일정의 시각적 스냅샷을 공유하기 위한 일반적인 요구 사항입니다. 이 가이드를 마치면 **프로젝트를 이미지로 저장**하는 방법을 안정적으로 사용할 수 있으며, **프로젝트를 PNG 형식으로 내보내기**도 예기치 않은 충돌 없이 수행할 수 있습니다.

## 빠른 답변
- **이미지를 내보낼 때 발생할 수 있는 예외는 무엇입니까?** `BitmapInvalidSizeException`  
- **예제에서 사용된 형식은 무엇입니까?** PNG (`SaveFileFormat.Png`)  
- **특별한 라이선스가 필요합니까?** 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **타임스케일을 변경할 수 있나요?** 예 – 타임스케일 단위(분, 시간, 일 등)를 설정할 수 있습니다.  
- **코드가 .NET Core와 호환됩니까?** 물론입니다 – 동일한 API가 .NET Framework와 .NET Core에서 모두 작동합니다.

## BitmapInvalidSizeException이란?
`BitmapInvalidSizeException`은 이미지에 대해 계산된 비트맵 크기가 지원 범위를 벗어났을 때(예: 너비 또는 높이가 0이거나 내부 제한을 초과) 발생합니다. 이는 일반적으로 타임스케일이나 보기 설정으로 인해 이미지가 너무 크거나 너무 작게 생성될 때 발생합니다.

## 프로젝트를 이미지로 내보내는 이유
- **시각적 보고** – Gantt 차트를 PDF, Word 문서 또는 웹 페이지에 삽입합니다.  
- **크로스 플랫폼 공유** – PNG 파일은 Microsoft Project 없이도 모든 장치에서 볼 수 있습니다.  
- **성능** – 이미지는 전체 프로젝트 파일에 비해 가볍기 때문에 빠른 미리보기에 적합합니다.

## 사전 요구 사항
1. C# 및 .NET 개발에 대한 기본 지식.  
2. Aspose.Tasks for .NET이 설치되어 있음(NuGet 패키지 `Aspose.Tasks`).  
3. 샘플 Microsoft Project 파일(예: `Blank2010.mpp`).  

## 네임스페이스 가져오기
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 단계별 가이드

### 단계 1: 프로젝트 초기화 및 보기 선택
먼저, `Project` 인스턴스를 생성하고 렌더링할 보기를 선택합니다(여기서는 첫 번째 Gantt 차트 보기를 사용합니다).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### 단계 2: 이미지 저장 옵션 구성 (프로젝트를 PNG로 내보내기)
원하는 이미지 형식을 설정하고 Aspose.Tasks에 보기에서 정의된 타임스케일을 사용하도록 지정합니다.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### 단계 3: 타임스케일 단위 조정 (이미지 크기 제어)
타임스케일을 변경하면 비트맵 크기에 영향을 줍니다. 이 예제에서는 이미지 크기를 관리하기 쉬운 **분** 단위를 사용합니다.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### 단계 4: 프로젝트를 이미지로 저장 시도
이 코드는 실제 **프로젝트를 이미지로 저장** 작업을 수행합니다.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### 단계 5: BitmapInvalidSizeException 잡기 및 처리
저장 호출을 `try / catch` 블록으로 감싸서 비트맵 크기가 유효하지 않을 경우 애플리케이션이 정상적으로 대응하도록 합니다.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|-------|-------|----------|
| 타임스케일 조정 후에도 예외가 계속 발생함 | 타임스케일이 여전히 너무 큰 비트맵을 생성 | `view.MiddleTimescaleTier.Count`를 줄이거나 더 거친 `TimescaleUnit`(예: Hours)으로 전환합니다. |
| 출력 파일이 비어 있음 | 잘못된 파일 경로나 쓰기 권한 부족 | `DataDir`이 쓰기 가능한 폴더를 가리키는지 확인하고, 형식을 변경할 경우 파일 이름이 `.png`로 끝나는지 확인합니다. |
| 이미지 품질이 낮음 | 기본 DPI가 낮을 수 있음 | `options.DpiX`와 `options.DpiY`를 더 높은 값(예: 300)으로 설정합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks에서 BitmapInvalidSizeException이 발생하는 원인은 무엇인가요?**  
A: 계산된 비트맵 크기가 유효하지 않을 때 발생합니다—보통 타임스케일이 너무 큰 이미지나 너비/높이가 0인 이미지를 만들 때 발생합니다.

**Q: 이미지를 내보낼 때 타임스케일을 맞춤 설정할 수 있나요?**  
A: 예. 튜토리얼에 표시된 대로 `view.MiddleTimescaleTier.Unit`와 `Count`를 필요에 맞게 수정할 수 있습니다.

**Q: Aspose.Tasks가 PNG 외에 다른 이미지 형식을 지원하나요?**  
A: 물론입니다. `SaveFileFormat`에는 JPEG, BMP, GIF, TIFF도 포함됩니다. `ImageSaveOptions`에서 열거형 값을 변경하면 됩니다.

**Q: 프로덕션 환경에서 이미지를 내보내려면 라이선스가 필요합니까?**  
A: 예. 라이브러리는 평가 모드에서도 작동하지만, 상용 라이선스를 사용하면 평가 제한이 해제되고 전체 지원을 받을 수 있습니다.

**Q: 내보낸 PNG의 품질을 어떻게 향상시킬 수 있나요?**  
A: DPI 설정(`options.DpiX`와 `options.DpiY`)을 높이거나 보기의 타임스케일을 조정하여 더 큰 비트맵을 생성합니다.

## 결론
위 단계들을 따라 하면 이제 Project 파일에서 **이미지를 내보내는 방법**, **프로젝트를 이미지로 저장하는 방법**, 그리고 `BitmapInvalidSizeException`을 우아하게 처리하는 방법을 알게 됩니다. 이러한 기술은 보고 파이프라인을 더욱 견고하게 만들고, 다양한 프로젝트 규모와 타임스케일에 걸쳐 시각적 내보내기가 안정적으로 작동하도록 보장합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-03-21  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose