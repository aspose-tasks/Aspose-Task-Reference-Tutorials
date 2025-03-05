---
title: Aspose.Tasks에서 프로젝트 자원 수집 관리
linktitle: Aspose.Tasks에서 리소스 수집 관리
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks API를 사용하여 .NET에서 Microsoft Project 리소스 컬렉션을 효율적으로 관리하는 방법을 알아보세요. 생산성과 유연성을 높입니다.
type: docs
weight: 13
url: /ko/net/resource-risk-analysis/managing-resource-collection/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 리소스 컬렉션을 효과적으로 관리하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 프로그래밍 방식으로 Microsoft Project 파일을 사용하여 프로젝트 데이터를 원활하게 통합하고 조작할 수 있도록 하는 강력한 API입니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. C# 및 .NET Framework에 대한 지식: 이 자습서에서는 C# 프로그래밍 언어 및 .NET Framework에 익숙하다고 가정합니다.
2. .NET용 Aspose.Tasks 설치: .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
3. 개발 환경 설정: Visual Studio 또는 기타 선호하는 IDE를 사용하여 개발 환경을 설정합니다.

## 네임스페이스 가져오기
시작하기 전에 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 1단계: 프로젝트 파일 로드
먼저 Microsoft Project 파일을 Aspose.Tasks 프로젝트 개체에 로드합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## 2단계: 빈 리소스 추가
다음으로 프로젝트에 빈 리소스를 추가해 보겠습니다.
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## 3단계: 이름이 있는 리소스 추가
이제 프로젝트에 지정된 이름의 리소스를 추가합니다.
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## 4단계: 다른 리소스 앞에 리소스 추가
해당 ID를 기반으로 다른 리소스 앞에 지정된 이름을 가진 리소스를 추가합니다.
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## 5단계: ID 또는 UID로 리소스에 액세스
ID 또는 UID로 리소스에 액세스할 수 있습니다.
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## 6단계: 리소스 정보 인쇄
프로젝트 리소스에 대한 정보를 인쇄합니다.
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## 7단계: 리소스 삭제
프로젝트에서 리소스를 삭제합니다.
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## 결론
.NET용 Aspose.Tasks를 사용하여 Microsoft Project 리소스 컬렉션을 관리하면 개발자에게 프로그래밍 방식으로 프로젝트 리소스를 효율적으로 처리할 수 있는 강력한 도구 세트가 제공됩니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 내의 리소스를 원활하게 조작하여 프로젝트 관리 작업의 생산성과 유연성을 향상시킬 수 있습니다.
## FAQ
### Q: Aspose.Tasks가 대규모 프로젝트 파일을 처리할 수 있나요?

A: 예, Aspose.Tasks는 대규모 프로젝트 파일을 효율적으로 처리하도록 설계되어 높은 성능과 안정성을 제공합니다.

### Q: Aspose.Tasks는 다른 버전의 Microsoft Project와 호환됩니까?

A: Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.

### Q: Aspose.Tasks를 사용하여 리소스 속성을 사용자 지정할 수 있나요?

A: 물론 Aspose.Tasks는 특정 프로젝트 요구 사항에 따라 리소스 속성을 사용자 정의할 수 있는 광범위한 기능을 제공합니다.

### Q: Aspose.Tasks는 동시 작업을 위한 멀티스레딩을 지원합니까?

A: 예, Aspose.Tasks는 멀티 스레딩을 지원하므로 프로젝트 데이터에 대한 동시 작업을 통해 성능을 향상시킬 수 있습니다.

### Q: Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?

 A: 예, Aspose.Tasks 사용자는 포럼을 통해 기술 지원에 액세스할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).