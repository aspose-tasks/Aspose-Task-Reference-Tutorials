---
title: Aspose.Tasks를 사용하여 MS 프로젝트 그룹 기준 관리
linktitle: Aspose.Tasks에서 그룹 기준 수집 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Group Criterion MS 프로젝트 컬렉션을 관리하는 방법을 알아보세요. 개발자를 위한 단계별 가이드.
weight: 28
url: /ko/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS 프로젝트 그룹 기준 관리

## 소개
Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있는 강력한 API입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 MS 프로젝트 내에서 Group Criterion 컬렉션을 관리하는 방법을 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Tasks: .NET 프로젝트에 Aspose.Tasks 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).

2. Microsoft Project 파일: 작업할 수 있는 Microsoft Project 파일(MPP)을 준비하세요.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 이 단계는 Aspose.Tasks가 제공하는 기능에 액세스하는 데 중요합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 1단계: 프로젝트 파일 로드

 초기화`Project` MPP 파일을 로드하여 개체를 만듭니다. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## 2단계: 액세스 그룹 기준

프로젝트에서 그룹을 검색하고 해당 기준에 액세스합니다.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## 3단계: 그룹 기준 반복

그룹의 각 기준을 반복하고 해당 속성을 표시합니다.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## 4단계: 그룹 기준 지우기

읽기 전용이 아닌 경우 기존 그룹 기준을 지웁니다.

```csharp
group.GroupCriteria.Clear();
```

## 5단계: 새 기준 추가

새 그룹 기준을 생성하여 그룹에 추가합니다.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## 6단계: 기준을 다른 그룹에 복사

한 그룹의 기준을 다른 그룹에 복사합니다.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Group Criterion MS 프로젝트 컬렉션을 관리하는 방법을 배웠습니다. 다음 단계를 수행하면 프로그래밍 방식으로 Microsoft Project 파일 내의 그룹 기준을 효과적으로 조작할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?

A: 예, Aspose.Tasks는 2003, 2007, 2010, 2013 및 2016을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.

### Q2: 단일 그룹에 여러 기준을 적용할 수 있나요?

A: 물론, 각 기준을 반복하고 그에 따라 추가하여 그룹에 여러 기준을 추가할 수 있습니다.

### Q3: Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?

 A: 예, Aspose.Tasks의 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?

 A: 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).

### Q5: 문제가 발생하면 어떻게 지원을 받을 수 있나요?

 A: 질문이 있거나 문제가 있는 경우 Aspose.Tasks 포럼에서 지원을 요청할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
