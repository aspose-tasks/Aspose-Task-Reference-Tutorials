---
title: Aspose.Tasks에서 MS 프로젝트 리소스 보기 열 사용자 정의
linktitle: Aspose.Tasks에서 리소스 보기 열 사용자 정의
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS Project 리소스 보기 열을 효율적으로 사용자 정의하는 방법을 알아보세요. 더 나은 프로젝트 관리를 위해 맞춤형 보기를 만듭니다.
weight: 17
url: /ko/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 리소스 보기 열 사용자 정의

## 소개
Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있는 강력한 API입니다. 프로젝트 관리의 일반적인 작업 중 하나는 특정 정보를 표시하도록 보기를 사용자 정의하는 것입니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS Project 리소스 보기 열을 사용자 정의하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. Microsoft 프로젝트 파일: 테스트에 편리한 샘플 MS 프로젝트 파일을 준비하세요.
3. 개발 환경: .NET 프레임워크로 구성된 개발 환경입니다.
## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 프로젝트로 가져오겠습니다.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 1단계: 프로젝트 파일 로드
Aspose.Tasks API를 사용하여 MS 프로젝트 파일을 로드합니다.
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 2단계: 리소스 가져오기 및 옵션 정의
다음으로, PDF 저장 옵션을 사용자 정의하고 정의하려는 보기 열이 있는 리소스를 가져옵니다.
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## 3단계: 맞춤 열 정의
이제 리소스 보기에 대한 사용자 정의 열을 정의하십시오. 다양한 필드를 지정하고 사용자 정의 계산을 위해 대리자를 사용할 수도 있습니다.
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## 4단계: 열 반복
정의된 열을 반복하고 해당 속성을 표시합니다.
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## 5단계: 사용자 정의된 보기 저장
마지막으로 사용자 정의 보기를 설정하고 PDF 파일로 저장합니다.
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
다음 단계를 수행하면 .NET용 Aspose.Tasks를 사용하여 MS Project 리소스 보기 열을 효율적으로 사용자 정의할 수 있습니다.
## 결론
MS 프로젝트 리소스 보기 열을 사용자 정의하는 것은 프로젝트 요구 사항에 맞는 관련 정보를 표시하는 데 필수적입니다. .NET용 Aspose.Tasks를 사용하면 이 작업이 간단하고 효율적이 되어 사용자 정의 보기를 쉽게 만들 수 있습니다.
## FAQ
### 리소스 외에 다른 요소에 대한 보기를 사용자 정의할 수 있나요?
예, Aspose.Tasks를 사용하면 작업, 할당 및 기타 프로젝트 요소에 대한 사용자 정의도 가능합니다.
### Aspose.Tasks는 PDF 이외의 형식으로 뷰 저장을 지원합니까?
예, XLSX, HTML, 이미지 등 다양한 형식으로 뷰를 저장할 수 있습니다.
### 사용자 정의 보기에 서식을 적용할 수 있습니까?
물론, Aspose.Tasks는 사용자 정의된 보기의 모양을 향상시키기 위한 광범위한 서식 옵션을 제공합니다.
### 프로젝트 데이터 변경에 따라 사용자 정의 보기를 동적으로 업데이트할 수 있습니까?
예, 기본 프로젝트 데이터가 변경될 때마다 사용자 정의 보기를 업데이트하고 다시 생성할 수 있습니다.
### Aspose.Tasks는 크로스 플랫폼 개발을 지원합니까?
.NET용 Aspose.Tasks는 주로 .NET 플랫폼을 대상으로 하지만 Java 및 기타 플랫폼에서 사용할 수 있는 버전도 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
