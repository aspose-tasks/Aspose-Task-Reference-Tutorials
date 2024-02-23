---
title: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 뷰 열 마스터링
linktitle: Aspose.Tasks에서 뷰 열 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로젝트 시각화를 향상하세요. MS 프로젝트 보기 열을 단계별로 처리하는 방법을 알아보세요. 효율성과 맞춤화를 강화하세요.
type: docs
weight: 12
url: /ko/net/view-wbs-code-configuration/view-columns/
---
## 소개
프로젝트 관리 영역에서 Aspose.Tasks for .NET은 Microsoft Project 파일을 처리하기 위한 강력한 툴킷으로 돋보입니다. 프로젝트 시각화의 필수 측면 중 하나는 뷰 열을 효율적으로 관리하는 것입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 MS 프로젝트 보기 열을 처리하여 프로젝트 보기를 사용자 정의하고 최적화하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.Tasks](https://reference.aspose.com/tasks/net/).
2. Microsoft Project 파일: 이 튜토리얼에 사용할 Microsoft Project 파일(MPP)을 준비합니다.
3. 개발 환경: Visual Studio 또는 기타 선호하는 IDE를 사용하여 .NET 개발 환경을 설정합니다.
## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 프로젝트로 가져옵니다. 이러한 네임스페이스는 Aspose.Tasks 작업을 위한 필수 클래스와 메서드를 제공합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Drawing;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1단계: 프로젝트 파일 로드
Aspose.Tasks를 사용하여 Microsoft Project 파일을 로드하는 것부터 시작하세요. 문서 디렉터리의 경로가 올바른지 확인하세요.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```
## 2단계: 보기 열 정의
다음으로, 프로젝트 보기에 포함할 보기 열을 정의하세요. 이 예에서는 자원 이름, 실제 작업 시간 및 자원 비용에 대한 열을 만듭니다.
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost)
};
```
## 3단계: 텍스트 스타일 사용자 정의
향상된 시각적 매력을 위해 콜백을 사용하여 텍스트 스타일을 맞춤설정하세요. 이 튜토리얼에서는 사용자 정의 콜백(`MyTextStyleCallback`) 텍스트 스타일을 수정합니다.
```csharp
columns[0].TextStyleModificationCallback = new MyTextStyleCallback();
```
## 4단계: 열 반복
정의된 열을 반복하여 각 열에 대한 정보를 검사하고 표시합니다.
```csharp
foreach (var column in columns)
{
    Console.WriteLine("Column Name: " + column.Name);
    Console.WriteLine("Column Field: " + column.Field);
    Console.WriteLine("Column Width: " + column.Width);
    Console.WriteLine("Column Callback: " + column.TextStyleModificationCallback);
    Console.WriteLine();
}
```
## 5단계: 프로젝트 보기 저장
보기 및 형식 옵션을 지정한 다음 프로젝트 보기를 PDF 파일로 저장합니다.
```csharp
var options = new PdfSaveOptions();
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save(OutDir + "WorkWithViewColumn_out.pdf", options);
```
## 결론
축하해요! .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 보기 열을 처리하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 더 나은 시각화 및 분석을 위해 프로젝트 보기 사용자 정의에 대한 기본적인 이해를 제공합니다.

## 자주 묻는 질문
### Q: Aspose.Tasks를 다른 프로젝트 관리 도구와 함께 사용할 수 있나요?
A: Aspose.Tasks는 주로 Microsoft Project 파일에 중점을 둡니다. 그러나 프로젝트 요구 사항에 따라 통합 가능성을 탐색할 수 있습니다.
### Q: 보기 열 사용자 정의 문제를 해결하려면 어떻게 해야 합니까?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 귀하가 직면하는 모든 문제에 대한 지역 사회 지원 및 도움을 받으십시오.
### Q: Aspose.Tasks를 구매하기 전에 사용할 수 있는 평가판이 있나요?
A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
###  Q. 의의는 무엇인가요?`MyTextStyleCallback` class in the tutorial?
 답:`MyTextStyleCallback` 이 클래스에서는 특정 보기에서 향상된 시각적 표현을 위해 텍스트 스타일을 사용자 정의하는 방법을 보여줍니다.
### Q: Aspose.Tasks에 대한 추가 리소스와 문서는 어디서 찾을 수 있나요?
 답: 다음을 참조하세요.[Aspose.Tasks 문서](https://reference.aspose.com/tasks/net/) 자세한 지침과 리소스를 확인하세요.