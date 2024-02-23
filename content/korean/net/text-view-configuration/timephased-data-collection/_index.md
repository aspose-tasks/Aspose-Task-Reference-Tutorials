---
title: Aspose.Tasks에서 시간대별 데이터 수집 마스터하기
linktitle: Aspose.Tasks에서 시간대별 데이터 수집
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 시간대별 데이터 수집을 살펴보세요. 단계별 가이드, FAQ 등. 오늘 귀하의 프로젝트 관리 역량을 강화하십시오!
type: docs
weight: 15
url: /ko/net/text-view-configuration/timephased-data-collection/
---
## 소개
Aspose.Tasks를 사용하여 .NET 애플리케이션에서 시간대별 데이터의 강력한 기능을 활용하려고 하시나요? 더 이상 보지 마세요! 이 포괄적인 가이드는 Aspose.Tasks for .NET을 사용하여 시간대별 데이터를 수집하는 과정을 안내하여 이 강력한 라이브러리를 최대한 활용할 수 있도록 보장합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 라이브러리를 다운로드하고 설치하세요.[Aspose.Tasks .NET 문서](https://reference.aspose.com/tasks/net/).
2. .NET 개발 환경: 작동하는 .NET 개발 환경이 설정되어 있는지 확인하십시오.
3. 문서 디렉터리: 코드 조각의 자리 표시자 "문서 디렉터리"를 문서 디렉터리 경로로 바꿉니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks 기능을 활용하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 프로젝트 및 리소스 생성
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. 프로젝트에 작업 추가
```csharp
var task = project.RootTask.Children.Add("Task 1");
// 작업 속성 설정...
var task2 = project.RootTask.Children.Add("Task 2");
// task2 속성 설정...
```
## 3. 작업에 자원 할당
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// 할당 속성 설정...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// 할당2 속성 설정...
```
## 4. 시간대별 데이터 작업
```csharp
// 윤곽이 잡힌 작업 윤곽 설정
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// 시간대별 데이터 수집이 읽기 전용인지 확인하세요.
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// 생성된 시간대별 데이터 지우기
assignment.TimephasedData.Clear();
// 시간대별 데이터 생성 및 추가
var td = new TimephasedData
{
    // 시간대별 데이터 속성 설정...
};
assignment.TimephasedData.Add(td);
// 시간대별 데이터 목록 추가
var list = new List<TimephasedData>();
// 목록에 더 많은 시간대별 데이터 항목을 추가합니다...
assignment.TimephasedData.AddRange(list);
// 유형 및 날짜 범위별로 시간대별 데이터 필터링
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// 필터링된 시간대별 데이터 인쇄...
```
## 5. 시간대별 데이터 조작
```csharp
//잘못된 시간대별 데이터 항목을 추가한 후 삭제하세요.
var td4 = new TimephasedData
{
    // 잘못된 시간대별 데이터 속성 설정...
};
assignment.TimephasedData.Add(td4);
// 잘못된 시간대별 데이터 항목 삭제
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// 모든 시간대별 항목을 반복합니다.
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // 시간대별 항목 세부정보 인쇄...
}
```
## 6. 시간대별 데이터를 다른 과제에 복사
```csharp
// 시간대별 데이터를 다른 과제에 복사
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// 컬렉션을 일반 목록으로 변환
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// 시간대별 데이터 항목을 하나씩 제거
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## 결론
결론적으로 이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 시간대별 데이터를 수집하는 방법에 대한 자세한 연습을 제공했습니다. 다음 단계를 수행하면 이 기능을 프로젝트에 원활하게 통합하여 효과적인 시간 추적 및 리소스 관리가 가능해집니다.
## 자주 묻는 질문
### 다른 프로젝트 관리 도구와 함께 Aspose.Tasks for .NET을 사용할 수 있나요?
예, Aspose.Tasks for .NET은 널리 사용되는 프로젝트 관리 도구와 함께 작동하도록 설계되었으며 다양한 파일 형식을 지원합니다.
### Aspose.Tasks로 관리할 수 있는 리소스 및 작업 수에 제한이 있나요?
Aspose.Tasks는 다양한 규모의 프로젝트를 처리하며 리소스 및 작업 수에 엄격한 제한이 없습니다.
### Aspose.Tasks for .NET과 관련된 문제나 쿼리에 대한 지원을 어떻게 받을 수 있나요?
 지원을 받으려면 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역사회와 연결하고 도움을 받으려면
### 구매하기 전에 .NET용 Aspose.Tasks를 사용해 볼 수 있나요?
 예, 다음에 액세스하여 .NET용 Aspose.Tasks의 기능을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/).
### .NET용 Aspose.Tasks 라이선스는 어디서 구매할 수 있나요?
 .NET용 Aspose.Tasks 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).