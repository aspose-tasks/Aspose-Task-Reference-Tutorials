---
title: Aspose.Tasks에서 프로젝트 타임라인 뷰 마스터하기
linktitle: Aspose.Tasks에서 타임라인 보기 사용자 정의
second_title: Aspose.태스크 .NET API
description: 타임라인 보기 사용자 정의에 대한 .NET용 Aspose.Tasks를 마스터하세요. 프로젝트 요구 사항에 맞춰 시각적으로 매력적인 타임라인을 통해 프로젝트 관리를 강화하세요.
type: docs
weight: 13
url: /ko/net/text-view-configuration/timeline-views/
---
## 소개
효과적인 프로젝트 관리를 위해서는 시각적으로 매력적이고 유익한 타임라인 보기를 만드는 것이 중요합니다. Aspose.Tasks for .NET은 타임라인 보기를 사용자 정의하기 위한 강력한 솔루션을 제공하여 프로젝트의 특정 요구 사항에 따라 작업 표시를 맞춤화할 수 있습니다. 이 단계별 가이드에서는 Aspose.Tasks를 사용하여 타임라인 뷰를 쉽게 만들고 사용자 지정하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- C# 및 .NET 프로그래밍에 대한 기본 지식.
-  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 그렇지 않은 경우 다운로드하십시오.[여기](https://releases.aspose.com/tasks/net/).
- Visual Studio와 같은 IDE(통합 개발 환경).
## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져왔는지 확인하세요.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 및 타임라인 보기 초기화
새 프로젝트와 타임라인 보기를 초기화하여 시작하세요.
```csharp
var project = new Project();
var view = new TimelineView();
```
## 2단계: 타임라인 보기 속성 설정
다양한 속성을 설정하여 타임라인 보기를 사용자 정의합니다.
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## 3단계: 타임라인 보기 세부정보 표시
타임라인 보기에 대한 정보를 검색합니다.
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## 4단계: 프로젝트에 뷰 추가
프로젝트에 사용자 정의된 타임라인 보기를 추가합니다.
```csharp
project.Views.Add(view);
```
## 5단계: 프로젝트에 테스트 데이터 추가
샘플 작업으로 프로젝트를 채웁니다.
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## 6단계: 프로젝트를 PDF로 저장
사용자 정의된 타임라인 보기가 포함된 프로젝트를 PDF 파일로 저장합니다.
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## 결론
축하해요! .NET용 Aspose.Tasks를 사용하여 타임라인 보기를 성공적으로 사용자 정의했습니다. 이 강력한 라이브러리는 시각적으로 매력적인 프로젝트 일정을 만드는 프로세스를 단순화하고 프로젝트 관리 기능을 향상시킵니다.
## 자주 묻는 질문
### Aspose.Tasks는 다른 .NET 프레임워크와 호환됩니까?
예, Aspose.Tasks는 다양한 .NET 프레임워크를 지원하여 개발 환경과의 호환성을 보장합니다.
### 타임라인 보기에서 개별 작업의 모양을 사용자 정의할 수 있나요?
전적으로! Aspose.Tasks는 타임라인 보기에서 각 작업의 모양을 사용자 정의할 수 있는 유연성을 제공합니다.
### Aspose.Tasks에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.Tasks 문서](https://reference.aspose.com/tasks/net/) 포괄적인 가이드와[지원 포럼](https://forum.aspose.com/c/tasks/15) 도움을 위해.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, 무료 평가판을 사용해 볼 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Tasks에 대한 임시 라이선스는 어떻게 얻나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).