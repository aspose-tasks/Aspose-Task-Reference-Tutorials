---
title: Aspose.Tasks에서 MS 프로젝트 페이지 보기 설정 사용자 정의
linktitle: Aspose.Tasks에서 페이지 보기 설정 구성
second_title: Aspose.태스크 .NET API
description: Microsoft Project 문서의 인쇄 형식을 조정하기 위해 .NET용 Aspose.Tasks에서 페이지 보기 설정을 구성하는 방법을 알아보세요.
weight: 21
url: /ko/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 페이지 보기 설정 사용자 정의

## 소개
Microsoft Project는 프로젝트 관리를 위한 강력한 도구이지만 프로젝트를 보고 인쇄하는 방식을 사용자 지정해야 하는 경우도 있습니다. Aspose.Tasks for .NET을 사용하면 특정 요구 사항에 맞게 페이지 보기 설정을 쉽게 구성할 수 있습니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET용 Aspose.Tasks: .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 파일: 페이지 보기 설정을 구성할 Microsoft Project 파일을 준비합니다.

## 네임스페이스 가져오기
먼저 .NET 프로젝트에서 Aspose.Tasks를 사용하려면 필요한 네임스페이스를 가져와야 합니다.
```csharp
    
    using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 파일 로드
 Microsoft Project 파일을 인스턴스에 로드하는 것부터 시작하세요.`Project` 수업.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## 2단계: 첫 번째 열 개수 설정
모든 페이지에 인쇄할 첫 번째 열 수를 지정합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## 3단계: 메모 인쇄
프로젝트와 함께 메모를 인쇄할지 여부를 선택합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## 4단계: 시간 척도를 페이지 끝에 맞추기
인쇄할 때 날짜 표시줄을 페이지 끝에 맞출지 여부를 결정합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## 5단계: 모든 시트 열 인쇄
뷰의 모든 시트 열을 인쇄할지 여부를 지정합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## 6단계: 빈 페이지 인쇄
보기의 빈 페이지를 인쇄할지 여부를 선택합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## 7단계: 모든 페이지의 첫 번째 열 인쇄
모든 페이지에 지정된 개수의 첫 번째 열을 인쇄할지 여부를 설정합니다.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## 8단계: 구성된 설정으로 프로젝트 저장
마지막으로 PDF와 같은 출력 형식을 지정하여 구성된 페이지 보기 설정으로 프로젝트를 저장합니다.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## 결론
.NET용 Aspose.Tasks에서 Microsoft Project 페이지 보기 설정을 구성하는 것은 간단하며 정확한 요구 사항에 맞게 인쇄 형식을 조정할 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 문서가 필요한 대로 정확하게 표시되는지 확인할 수 있습니다.
## FAQ
### Q: PDF 외에 다른 파일 형식에 대한 페이지 보기 설정을 구성할 수 있습니까?
A: 예, Aspose.Tasks는 XLSX, MPP 및 HTML을 포함하여 프로젝트 저장을 위한 다양한 파일 형식을 지원합니다.
### Q: 인쇄할 수 있는 열 수에 제한이 있습니까?
A: Aspose.Tasks를 사용하면 요구 사항에 따라 인쇄할 열 수를 사용자 정의할 수 있습니다.
### Q: 프로젝트마다 다른 페이지 보기 설정을 적용할 수 있나요?
A: 예, 작업하는 각 프로젝트 파일에 대해 독립적으로 페이지 보기 설정을 조정할 수 있습니다.
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 Microsoft Project 2003 및 이후 버전과의 호환성을 제공합니다.
### Q: Aspose.Tasks에 대한 추가 지원은 어디에서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 이용 중 발생한 문의사항이나 문제에 대해
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
