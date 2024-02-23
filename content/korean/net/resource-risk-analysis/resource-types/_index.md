---
title: Aspose.Tasks의 리소스 유형
linktitle: Aspose.Tasks의 리소스 유형
second_title: Aspose.태스크 .NET API
description: 단계별 튜토리얼을 통해 Aspose.Tasks for .NET에서 작업, 자재, 비용 리소스 등 다양한 유형의 리소스로 작업하는 방법을 알아보세요.
type: docs
weight: 14
url: /ko/net/resource-risk-analysis/resource-types/
---
## 소개
Aspose.Tasks for .NET은 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있는 강력한 라이브러리입니다. 작업, 리소스 또는 일정을 관리하든 Aspose.Tasks는 포괄적인 API 세트를 제공하여 프로세스를 단순화합니다. 이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 프로젝트 내에서 활용할 수 있는 다양한 유형의 리소스를 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. Visual Studio: .NET 개발을 위한 강력한 IDE(통합 개발 환경)인 Visual Studio를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C#에 대한 기본 지식: .NET 개발에 사용되는 프로그래밍 언어인 C#에 익숙해집니다.

## 네임스페이스 가져오기
먼저 .NET용 Aspose.Tasks의 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
    
```

## 1단계: 새 프로젝트 인스턴스 만들기
```csharp
var project = new Project();
```
이 줄은 모든 프로젝트 관련 데이터 및 작업의 컨테이너 역할을 하는 새 Project 개체를 초기화합니다.
## 2단계: 작업 자원 추가
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
여기서는 "Work Resource"라는 새 작업 리소스를 만들고 해당 유형을 ResourceType.Work로 지정합니다.
## 3단계: 재료 자원 추가
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
이 단계에서는 유형이 ResourceType.Material로 설정된 "Material Resource"라는 재료 리소스를 추가합니다. 또한 측정 단위를 나타내기 위해 재료 라벨을 "kg"으로 지정합니다.
## 4단계: 비용 리소스 추가
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
마지막으로 "Cost Resource"라는 비용 리소스를 추가하고 해당 유형을 ResourceType.Cost로 설정합니다. 또한 비용 값을 59.99로 설정하여 이 리소스와 관련된 금전적 가치를 나타냅니다.

## 결론
이 튜토리얼에서는 작업, 재료 및 비용 리소스를 포함하여 Aspose.Tasks for .NET에서 다양한 유형의 리소스로 작업하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 프로젝트 내의 리소스를 프로그래밍 방식으로 효과적으로 관리할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET을 다른 프로젝트 관리 소프트웨어 형식과 함께 사용할 수 있습니까?
A: 예, Aspose.Tasks는 Microsoft Project(MPP), Primavera P6 등을 포함한 다양한 형식을 지원합니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET에 대한 기술 지원은 어떻게 받을 수 있나요?
 A: Aspose.Tasks 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15) 기술 지원을 위해.
### Q: .NET용 Aspose.Tasks의 임시 라이선스를 구입할 수 있나요?
 A: 예, 임시 라이센스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for .NET은 참조용 문서를 제공합니까?
 A: 예, 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).