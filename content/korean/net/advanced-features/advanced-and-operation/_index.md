---
title: Aspose.Tasks의 고급 AND 연산
linktitle: Aspose.Tasks의 고급 AND 연산
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 고급 AND 작업을 수행하여 여러 기준에 따라 프로젝트 작업을 효율적으로 필터링하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/advanced-features/advanced-and-operation/
---
## 소개

 이 튜토리얼에서는 작업 및 프로젝트 관리를 위한 강력한 도구인 Aspose.Tasks for .NET의 고급 AND 연산을 자세히 살펴보겠습니다. 다음을 사용하여 여러 조건을 기반으로 프로젝트 작업을 필터링하는 방법을 살펴보겠습니다.`Util.And` 수업.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. C# 프로그래밍 언어에 대한 기본 지식.
2.  .NET용 Aspose.Tasks를 설치했습니다. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
3. Visual Studio와 같은 통합 개발 환경(IDE)입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 C# 프로젝트로 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## 1단계: 프로젝트 초기화 및 작업 수집

새로운 Aspose.Tasks 프로젝트를 초기화하고 그 안의 모든 작업을 수집하는 것부터 시작하세요.

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 2단계: 필터 조건 정의

다음으로 필터 조건을 정의합니다. 이 예에서는 두 가지 조건을 만듭니다. 하나는 요약 작업을 필터링하고 다른 하나는 null이 아닌 작업을 필터링합니다.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 3단계: AND 연산으로 조건 결합

 이제 다음을 사용하여 조건을 결합합니다.`Util.And` 복합 조건을 생성하는 클래스:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 4단계: 조건 적용 및 작업 필터링

수집된 작업에 결합된 조건을 적용하고 그에 따라 필터링합니다.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 5단계: 필터링된 작업 출력

마지막으로 필터링된 작업을 출력합니다.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // 여기서 추가 처리를 할 수 있습니다
}
```

## 결론

 이 튜토리얼에서는 .NET용 Aspose.Tasks에서 고급 AND 연산을 수행하는 방법을 배웠습니다. 다음을 사용하여 조건을 결합하여`Util.And` 수업을 통해 여러 기준에 따라 작업을 효율적으로 필터링할 수 있습니다.

## FAQ

### Q1: .NET용 Aspose.Tasks란 무엇입니까?

A: Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다.

### Q2: Util.And를 사용하여 두 개 이상의 조건을 적용할 수 있나요?

A: 예, Util.And를 사용하면 원하는 수의 조건을 결합하여 복잡한 필터링 기준을 만들 수 있습니다.

### Q3: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있습니까?

 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: .NET용 Aspose.Tasks에 대한 설명서는 어디에서 찾을 수 있습니까?

 A: 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).

### Q5: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).