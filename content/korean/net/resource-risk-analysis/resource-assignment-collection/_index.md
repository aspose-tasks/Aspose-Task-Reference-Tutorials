---
title: Aspose.Tasks의 자원 할당 수집
linktitle: Aspose.Tasks의 자원 할당 수집
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 자원 할당을 관리하는 방법을 알아보세요. 코드 예제가 포함된 단계별 튜토리얼입니다.
type: docs
weight: 12
url: /ko/net/resource-risk-analysis/resource-assignment-collection/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 리소스 할당을 관리하는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. 이 튜토리얼에서는 프로세스를 단계별로 자세히 살펴보고 리소스 할당을 효율적으로 조작하는 방법을 확실하게 이해할 수 있도록 하겠습니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 여러분이 알아야 할 모든 것을 안내합니다.
## 전제조건
코드를 살펴보기 전에 다음이 설정되어 있는지 확인하세요.
1. .NET용 Aspose.Tasks 설치: 개발 환경에 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. C#에 대한 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍 언어에 대한 기본 지식을 가지고 있다고 가정합니다.
3. Microsoft Project 파일: 테스트 목적으로 Microsoft Project 파일을 준비합니다. 샘플 파일이 없으면 샘플 파일을 만들 수 있습니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 가져오겠습니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1단계: 프로젝트 파일 로드
Microsoft Project 파일을 로드하여 시작합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## 2단계: 작업 및 리소스 추가
이제 프로젝트에 작업과 리소스를 추가해 보겠습니다.
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## 3단계: 작업에 자원 할당
다음으로 작업에 리소스를 할당하겠습니다.
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## 4단계: 다양한 할당 유형 작업
단위 또는 비용과 관련된 할당 작업을 수행할 수도 있습니다.
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// 3단계에 표시된 것과 유사하게 단위 및 비용이 포함된 할당의 속성을 설정합니다.
```
## 5단계: 과제 인쇄
프로젝트 할당을 인쇄합니다.
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // 과제 세부정보 인쇄
}
```
## 6단계: UID로 할당 검색
UID별로 할당을 검색할 수 있습니다.
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## 7단계: 읽기 전용 상태 확인
리소스 할당 컬렉션이 읽기 전용인지 확인합니다.
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## 8단계: 컬렉션을 목록으로 변환하고 반복
컬렉션을 목록으로 변환하고 반복합니다.
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## 결론
축하해요! .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 리소스 할당을 관리하는 방법을 배웠습니다. 다음 단계를 따르면 작업과 리소스를 효율적으로 조작하여 프로젝트 관리를 쉽게 할 수 있습니다.
## FAQ
### Q: 다양한 버전의 Microsoft Project 파일과 함께 Aspose.Tasks for .NET을 사용할 수 있나요?
A: 예, Aspose.Tasks for .NET은 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: .NET용 Aspose.Tasks를 구매하기 전에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음 사이트에서 Aspose.Tasks for .NET 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET을 사용하는 동안 문제가 발생하면 어떻게 지원을 받을 수 있나요?
 A: Aspose.Tasks 포럼에서 지원을 요청할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: .NET용 Aspose.Tasks에 임시 라이선스를 사용할 수 있나요?
 A: 예, 평가 목적으로 임시 라이선스를 사용할 수 있습니다. 당신은 하나를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### Q: .NET용 Aspose.Tasks의 정식 라이선스는 어디에서 구매할 수 있나요?
 A: Aspose 온라인 스토어에서 정식 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).