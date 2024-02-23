---
title: .NET용 Aspose.Tasks를 사용한 마스터 시간대별 데이터 처리
linktitle: Aspose.Tasks에서 시간대별 데이터 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 탐색하여 시간대별 데이터를 손쉽게 처리하고, 프로젝트 계획을 개선하고, 리소스 관리를 최적화하세요. #Aspose #작업 #MS 프로젝트
type: docs
weight: 14
url: /ko/net/text-view-configuration/timephased-data/
---
## 소개
프로젝트 관리 세계에서 시간대별 데이터를 효과적으로 처리하는 것은 리소스 할당, 비용 추정 및 전체 프로젝트 계획에 매우 중요합니다. Aspose.Tasks for .NET은 맞춤형 시간대별 데이터를 원활하게 사용할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 시간대별 데이터를 처리하는 과정을 안내하여 프로젝트의 리소스 관리를 최적화할 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 프로젝트 관리 개념에 대한 기본적인 이해.
-  .NET용 Aspose.Tasks를 설치했습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- 제공된 예제를 구현하기 위한 Visual Studio와 같은 코드 편집기.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 기능을 활용하려면 필요한 네임스페이스를 가져와야 합니다. 코드 파일 시작 부분에 다음 줄을 추가합니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```
이제 Aspose.Tasks를 사용하여 시간대별 데이터를 처리하는 방법을 안내하기 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
여기서는 새 프로젝트를 초기화하고 계산 모드를 설정합니다.
## 2단계: 자원 및 작업 정의
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
작업 및 비용 자원과 작업을 생성하여 프로젝트 구조를 시뮬레이션합니다.
## 3단계: 작업에 자원 할당
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
작업에 작업 및 비용 자원을 할당합니다.
## 4단계: 사용자 정의 시간대별 데이터 추가
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// CostAssignment와 유사한 단계
costAssignment.TimephasedData.Clear();
```
작업 및 비용 할당 모두에 대해 사용자 정의 시간대별 데이터를 추가합니다.
## 5단계: 시간대별 데이터 표시
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // 각 시간대별 데이터 항목에 대한 관련 정보 표시
    }
}
```
마지막으로 각 과제에 대한 시간대별 데이터를 표시합니다.
#
## 결론
Aspose.Tasks에서 시간대별 데이터를 효과적으로 처리하면 세부 프로젝트 계획 및 리소스 관리에 대한 새로운 가능성이 열립니다. 이 단계별 가이드를 따라 프로젝트의 특정 요구 사항을 충족하기 위해 시간대별 데이터를 조작하는 방법을 배웠습니다.
## 자주 묻는 질문
### 다른 프로젝트 관리 도구와 함께 Aspose.Tasks for .NET을 사용할 수 있나요?
Aspose.Tasks는 주로 .NET 개발을 위해 설계되었습니다. 그러나 해당 기능은 다양한 프로젝트 관리 도구를 보완할 수 있습니다.
### .NET용 Aspose.Tasks에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 사용해 볼 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)지역 사회 지원을 위해.
### 임시 라이센스란 무엇이며 어떻게 얻을 수 있나요?
 임시 라이선스에 대해 알아보기[여기](https://purchase.aspose.com/temporary-license/).
### .NET용 Aspose.Tasks에 대한 설명서는 어디에서 찾을 수 있나요?
 종합적인 내용을 참고하세요[선적 서류 비치](https://reference.aspose.com/tasks/net/) 자세한 정보를 보려면.