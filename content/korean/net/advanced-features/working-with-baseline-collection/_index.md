---
title: Aspose.Tasks에서 기준 컬렉션 작업
linktitle: Aspose.Tasks에서 기준 컬렉션 작업
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET에서 기준선을 효율적으로 관리하는 방법을 알아보세요. 단계별 안내를 보려면 포괄적인 튜토리얼을 따르세요.
type: docs
weight: 20
url: /ko/net/advanced-features/working-with-baseline-collection/
---
## 소개

Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일을 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 많은 기능 중에서 프로젝트 내의 기준선 관리를 위한 강력한 지원을 제공합니다. 기준선은 원래 프로젝트 계획을 현재 상태와 비교할 수 있게 해주고 프로젝트 진행 상황을 더 잘 추적하고 분석할 수 있게 해주기 때문에 프로젝트 관리에 필수적입니다.

## 전제조건

Aspose.Tasks에서 기본 컬렉션 작업을 시작하기 전에 다음 전제 조건이 있는지 확인하세요.

1. Visual Studio: 시스템에 Visual Studio IDE를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙해집니다.
4. Microsoft Project 파일: 테스트 목적으로 Microsoft Project 파일(.mpp)을 준비합니다.

## 네임스페이스 가져오기

Aspose.Tasks에서 기준 컬렉션 작업을 시작하려면 다음 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

이제 각 예를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 파일 로드

먼저 Aspose.Tasks를 사용하여 Microsoft Project 파일을 로드합니다.

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 2단계: 리소스 가져오기

다음으로 프로젝트에서 원하는 리소스를 검색합니다.

```csharp
var resource = project.Resources.GetByUid(1);
```

## 3단계: 기준 정보 표시

이제 리소스와 관련된 기준선에 대한 정보를 표시합니다.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 4단계: 기준선 반복

리소스와 관련된 각 기준선을 반복하고 관련 정보를 인쇄합니다.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 5단계: 기준선 제거

리소스와 관련된 모든 기준을 삭제합니다.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks에서 기준 컬렉션을 사용하여 작업하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 .NET 애플리케이션 내에서 기준선을 쉽게 관리할 수 있어 효과적인 프로젝트 추적 및 분석이 가능합니다.

## FAQ

### Q1: Aspose.Tasks가 대용량 프로젝트 파일을 처리할 수 있나요?

A1: 예, Aspose.Tasks는 대규모 프로젝트 파일을 효율적으로 처리하도록 최적화되어 원활한 성능을 보장합니다.

### Q2: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?

A2: Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.

### Q3: Aspose.Tasks에서 기준선을 사용자 정의할 수 있나요?

A3: 예, Aspose.Tasks for .NET을 사용하여 프로젝트 요구 사항에 따라 기준선을 사용자 지정할 수 있습니다.

### Q4: Aspose.Tasks는 클라우드 플랫폼을 지원합니까?

A4: 예, Aspose.Tasks는 널리 사용되는 클라우드 플랫폼과의 통합을 지원하여 배포 유연성을 제공합니다.

### Q5: Aspose.Tasks 사용자가 도움을 구하고 지식을 공유할 수 있는 커뮤니티 포럼이 있습니까?

 A5: 네, 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티에 참여하고 전문가의 도움을 받으세요.