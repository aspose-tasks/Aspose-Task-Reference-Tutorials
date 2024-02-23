---
title: .NET용 Aspose.Tasks에서 작업 기준 마스터하기
linktitle: Aspose.Tasks에서 작업 기준 처리
second_title: Aspose.태스크 .NET API
description: 이 포괄적인 튜토리얼을 통해 Aspose.Tasks for .NET에서 작업 기준을 처리하는 방법을 알아보세요. 오늘 귀하의 프로젝트 관리 기술을 향상시키십시오!
type: docs
weight: 16
url: /ko/net/task-table-management/task-baselines/
---
## 소개
역동적인 프로젝트 관리 세계에서는 체계적으로 정보를 체계적으로 유지하는 것이 중요합니다. Aspose.Tasks for .NET은 작업 기준을 처리하기 위한 강력한 솔루션을 제공하여 귀중한 기준 정보에 효율적으로 액세스할 수 있도록 해줍니다. 이 단계별 가이드는 각 개념을 명확하게 이해할 수 있도록 프로세스를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  환경 설정: 개발 환경에 Aspose.Tasks for .NET이 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[Aspose.Tasks 문서](https://reference.aspose.com/tasks/net/).
- C#의 기본 지식: 이 튜토리얼에서는 기초적인 이해가 필요하다고 가정하므로 C# 프로그래밍 언어의 기본 사항을 숙지하세요.
- 통합 개발 환경(IDE): Visual Studio와 같은 선호하는 IDE를 사용하여 원활하게 진행하세요.
## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 프로젝트로 가져옵니다. 이렇게 하면 Aspose.Tasks 기능에 액세스할 수 있습니다.
```csharp
    using Aspose.Tasks;
    using System;
```
이제 Aspose.Tasks에서 작업 기준을 처리하는 과정을 안내하기 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 생성
```csharp
var project = new Project();
```
 다음을 사용하여 새 프로젝트를 초기화하는 것으로 시작하세요.`Project` 수업.
## 2단계: 작업 생성 및 기준 설정
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
 프로젝트에 작업을 추가하고 다음을 사용하여 기준선을 설정합니다.`SetBaseline` 방법.
## 3단계: 작업 기준 정보 표시
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
시작 시간, 기간, 완료 시간 등 작업 기준에 대한 주요 정보를 검색하고 표시합니다.
## 4단계: 추가 기준 세부정보
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
기준선이 임시 기준선인지 여부 및 이와 관련된 고정 비용을 포함한 추가 세부정보를 살펴보세요.
## 5단계: 시간대별 데이터 인쇄
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
작업 기준과 관련된 시간대별 데이터를 이해하여 다양한 프로젝트 타임라인에 대한 통찰력을 제공합니다.
## 결론
축하해요! .NET용 Aspose.Tasks에서 작업 기준선을 처리하는 방법을 성공적으로 배웠습니다. 이러한 지식은 프로젝트 관리 능력을 향상시켜 정확한 추적 및 계획을 보장합니다.
## 자주 묻는 질문
### Q: Aspose.Tasks를 다른 .NET 프레임워크와 함께 사용할 수 있습니까?
A: Aspose.Tasks는 여러 .NET 프레임워크와 호환되므로 개발 환경에 유연성을 제공합니다.
### Q: Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
A: 예, 다음에서 지원을 받고 커뮤니티에 참여할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 답: 방문하다[여기](https://purchase.aspose.com/temporary-license/) Aspose.Tasks에 대한 임시 라이센스를 얻으려면.
### Q: 작업 기준을 넘어서는 자습서가 있습니까?
 A:탐색해 보세요[선적 서류 비치](https://reference.aspose.com/tasks/net/) Aspose.Tasks 기능에 대한 다양한 튜토리얼을 확인하세요.
### Q: .NET용 Aspose.Tasks는 어디서 구매할 수 있나요?
 A: Aspose.Tasks를 편리하게 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).