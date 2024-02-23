---
title: Aspose.Tasks로 MS 프로젝트 필터 기준 익히기
linktitle: Aspose.Tasks의 필터 기준
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 필터 기준을 구현하는 방법을 알아보세요. 타겟 데이터 분석을 통해 프로젝트 관리 효율성을 높입니다.
type: docs
weight: 18
url: /ko/net/tasks-project-management/filter-criteria/
---
## 소개
프로젝트 관리 영역에서 Microsoft Project는 프로젝트 기획자와 관리자를 지원하는 다양한 기능을 제공하는 강력한 도구입니다. 많은 기능 중에는 프로젝트 데이터를 필터링하는 기능이 있어 사용자가 프로젝트 작업의 특정 측면에 집중할 수 있습니다. 그러나 이러한 필터링 기능을 익히는 것은 올바른 지침 없이는 어려운 작업이 될 수 있습니다. 이 튜토리얼은 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 기준 필터를 구현하는 단계별 가이드를 제공하여 프로세스를 이해하는 것을 목표로 합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. C#에 대한 기본 이해: 이 자습서에서 다루는 개념을 이해하려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.
2.  .NET용 Aspose.Tasks 설치: 개발 환경에 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
3. Microsoft Project 파일: 필터 기준을 구현하는 데 사용할 Microsoft Project 파일(예: Project2003.mpp)을 준비합니다.

## 네임스페이스 가져오기
먼저, Aspose.Tasks for .NET을 사용하려면 필요한 네임스페이스를 가져와야 합니다. 다음과 같이하세요:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## 1단계: 프로젝트 파일 로드
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 설명: 이 코드 줄은`Project` 클래스를 생성하고 해당 경로로 지정된 Microsoft Project 파일을 로드합니다.
## 2단계: 작업 필터 검색
```csharp
var filter = project.TaskFilters.ToList()[1];
```
설명: 여기서는 프로젝트에서 작업 필터를 검색합니다. 인덱스 조정(`[1]`) 요구 사항에 따라 원하는 필터를 선택합니다.
## 3단계: 기준 행 표시
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
설명: 이 섹션은 필터의 각 기준 행을 반복하고 해당 필드, 작업, 테스트 및 값(있는 경우)을 표시합니다.
## 4단계: 인쇄 필터 기준
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
설명: 필터 기준의 작업을 인쇄합니다.
## 5단계: 기준 세부정보 표시
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
설명: 이 부분은 각 기준 행에 대한 자세한 정보를 검색하고 표시하여 필터 구성에 대한 통찰력을 제공합니다.

## 결론
.NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 필터 기준을 마스터하는 것은 프로젝트 관리 효율성을 크게 향상시킬 수 있는 귀중한 기술입니다. 이 튜토리얼을 따라가면서 프로그래밍 방식으로 필터 기준을 조작하여 특정 요구 사항에 맞게 프로젝트 보기를 맞춤화하는 방법을 배웠습니다.
## FAQ
### Q: MS Project에서 여러 필터를 동시에 적용할 수 있나요?
A: 예, 여러 필터를 결합하여 프로젝트 데이터를 더욱 구체화할 수 있습니다.
### Q: Aspose.Tasks는 이전 버전의 Microsoft Project 파일을 지원합니까?
A: 예, Aspose.Tasks는 이전 버전과의 호환성을 제공하므로 다양한 버전의 Microsoft Project 파일로 작업할 수 있습니다.
### Q: Aspose.Tasks는 다른 .NET 프레임워크와 호환됩니까?
A: Aspose.Tasks는 .NET Framework, .NET Core 및 .NET Standard를 지원하여 다양한 개발 환경에서 유연성을 보장합니다.
### Q: 동적 조건에 따라 필터 기준을 사용자 정의할 수 있습니까?
A: 물론, 동적 매개변수를 기반으로 필터 기준을 프로그래밍 방식으로 조정하여 적응형 프로젝트 데이터 분석을 활성화할 수 있습니다.
### Q: Aspose.Tasks에 문제가 발생하면 어디서 도움을 받을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티에서 지원을 구하거나 Aspose.Tasks 지원에 직접 연락하여 맞춤형 지원을 받으세요.