---
title: .NET용 Aspose.Tasks에서 테이블 필드 컬렉션 마스터링
linktitle: Aspose.Tasks의 테이블 필드 컬렉션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 역동적인 프로젝트 관리 세계를 탐험해보세요. 맞춤형 프로젝트 경험을 위해 테이블 필드 컬렉션을 조작하는 방법을 알아보세요.
type: docs
weight: 13
url: /ko/net/task-table-management/table-field-collection/
---
## 소개
Aspose.Tasks for .NET은 Microsoft Project 파일 작업을 위한 광범위한 기능을 제공하여 프로젝트 관리를 용이하게 하는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks의 테이블 필드 컬렉션을 자세히 살펴보고 C#을 사용하여 효율적으로 조작하고 관리하는 방법을 탐구합니다.
## 전제조건
시작하기 전에 다음이 설정되어 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식.
- .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- Visual Studio와 같은 IDE(통합 개발 환경).
## 네임스페이스 가져오기
먼저 C# 파일 시작 부분에 필요한 네임스페이스를 가져왔는지 확인하세요.
```csharp
    using Aspose.Tasks;
    using System;
    
```
이제 단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 설정
프로젝트 파일이 있는 문서 디렉터리의 경로를 설정합니다.
```csharp
String DataDir = "Your Document Directory";
```
## 2단계: 프로젝트 파일 로드
Aspose.Tasks 라이브러리를 사용하여 프로젝트 파일을 로드합니다.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## 3단계: 테이블 필드 반복
프로젝트 내의 테이블 필드를 반복합니다.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    // 테이블 필드 반복
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## 4단계: 새 테이블 필드 추가
기존 테이블에 새 테이블 필드를 추가합니다.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## 5단계: 새 필드 삽입
테이블 내의 특정 위치에 새 필드를 삽입합니다.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## 6단계: 새 테이블 필드 편집
인덱스 액세스를 사용하여 새로 추가된 테이블 필드를 편집합니다.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## 7단계: 필드 제거
테이블 필드를 하나씩 제거하거나 전체 컬렉션을 지웁니다.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// 필드 제거
table.TableFields.RemoveAt(idx);
```
## 8단계: 컬렉션 삭제
테이블 필드 컬렉션을 하나씩 또는 완전히 지웁니다.
```csharp
if (deleteOneByOne)
{
    // 하나씩 제거해 보세요
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // 컬렉션을 완전히 삭제하세요.
    table.TableFields.Clear();
}
```
이제 .NET용 Aspose.Tasks의 테이블 필드 컬렉션을 성공적으로 탐색하여 프로젝트 요구 사항에 따라 테이블 필드를 관리하고 조작할 수 있습니다.
## 결론
결론적으로 Aspose.Tasks for .NET에서 테이블 필드 컬렉션을 사용하는 방법을 이해하면 효율적인 프로젝트 관리 및 사용자 정의 가능성이 열립니다. Aspose.Tasks가 제공하는 유연성을 통해 개발자는 특정 프로젝트 요구 사항을 원활하게 충족하도록 애플리케이션을 맞춤화할 수 있습니다.
## 자주 묻는 질문
### 모든 버전의 Microsoft Project 파일에서 Aspose.Tasks for .NET을 사용할 수 있나요?
예, Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원하여 호환성과 유연성을 보장합니다.
### 런타임 중에 테이블 필드를 동적으로 생성하고 수정할 수 있습니까?
전적으로! 튜토리얼에 표시된 대로 필요에 따라 테이블 필드를 동적으로 추가, 삽입, 편집 및 제거할 수 있습니다.
### 상업용 프로젝트에서 Aspose.Tasks for .NET을 사용하기 위한 라이선스 고려 사항이 있나요?
 예, 상업용 프로젝트에서 Aspose.Tasks for .NET을 사용하려면 유효한 라이선스가 필요합니다. 라이센스를 취득하실 수 있습니다[여기](https://purchase.aspose.com/buy).
### .NET용 Aspose.Tasks에 대한 지원을 받거나 도움을 받으려면 어떻게 해야 합니까?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원을 받고, 질문하고, 커뮤니티와 협력할 수 있습니다.
### .NET용 Aspose.Tasks에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 통해 Aspose.Tasks for .NET의 기능을 탐색할 수 있습니다. 다운로드 해[여기](https://releases.aspose.com/).