---
title: Aspose.Tasks를 사용하여 MS 프로젝트 진행 라인 처리
linktitle: Aspose.Tasks에서 진행 라인 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일의 진행 라인을 조작하여 프로젝트 시각화 및 관리를 향상시키는 방법을 알아보세요.
type: docs
weight: 15
url: /ko/net/project-management-integration/progress-lines/
---
## 소개
Microsoft Project(MS Project)는 프로젝트 관리를 위한 강력한 도구로, 사용자가 프로젝트의 다양한 측면을 추적할 수 있습니다. MS Project의 중요한 기능 중 하나는 진행 라인을 시각화하는 기능으로, 이해관계자가 프로젝트 상태와 궤적을 이해하는 데 도움이 됩니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks 라이브러리를 사용하여 MS 프로젝트에서 진행 라인을 처리하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. Visual Studio: Visual Studio 또는 기타 선호하는 .NET 개발 환경을 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 가져오세요.
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
이제 진행 라인 처리의 각 단계를 자세히 살펴보겠습니다.
## 1단계: 프로젝트 파일 로드
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 여기서는 MS 프로젝트 파일을 로드합니다.`Project2.mpp` 상태 보고 날짜를 설정합니다.
## 2단계: 간트 차트 보기 정의
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
추가 조작을 위해 프로젝트 보기를 Gantt 차트 보기로 변환했습니다.
## 3단계: 진행 라인 정의
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Gantt 차트 보기의 진행 라인을 초기화합니다.
## 4단계: 진행률 설정 구성
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
여기서는 선 색상, 패턴, 글꼴 등과 같은 진행 선에 대한 다양한 속성을 설정합니다.
## 5단계: 진행 라인 구성 확인
```csharp
// 출력 진행 라인 설정
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// 기타 설정 출력...
```
검증을 위해 구성된 진행 라인 설정을 출력합니다.
## 6단계: 프로젝트 파일 저장
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
마지막으로 수정된 프로젝트 파일을 진행 라인과 함께 저장합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 진행 라인을 처리하는 방법을 배웠습니다. 다음 단계를 수행하면 프로그래밍 방식으로 MS 프로젝트 파일의 진행 라인을 효과적으로 사용자 정의하고 시각화할 수 있습니다.
## FAQ
### Q: 진행 라인의 모양을 추가로 사용자 정의할 수 있나요?
A: 예. 선 색상, 패턴, 글꼴 등 다양한 속성을 요구 사항에 맞게 조정할 수 있습니다.
### Q: Aspose.Tasks는 다른 프로젝트 관리 기능을 지원합니까?
A: 예, Aspose.Tasks는 작업, 리소스 및 달력을 포함하여 MS 프로젝트 파일의 다양한 측면을 조작하기 위한 광범위한 지원을 제공합니다.
### Q: Aspose.Tasks를 다른 .NET 라이브러리와 통합할 수 있나요?
A: 물론 Aspose.Tasks는 다른 .NET 라이브러리와 원활하게 통합되도록 설계되어 프로젝트 관리 애플리케이션을 더욱 향상시킬 수 있습니다.
### Q: Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 A: 예, Aspose.Tasks 포럼에서 유용한 리소스를 찾고 도움을 구할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks는 평가 목적으로 임시 라이선스를 제공합니까?
 A: 예, 다음에서 평가용 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).