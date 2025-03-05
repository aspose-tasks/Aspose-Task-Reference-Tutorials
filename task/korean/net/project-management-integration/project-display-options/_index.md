---
title: Aspose.Tasks에서 MS 프로젝트 표시 옵션 구성
linktitle: Aspose.Tasks에서 프로젝트 표시 옵션 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 MS 프로젝트 표시 옵션을 구성하는 방법을 알아보세요. 프로젝트의 모양을 손쉽게 사용자 정의하세요.
type: docs
weight: 17
url: /ko/net/project-management-integration/project-display-options/
---
## 소개
Microsoft Project는 프로젝트의 모양을 사용자 정의할 수 있는 다양한 디스플레이 옵션을 제공합니다. Aspose.Tasks for .NET은 이러한 옵션을 프로그래밍 방식으로 조작할 수 있는 강력한 프레임워크를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 MS 프로젝트 표시 옵션을 구성하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1.  .NET용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. Microsoft 프로젝트 파일: 표시 옵션을 적용할 수 있는 유효한 MS 프로젝트 파일(.mpp)이 준비되어 있습니다.
3. C# 기본 지식: C# 프로그래밍 언어에 대한 지식이 필요합니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 C# 코드로 가져와야 합니다.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 파일 로드
 다음을 사용하여 MS 프로젝트 파일을 로드합니다.`Project` Aspose.Tasks에서 제공하는 클래스:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 2단계: 표시 옵션 구성
이제 MS Project에서 사용할 수 있는 다양한 표시 옵션을 구성해 보겠습니다.
### 작업 일정 경고 비활성화
수동 예약 작업과의 예약 충돌에 대한 경고를 비활성화하려면(Project 2010 이상에서 사용 가능):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### 라벨 앞에 공백 추가
숫자 값과 시간 약어 앞에 공백을 추가하도록 설정합니다.
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### 시간 단위에 대한 라벨 표시 구성
다양한 시간 단위가 표시되는 방식을 사용자 정의합니다.
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### 프로젝트 요약 작업 표시
전체 프로젝트에 대한 요약 정보를 단일 행에 표시합니다.
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### 작업 일정 제안 활성화
수동으로 예약된 작업과의 예약 충돌에 대한 제안 표시 허용:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### 하이퍼링크에 밑줄을 긋습니다
프로젝트 내의 하이퍼링크에 밑줄을 표시하도록 설정합니다.
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## 3단계: 프로젝트 저장
마지막으로 적용된 표시 옵션을 사용하여 프로젝트를 저장합니다.
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 표시 옵션을 구성하는 방법을 배웠습니다. 이러한 기능을 사용하면 프로젝트 파일의 모양을 프로그래밍 방식으로 효율적으로 사용자 정의할 수 있습니다.
## FAQ
### Q: 이러한 표시 옵션을 특정 작업에만 적용할 수 있습니까?
A: 예, Aspose.Tasks API를 사용하여 개별 작업에 표시 옵션을 선택적으로 적용할 수 있습니다.
### Q: 이러한 표시 옵션이 기본 프로젝트 데이터에 영향을 줍니까?
A: 아니요. 이러한 옵션은 프로젝트의 시각적 표현만 수정하고 기본 데이터는 변경하지 않습니다.
### Q: 이러한 표시 옵션은 모든 버전의 Microsoft Project와 호환됩니까?
A: 아니요. 일부 옵션은 특정 버전의 MS Project에만 국한될 수 있습니다. 호환성 세부정보는 설명서를 참조하세요.
### Q: 디스플레이 옵션을 기본 설정으로 되돌릴 수 있나요?
A: 예, Aspose.Tasks API를 사용하여 표시 옵션을 기본값으로 재설정할 수 있습니다.
### Q: 프로그래밍 방식으로 디스플레이 옵션을 사용자 정의하는 데 제한이 있습니까?
A: Aspose.Tasks는 광범위한 사용자 정의 기능을 제공하지만 MS 프로젝트 파일 형식의 제한으로 인해 특정 표시 옵션에 프로그래밍 방식으로 액세스하지 못할 수 있습니다.