---
title: Aspose.Tasks에서 MS 프로젝트 속성 컬렉션 관리
linktitle: Aspose.Tasks에서 확장된 속성 컬렉션 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS Project 확장 속성을 효율적으로 관리하는 방법을 알아보세요. 단계별 지침에 따라 작업 속성을 원활하게 조작합니다.
type: docs
weight: 12
url: /ko/net/tasks-project-management/extended-attribute-collection/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 MS Project 확장 속성을 효율적으로 관리하고 싶으십니까? 이 튜토리얼에서는 프로세스를 단계별로 안내합니다. 뛰어들어보자!
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
3. C# 기본 지식: C# 프로그래밍 언어 기본 사항을 숙지하세요.

## 네임스페이스 가져오기
필요한 네임스페이스를 프로젝트로 가져오는 것부터 시작하세요.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1단계: 프로젝트 파일 로드
먼저 다음 코드 조각을 사용하여 MS 프로젝트 파일을 로드합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 2단계: 작업 및 확장된 속성에 액세스
특정 작업 및 해당 확장 속성에 액세스합니다.
```csharp
var task = project.RootTask.Children.GetById(1);
```
## 3단계: 확장된 속성 지우기
필요한 경우 기존 확장 속성을 지웁니다.
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## 4단계: 확장된 속성 정의 생성
새로운 확장된 속성에 대한 정의를 만듭니다.
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## 5단계: 작업 확장 속성 반복
작업 확장 속성을 반복합니다.
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## 6단계: 확장된 속성 추가
작업에 새로운 확장 속성을 추가합니다.
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## 7단계: 확장된 속성 작업
필요에 따라 확장된 속성에 대한 작업을 수행합니다.
## 8단계: 확장된 속성 제거
인덱스별로 또는 조건부로 확장된 속성을 제거합니다.
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## 9단계: 다른 작업에 속성 복사
동일하거나 다른 프로젝트 내의 다른 작업에 속성을 복사합니다.
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## 결론
.NET용 Aspose.Tasks를 사용하면 MS 프로젝트 확장 속성 컬렉션 관리가 원활해집니다. 이 튜토리얼에 설명된 단계를 따르면 확장된 속성을 효율적으로 처리하여 프로젝트 관리 기능을 향상시킬 수 있습니다.
## FAQ
### Q: 여러 프로젝트에서 확장된 속성을 조작할 수 있습니까?
A: 예, Aspose.Tasks for .NET을 사용하여 다른 프로젝트의 작업 간에 확장된 속성을 복사할 수 있습니다.
### Q: 작업당 확장 속성 수에 제한이 있습니까?
A: .NET용 Aspose.Tasks는 작업당 확장 속성 수에 본질적인 제한을 두지 않습니다.
### Q: 사용자 정의 확장 속성 필드를 생성할 수 있습니까?
답: 물론이죠! Aspose.Tasks for .NET을 사용하면 프로젝트 요구 사항에 맞는 사용자 정의 확장 속성 필드를 정의할 수 있습니다.
### Q: .NET용 Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일 읽기 및 쓰기를 지원합니까?
A: 예, .NET용 Aspose.Tasks는 다양한 버전에서 MS Project 파일 형식을 지원합니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).