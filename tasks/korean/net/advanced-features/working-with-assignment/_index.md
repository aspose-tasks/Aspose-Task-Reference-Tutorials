---
title: Aspose.Tasks에서 할당 작업
linktitle: Aspose.Tasks에서 할당 작업
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks를 사용하여 .NET에서 프로젝트 할당을 관리하는 방법을 알아보세요. 리소스 예약을 위한 다양한 윤곽을 살펴보세요.
weight: 13
url: /ko/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 할당 작업

## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 할당 작업을 수행하는 방법을 살펴보겠습니다. 할당은 작업에 리소스를 할당하고 진행 상황을 예약하고 추적하는 데 도움이 되므로 프로젝트 관리에서 매우 중요합니다. Aspose.Tasks를 사용하여 다양한 윤곽을 갖춘 자원 할당 시간대별 데이터를 생성하는 데 중점을 둘 것입니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Tasks 설치: 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
2. C# 및 .NET Framework에 대한 기본 이해: 계속 진행하려면 C# 프로그래밍 언어 및 .NET Framework 개념에 대한 지식이 필요합니다.

## 네임스페이스 가져오기

필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## 1단계: 프로젝트 및 작업 생성

새 프로젝트를 만들고 여기에 작업을 추가하는 것부터 시작해 보겠습니다. 작업의 시작 날짜, 기간 및 완료 날짜를 설정합니다.

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 2단계: 자원 추가 및 작업에 할당

다음으로 프로젝트에 자원을 추가하고 이전에 생성된 작업에 할당합니다.

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 3단계: 다양한 등고선을 사용하여 시간대별 데이터 생성

이제 자원 할당에 대해 다양한 윤곽을 사용하여 시간대별 데이터를 생성해 보겠습니다.

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## 4단계: 윤곽 변경 및 데이터 생성

윤곽선 유형을 변경하고 이에 따라 시간대별 데이터를 생성할 수 있습니다. 여기 몇 가지 예가 있어요.

```csharp
// 윤곽 변경
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// 시간대별 데이터 생성 및 인쇄
// 다른 윤곽선 유형에 대해 이 단계를 반복합니다.
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 할당 작업을 수행하는 방법을 배웠습니다. 다양한 등고선을 사용하여 자원 할당 시간대별 데이터 생성을 탐색했습니다. 이 지식은 프로젝트 관리 시나리오에서 매우 유용할 수 있습니다.

## FAQ

### Q1: 내 .NET 애플리케이션에서 작업을 예약하기 위해 Aspose.Tasks를 사용할 수 있습니까?

A1: 예, Aspose.Tasks는 .NET 애플리케이션의 작업 일정 관리 및 관리를 위한 포괄적인 API를 제공합니다.

### Q2: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?

 A2: 예, 다음에서 무료 평가판을 이용하실 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: Aspose.Tasks의 작업이나 리소스 수에 제한이 있나요?

A3: Aspose.Tasks는 프로젝트에서 관리할 수 있는 작업이나 리소스의 수에 제한을 두지 않습니다.

### Q4: Aspose.Tasks에서 리소스 할당에 대한 윤곽을 사용자 정의할 수 있나요?

A4: 예, 이 튜토리얼에서 설명한 것처럼 프로젝트 요구 사항에 따라 거북이, 종, 피크 등과 같은 다양한 윤곽을 설정할 수 있습니다.

### Q5: Aspose.Tasks 관련 쿼리에 대한 지원은 어디서 찾을 수 있나요?

A5: 다음에서 지원을 찾을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 전문가와 커뮤니티 구성원이 적극적으로 토론에 참여하는 곳입니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
