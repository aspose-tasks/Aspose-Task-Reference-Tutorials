---
title: Aspose.Tasks에서 분할 부품의 MS 프로젝트 수집
linktitle: Aspose.Tasks의 분할 부품 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 분할된 부분을 수집하는 방법을 알아보세요. 이 포괄적인 튜토리얼은 프로세스를 단계별로 안내합니다.
weight: 19
url: /ko/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 분할 부품의 MS 프로젝트 수집

## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 MS 프로젝트에서 분할된 부분을 수집하는 방법을 살펴보겠습니다. 작업을 여러 부분으로 나누는 것은 프로젝트 관리의 중요한 측면이 될 수 있으며 Aspose.Tasks는 이를 효율적으로 처리할 수 있는 편리한 방법을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET용 Aspose.Tasks 설치: .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. C#에 대한 기본 지식: C#으로 코드 조각을 작성할 예정이므로 C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
C# 프로젝트에 필요한 네임스페이스를 포함합니다.
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## 1단계: 프로젝트 설정
먼저, 선호하는 IDE에서 새 프로젝트를 생성하고 .NET용 Aspose.Tasks가 올바르게 참조되는지 확인하세요.
## 2단계: 프로젝트 개체 초기화
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
MS 프로젝트 파일의 경로를 사용하여 새 프로젝트 개체를 초기화합니다.
## 3단계: 작업 검색 및 분할 부분 반복
```csharp
var task = project.RootTask.Children.GetById(1);
// 분할된 부분에 대한 반복
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
프로젝트에서 작업을 검색하고 분할된 부분을 반복하여 시작 날짜와 완료 날짜를 인쇄합니다.
## 4단계: 인덱스별로 분할된 부분 가져오기
```csharp
// 인덱스로 부품 가져오기
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
특정 분할 부분을 인덱스별로 검색하고 시작 날짜를 인쇄합니다.

## 결론
MS 프로젝트 파일에서 분할된 부분을 관리하면 프로젝트 관리 효율성이 크게 향상됩니다. Aspose.Tasks for .NET은 분할 작업을 원활하게 처리할 수 있는 직관적인 API를 제공하여 이 프로세스를 단순화합니다.
## FAQ
### Q: 런타임 중에 작업을 동적으로 분할할 수 있습니까?
A: 예, .NET용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 작업을 분할할 수 있습니다.
### Q: Aspose.Tasks는 모든 버전의 MS 프로젝트 파일을 지원합니까?
A: Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.
### Q: 테스트 목적으로 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음 사이트에서 무료 평가판을 구할 수 있습니다.[여기](https://releases.aspose.com/) 평가를 위해.
### Q: 내 프로젝트에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 임시 라이센스는 다음에서 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 단기 사용을 위해.
### Q: Aspose.Tasks에 관해 도움이나 지원을 어디서 구할 수 있나요?
 A: Aspose.Tasks 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15)커뮤니티 또는 Aspose 지원팀의 도움을 구하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
