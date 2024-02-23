---
title: .NET용 Aspose.Tasks에서 작업 사용량 보기 마스터하기
linktitle: Aspose.Tasks에서 작업 사용량 보기 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 살펴보고 작업 사용량 보기를 구성하는 방법을 알아보세요. 기간 설정을 사용자 정의하고 프로젝트 관리 시각적 효과를 향상하세요.
type: docs
weight: 24
url: /ko/net/task-table-management/task-usage-views/
---
## 소개
프로젝트 관리 영역에서 작업 사용량을 시각화하는 것은 효과적인 계획과 실행을 위해 매우 중요합니다. Aspose.Tasks for .NET은 작업 사용 보기 렌더링을 위한 강력한 솔루션을 제공하므로 시간 척도 설정 및 프레젠테이션 형식을 사용자 정의할 수 있습니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 작업 사용량 보기를 구성하는 단계를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks: Aspose.Tasks 라이브러리가 .NET 프로젝트에 통합되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
2. .NET 환경: 컴퓨터에 작동하는 .NET 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다. 코드에 다음 줄을 추가합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1단계: 문서 디렉터리 경로 설정
 Aspose.Tasks 기능을 사용하기 전에 문서 디렉터리의 경로를 설정하세요. 바꾸다`"Your Document Directory"` 실제 경로와 함께.
```csharp
String DataDir = "Your Document Directory";
```
## 2단계: 프로젝트 로드
 Aspose.Tasks 초기화`Project` 프로젝트 파일(예: TaskUsageView.mpp)을 로드하여 개체를 생성합니다.
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## 3단계: SaveOptions 정의
 만들기`SaveOptions`렌더링 옵션을 지정하는 개체입니다. 기간을 '일'로 설정하고 표시 형식을 'TaskUsage'로 설정합니다.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## 4단계: 일 단위로 저장
'일'의 사전 정의된 기간 설정으로 프로젝트를 저장합니다.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 5단계: ThirdsOfMonths 시간 척도로 저장
기간 설정을 'ThirdsOfMonths'로 변경하고 프로젝트를 저장합니다.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 6단계: 월 단위로 저장
기간을 '월'로 설정하고 업데이트된 설정으로 프로젝트를 저장합니다.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 결론
.NET용 Aspose.Tasks를 사용하여 작업 사용량 보기를 구성하는 것은 간단한 프로세스입니다. 기간 설정을 사용자 정의하면 특정 요구 사항에 따라 프로젝트 작업의 시각화를 조정할 수 있습니다.
 더 많은 특징과 기능을 자유롭게 탐색해 보세요.[선적 서류 비치](https://reference.aspose.com/tasks/net/).
## 자주 묻는 질문
### 미리 정의된 설정 이상으로 기간을 맞춤 설정할 수 있나요?
예, 간격과 단위를 지정하여 사용자 정의 기간을 설정할 수 있습니다.
### 다른 프레젠테이션 형식을 사용할 수 있나요?
Aspose.Tasks는 GanttChart, ResourceUsage 등을 포함한 다양한 프레젠테이션 형식을 지원합니다.
### Aspose.Tasks는 다른 프로젝트 파일 형식과 호환됩니까?
예, Aspose.Tasks는 MPP, XML 및 CSV와 같은 널리 사용되는 프로젝트 파일 형식을 지원합니다.
### 특정 작업에 다른 기간 설정을 적용할 수 있나요?
물론, 프로젝트 내의 개별 작업에 대한 기간 설정을 사용자 정의할 수 있습니다.
### Aspose.Tasks에 대한 지원을 받거나 도움을 구하려면 어떻게 해야 합니까?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역 사회의 지원과 지도를 위해.