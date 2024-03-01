---
title: Aspose.Tasks의 개요 코드 MS 프로젝트 수집
linktitle: Aspose.Tasks의 개요 코드 컬렉션
second_title: Aspose.태스크 .NET API
description: Aspose.Tasks for .NET을 사용하여 Microsoft Project 개요 코드를 수집하는 방법을 알아보세요. 이 포괄적인 튜토리얼은 단계별 지침을 제공합니다.
type: docs
weight: 11
url: /ko/net/outline-code-page-settings/outline-code-collection/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 개요 코드를 수집하는 방법을 살펴보겠습니다. 명확성과 이해를 보장하기 위해 프로세스를 단계별 지침으로 나누어 보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C# 프로그래밍에 대한 기본 이해: C#에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
먼저 C# 프로젝트의 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## 1단계: 프로젝트 파일 로드
 다음을 사용하여 Microsoft Project 파일을 로드하는 것으로 시작합니다.`Project` 수업.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## 2단계: 개요 코드 수집
프로젝트 작업에서 개요 코드를 수집하는 컬렉터를 만듭니다.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## 3단계: 작업 및 개요 코드 반복
수집된 작업과 개요 코드를 반복하여 세부 정보를 인쇄합니다.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## 4단계: 사용자 정의 개요 코드 정의 추가
프로젝트에 사용자 정의 개요 코드 정의를 추가합니다.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## 5단계: 개요 코드 생성 및 삽입
개요 코드를 생성하고 작업에 삽입합니다.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## 6단계: 개요 코드 조작
필요에 따라 삽입, 제거, 삭제 등 개요 코드를 조작합니다.
```csharp
// 조작의 예
// ...
// 2가 포함된 코드를 올바른 위치에 삽입하세요.
task.OutlineCodes.Insert(2, code2);
// 코드가 삽입되었는지 확인하세요
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 개요 코드를 수집하는 방법을 배웠습니다. 다음 단계를 수행하면 프로젝트 내에서 개요 코드를 효과적으로 관리하여 구성과 명확성을 높일 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 주로 .NET 플랫폼을 대상으로 하지만 Aspose.Tasks for Cloud를 통해 다른 프로그래밍 언어에 대한 지원도 제공합니다.
### Q: Aspose.Tasks for .NET이 처리할 수 있는 프로젝트 파일의 크기에 제한이 있나요?
A: .NET용 Aspose.Tasks는 대규모 프로젝트 파일을 효율적으로 처리할 수 있지만 성능은 파일의 복잡성과 크기에 따라 달라질 수 있습니다.
### Q: Aspose.Tasks for .NET은 최신 버전의 Microsoft Project와 호환됩니까?
A: 예, Aspose.Tasks for .NET은 최신 버전을 포함하여 다양한 버전의 Microsoft Project를 지원합니다.
### Q: .NET용 Aspose.Tasks로 작업할 때 출력 형식을 사용자 정의할 수 있나요?
A: 물론입니다. Aspose.Tasks for .NET은 요구 사항에 따라 출력 형식을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### Q: Aspose.Tasks for .NET에 대한 추가 지원이나 리소스는 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for .NET에 관한 지원이나 문의 사항이 있으신 경우.