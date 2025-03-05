---
title: .NET용 Aspose.Tasks에서 MS 프로젝트 XLSX 옵션 구성
linktitle: Aspose.Tasks에서 XLSX 옵션 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 MS Project XLSX 옵션을 구성하는 방법을 알아보세요. 열, 인코딩 등을 손쉽게 사용자 정의하세요.
type: docs
weight: 11
url: /ko/net/file-format-options/configuring-xlsx-options/
---
## 소개
Microsoft Project(MS Project)는 프로젝트 관리를 위한 강력한 도구이며 .NET용 Aspose.Tasks는 프로그래밍 방식으로 MS Project 파일 작업을 위한 원활한 통합을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS Project XLSX 옵션을 구성하는 과정을 안내합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
 개발 환경에 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[.NET 다운로드 페이지용 Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. C#과 .NET Framework의 기본 이해
이 튜토리얼을 진행하려면 C# 프로그래밍 언어 및 .NET 프레임워크에 대한 지식이 필요합니다.
### 3. 마이크로소프트 프로젝트 파일
XLSX 파일로 구성하고 저장하려는 Microsoft Project 파일(MPP)을 준비합니다.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## 1단계: 프로젝트 로드
```csharp
var project = new Project("YourProjectFile.mpp");
```
구성하려는 Microsoft Project 파일을 로드합니다.
## 2단계: XlsxOptions 정의
```csharp
var options = new XlsxOptions();
```
 인스턴스 만들기`XlsxOptions` XLSX로 저장하기 위한 설정을 구성합니다.
## 3단계: 간트 차트 열 추가
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
옵션에 원하는 간트 차트 열을 추가합니다.
## 4단계: 리소스 보기 열 추가
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
옵션에 리소스 보기에 대해 원하는 열을 포함합니다.
## 5단계: 과제 보기 열 추가
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
옵션에서 과제 보기에 원하는 열을 추가하세요.
## 6단계: 인코딩 설정
```csharp
options.Encoding = Encoding.Unicode;
```
출력 파일의 인코딩을 설정합니다.
## 7단계: 프로젝트를 XLSX로 저장
```csharp
project.Save("OutputFile.xlsx", options);
```
구성된 옵션이 포함된 프로젝트를 XLSX 파일로 저장합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS Project XLSX 옵션을 구성하는 방법을 배웠습니다. 다음 단계를 수행하면 요구 사항에 따라 출력 형식을 사용자 정의하여 프로젝트 관리 작업 흐름의 유연성과 유용성을 향상시킬 수 있습니다.
## FAQ

### Q: 간트 차트, 자원 보기, 과제 보기에 대해 서로 다른 열을 별도로 구성할 수 있나요?

A: 예, Aspose.Tasks for .NET을 사용하여 각 보기에 대해 독립적으로 열을 사용자 정의할 수 있습니다.

### Q: .NET용 Aspose.Tasks를 구매하기 전에 사용할 수 있는 평가판이 있습니까?

 A: 예, 다음 사이트에서 무료 평가판을 다운로드할 수 있습니다.[.NET 릴리스 페이지용 Aspose.Tasks](https://releases.aspose.com/).

### Q: 구현 중에 문제가 발생하거나 질문이 있는 경우 어떻게 지원을 받을 수 있나요?

 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 및 Aspose 지원 팀의 도움을 받으십시오.

### Q: Windows가 아닌 플랫폼에서 .NET용 Aspose.Tasks를 사용하여 XLSX 파일을 생성할 수 있습니까?

A: Aspose.Tasks for .NET은 기본적으로 Windows 플랫폼용으로 설계되었지만 다른 플랫폼에 대한 호환성 옵션도 살펴볼 수 있습니다.

### Q: 테스트 목적으로 사용할 수 있는 임시 라이선스 옵션이 있습니까?

 A: 네, 임시 면허를 취득할 수 있습니다.[Aspose.Tasks 임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).