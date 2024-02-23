---
title: Aspose.Tasks에서 간트 차트 보기 마스터하기
linktitle: Aspose.Tasks의 간트 차트 보기
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일에서 Gantt 차트 보기를 사용자 정의하는 방법을 알아보세요. 효율적인 프로젝트 관리를 위한 단계별 가이드입니다.
type: docs
weight: 22
url: /ko/net/tasks-project-management/gantt-chart-views/
---
## 소개
간트 차트는 프로젝트 관리에서 작업, 일정 및 종속성을 시각화하는 데 사용되는 강력한 도구입니다. Aspose.Tasks for .NET은 Microsoft Project 파일에서 Gantt 차트 보기 작업을 위한 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 활용하여 간트 차트 보기를 조작하고, 모양을 사용자 정의하고, PDF 파일로 저장하는 방법을 살펴보겠습니다.
## 전제조건
계속하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
 .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/)설명서에 제공된 설치 지침을 따르십시오.[여기](https://reference.aspose.com/tasks/net/).
### 2. 마이크로소프트 프로젝트 파일
Microsoft Project 파일을 준비합니다(`Project2.mpp`) Gantt 차트 보기 작업에 사용할 것입니다.
### 3. C# 및 .NET Framework에 대한 기본 지식
이 자습서에서는 사용자가 C# 프로그래밍 언어 및 .NET 프레임워크에 대한 기본 지식을 가지고 있다고 가정합니다.
## 네임스페이스 가져오기
Aspose.Tasks에서 Gantt 차트 보기 작업을 시작하기 전에 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

제공된 예제 코드를 여러 단계로 나누고 각 단계를 자세히 설명하겠습니다.
## 1단계: 프로젝트 파일 로드
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
이 단계에는 Microsoft Project 파일(`Project2.mpp` )의 인스턴스에`Project` 수업.
## 2단계: 상황 보고 날짜 설정
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
여기서는 프로젝트 상황 보고 날짜를 시작 날짜로 설정합니다.
## 3단계: 간트 차트 보기에 액세스
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
프로젝트에서 Gantt 차트 보기에 액세스합니다. Aspose.Tasks를 사용하면 간트 차트, 네트워크 다이어그램 및 작업 사용량과 같은 보기에 액세스할 수 있습니다.
## 4단계: 간트 차트 보기 사용자 정의
이제 Gantt 차트 보기의 다양한 측면을 사용자 정의해 보겠습니다.
### 막대 반올림 설정
```csharp
view.BarRounding = false;
```
간트 차트의 막대를 가장 가까운 날로 반올림할지 여부를 설정합니다.
### 막대 크기 설정
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
이는 차트의 Gantt 막대 높이를 결정합니다.
### 롤업 막대 숨기기
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
요약 작업을 확장할 때 롤업 막대를 숨길지 여부를 지정합니다.
### 휴무시간 색상 설정
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
간트 차트에서 휴무 시간의 색상을 정의합니다.
### 롤업 간트 바
```csharp
view.RollUpGanttBars = true;
```
간트 차트의 막대를 롤업해야 하는지 여부를 지정합니다.
### 막대 분할 표시
```csharp
view.ShowBarSplits = true;
```
간트 차트에 작업 분할을 표시해야 하는지 여부를 결정합니다.
### 그림을 보여주다
```csharp
view.ShowDrawings = true;
```
간트 차트의 그림을 표시해야 하는지 여부를 지정합니다.
### 시간 척도 크기 백분율
```csharp
view.TimescaleSizePercentage = 10;
```
시간 표시줄 계층의 단위 간 간격을 조정하기 위한 백분율을 설정합니다.
## 5단계: 간트 차트 보기를 PDF로 저장
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
마지막으로 사용자 정의된 간트 차트 보기를 PDF 파일로 저장합니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET에서 Gantt 차트 보기로 작업하는 방법을 배웠습니다. 제공된 단계를 따르면 프로젝트 요구 사항에 따라 Gantt 차트를 효율적으로 조작하고 사용자 정의할 수 있습니다.
## FAQ
### Q: Gantt 차트 막대의 모양을 추가로 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks는 색상, 모양 및 크기를 포함하여 Gantt 차트 막대의 모양을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### Q: Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: Gantt 차트 보기를 PDF가 아닌 다른 형식으로 내보낼 수 있습니까?
A: 물론 Aspose.Tasks는 Gantt 차트 보기를 PNG, JPEG 및 XPS를 포함한 다양한 형식으로 내보내는 것을 지원합니다.
### Q: Aspose.Tasks는 복잡한 프로젝트 일정 알고리즘을 지원합니까?
A: 예, Aspose.Tasks는 복잡한 프로젝트 일정을 효과적으로 처리할 수 있는 고급 일정 알고리즘을 제공합니다.
### Q: 도움을 구하거나 Aspose.Tasks에 대한 내 경험을 공유할 수 있는 커뮤니티 포럼이 있습니까?
 A: 네, 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 다른 사용자와 소통하고, 질문하고, 쿼리에 대한 해결책을 찾으세요.