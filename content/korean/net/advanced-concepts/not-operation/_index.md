---
title: Aspose.Tasks에서 NOT 연산으로 작업하기
linktitle: Aspose.Tasks에서 NOT 연산으로 작업하기
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 NOT 작업을 사용하여 작업을 효과적으로 필터링하는 방법을 알아보세요. 지금 프로젝트 관리 역량을 강화하세요.
type: docs
weight: 20
url: /ko/net/advanced-concepts/not-operation/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 NOT 연산을 활용하는 방법을 살펴보겠습니다. NOT 연산을 사용하면 필터 조건을 반전시켜 지정된 기준을 충족하지 않는 요소를 선택할 수 있습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. Visual Studio: 코드 예제를 따라하려면 Visual Studio가 제대로 설치되어 있어야 합니다.
2.  .NET용 Aspose.Tasks: 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
3. C#의 기본 이해: C# 프로그래밍 언어에 익숙하면 코드 예제를 이해하는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 코드에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1단계: 프로젝트 및 작업 설정

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 다음을 사용하여 "Project2.mpp"라는 프로젝트 파일을 로드하는 것으로 시작합니다.`Project` Aspose.Tasks에서 제공하는 클래스입니다. 프로젝트 파일이 지정된 디렉터리에 있는지 확인하세요.

## 2단계: 프로젝트 작업 수집

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 여기서는`ChildTasksCollector` 프로젝트 내의 모든 작업을 수집하는 개체입니다. 그런 다음 우리는`TaskUtils.Apply`프로젝트의 작업 계층 구조를 탐색하고 모든 하위 작업을 수집하는 방법입니다.

## 3단계: 필터 조건 정의

```csharp
var filter = new NullCondition();
```

 이름이 지정된 사용자 정의 클래스를 사용하여 필터 조건을 정의합니다.`NullCondition`, 이 조건은 null 값이 있는 작업을 선택합니다.

## 4단계: NOT 연산 적용

```csharp
var condition = new Not<Task>(filter);
```

 다음을 사용하여 필터 조건에 NOT 연산을 적용합니다.`Not<T>` Aspose.Tasks에서 제공하는 클래스입니다. 그러면 필터 조건이 반전되어 null 값이 없는 작업이 선택됩니다.

## 5단계: 작업 필터링

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 사용자 정의를 사용하여 적용된 조건에 따라 수집된 작업을 필터링합니다.`Filter` 방법. 이 메서드는 열거 가능한 작업 컬렉션과 필터 조건을 입력 매개 변수로 사용하고 조건을 충족하는 작업 목록을 반환합니다.

## 6단계: 필터링된 작업 처리

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // 다른 속성으로 작업...
}
```

마지막으로 필터링된 작업을 반복하고 원하는 작업을 수행합니다. 이 예에서는 단순히 작업 이름을 콘솔에 인쇄합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 NOT 작업을 수행하는 방법을 배웠습니다. 필터 조건을 반전함으로써 지정된 기준을 충족하지 않는 요소를 선택적으로 선택할 수 있으므로 프로젝트 내 작업 조작의 유연성이 향상됩니다.

## FAQ

### Q1: Aspose.Tasks를 다른 .NET 프레임워크와 함께 사용할 수 있나요?

A: 예, Aspose.Tasks는 .NET Core, .NET Standard 및 .NET Framework를 포함한 다양한 .NET 프레임워크를 지원합니다.

### Q2: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?

 A: 예, 다음 사이트에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/).

### Q3: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?

 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원 문의 또는 기술 지원이 필요합니다.

### Q4: Aspose.Tasks에 대한 임시 라이선스를 구입할 수 있나요?

 A: 네, 임시 라이센스를 구입하실 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Tasks에 대한 종합 문서는 어디에서 찾을 수 있나요?

 A: 다음 사이트에서 전체 설명서에 액세스할 수 있습니다.[Aspose.Tasks 문서 페이지](https://reference.aspose.com/tasks/net/).