---
title: Aspose.Tasks를 사용하여 MS 프로젝트 개요 값 관리
linktitle: Aspose.Tasks의 개요 값 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일의 개요 값을 관리하는 방법을 알아보세요. 코드 예제가 포함된 단계별 튜토리얼입니다.
type: docs
weight: 17
url: /ko/net/outline-code-page-settings/outline-value-collection/
---
## 소개
Aspose.Tasks for .NET은 Microsoft Project 파일과 상호 작용할 수 있는 포괄적인 기능 세트를 제공합니다. 그러한 기능 중 하나는 프로젝트 내에서 개요 값을 관리하는 기능입니다. 이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 개요 값을 수집하고 조작하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET용 Aspose.Tasks: 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: Visual Studio와 같은 적합한 IDE가 설치되어 있는지 확인하세요.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.
## 네임스페이스 가져오기
C# 코드 파일에서 Aspose.Tasks 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Tasks;
using System;

```
제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
 먼저,`Project` 기존 Microsoft Project 파일을 로드하여 개체:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 2단계: 기존 개요 값 지우기
그런 다음 프로젝트에서 기존 개요 값을 모두 지웁니다.
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## 3단계: 새 개요 코드 정의
이제 설명과 값을 사용하여 새 개요 코드를 정의합니다.
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## 4단계: 개요 값 업데이트
개요 코드 값을 업데이트합니다.
```csharp
codeDefinition.Values[0].Value = "654321";
```
## 5단계: 개요 값 반복
개요 값을 반복하고 세부 정보를 인쇄합니다.
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## 6단계: 개요 값 조작
필요에 따라 개요 값 제거, 삽입, 복사와 같은 작업을 수행합니다.
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일의 개요 값으로 작업하는 방법을 배웠습니다. 제공된 단계를 수행하면 프로젝트 내에서 개요 값을 효율적으로 관리하여 더 큰 제어력과 유연성을 얻을 수 있습니다.
## FAQ
### Q: 여러 개요 코드를 동시에 조작할 수 있습니까?
A: 예, Aspose.Tasks를 사용하여 프로젝트 내에서 여러 개요 코드를 정의하고 조작할 수 있습니다.
### Q: Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks는 MPP 및 XML 형식을 포함하여 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: 개요 값으로 작업하는 동안 오류를 처리하려면 어떻게 해야 합니까?
A: try-catch 블록과 같은 오류 처리 메커니즘을 구현하여 예외를 적절하게 관리할 수 있습니다.
### Q: 내 프로젝트에서 개요 값의 모양을 사용자 지정할 수 있습니까?
A: 예, Aspose.Tasks는 요구 사항에 따라 개요 값의 모양과 동작을 사용자 정의할 수 있는 광범위한 API를 제공합니다.
### Q: Aspose.Tasks에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지역사회 지원을 위해[선적 서류 비치](https://reference.aspose.com/tasks/net/) API 및 기능에 대한 자세한 내용은