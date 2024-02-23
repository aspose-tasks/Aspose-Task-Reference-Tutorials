---
title: Aspose.Tasks에서 간트 차트 시간 척도 계층을 구성합니다.
linktitle: Aspose.Tasks에서 시간 척도 계층 구성
second_title: Aspose.태스크 .NET API
description: 정확한 프로젝트 타임라인 시각화를 위해 Gantt 차트 보기에서 기간 계층을 구성하려면 .NET용 Aspose.Tasks를 탐색하세요. #Aspose.Tasks #MS 프로젝트
type: docs
weight: 16
url: /ko/net/text-view-configuration/timescale-tiers/
---
## 소개
프로젝트 관리의 역동적인 환경에서 효과적인 시각화는 일정과 기한을 이해하는 데 매우 중요합니다. .NET용 Aspose.Tasks는 강력한 도구 세트를 제공하며, 이 튜토리얼에서는 Gantt 차트 보기에서 최적의 표현을 위해 시간 척도 계층을 구성하는 방법을 살펴보겠습니다. 프로젝트 시각화를 향상하려면 다음 단계별 지침을 따르십시오.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- C# 및 .NET에 대한 기본 지식.
- .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- .NET 애플리케이션 개발을 위해 설정된 개발 환경입니다.
## 네임스페이스 가져오기
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
이제 제공된 예제의 각 단계를 분석해 보겠습니다.
## 1단계: 프로젝트 초기화 및 작업 링크 추가
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
여기서는 프로젝트를 생성하고 "작업 1"과 "작업 2" 사이에 작업 링크를 설정합니다.
## 2단계: 간트 차트 보기 구성
```csharp
var view = (GanttChartView)project.DefaultView;
```
사용자 정의를 위해 간트 차트 보기에 액세스합니다.
## 3단계: 중간 기간 계층 조정
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
특정 레이블 및 정렬을 사용하여 주를 표시하도록 중간 기간 계층을 사용자 정의합니다.
## 4단계: 최상위 기간 계층 추가
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
월을 나타내기 위해 최상위 기간 계층을 추가합니다.
## 5단계: 중간 계층 날짜 사용자 정의
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
더 나은 시각화를 위해 월 레이블을 개인화하십시오.
## 6단계: 프로젝트 기간 설정
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
전체 일정을 제어하려면 프로젝트 기간을 정의하세요.
## 7단계: 사용자 정의된 시간 단위로 프로젝트 저장
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
정의된 기간 설정으로 프로젝트를 저장합니다.
## 결론
결론적으로 Aspose.Tasks for .NET에서 기간 계층을 구성하면 프로젝트 일정을 보다 맞춤화되고 시각적으로 매력적으로 표현할 수 있습니다. 이러한 단계를 통해 프로젝트 관리 요구 사항을 정확하게 충족하는 Gantt 차트 보기를 만들 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks를 다른 .NET 라이브러리와 함께 사용할 수 있나요?
예, Aspose.Tasks는 다른 .NET 라이브러리와 원활하게 통합되어 개발 스택에 유연성을 제공합니다.
### 테스트 목적으로 임시 라이센스를 사용할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/) 평가를 위해.
### 간트 차트 보기에 대한 추가 사용자 정의 옵션이 있습니까?
물론 Aspose.Tasks는 다양한 프로젝트 요구 사항에 맞게 간트 차트 보기에 대한 광범위한 사용자 정의 옵션을 제공합니다.
### 다양한 형식으로 시간 척도를 렌더링할 수 있나요?
물론, 프로젝트 상황에 가장 잘 맞는 다양한 형식과 스타일을 탐색하여 시간 척도를 표현할 수 있습니다.
### Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 네, 방문해 보세요[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.