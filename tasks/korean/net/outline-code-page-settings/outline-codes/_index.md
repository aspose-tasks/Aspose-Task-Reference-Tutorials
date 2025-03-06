---
title: .NET용 Aspose.Tasks에서 프로젝트 개요 코드 관리
linktitle: Aspose.Tasks에서 개요 코드 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 코드를 관리하는 방법을 알아보세요. 프로젝트 구성을 쉽게 단순화하세요.
weight: 10
url: /ko/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Tasks에서 프로젝트 개요 코드 관리

## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 개요 코드를 관리하는 방법을 살펴보겠습니다. 개요 코드는 사용자가 특정 기준에 따라 작업을 분류하고 구성할 수 있는 Microsoft Project의 사용자 정의 필드입니다. Aspose.Tasks는 이러한 개요 코드를 프로그래밍 방식으로 읽고 조작하는 프로세스를 단순화합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Tasks: 다음에서 .NET 라이브러리용 Aspose.Tasks를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
2. 개발 환경: Visual Studio와 같은 .NET 프로그래밍에 적합한 개발 환경을 설정합니다.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 코드 예제를 이해하는 데 도움이 됩니다.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다. 이를 통해 Aspose.Tasks 라이브러리에서 제공하는 클래스와 메서드에 액세스할 수 있습니다.
1. Visual Studio 열기: Visual Studio IDE를 시작합니다.
2. 새 프로젝트 만들기: 새 C# 프로젝트를 시작하거나 Aspose.Tasks를 사용하려는 기존 프로젝트를 엽니다.
3. Aspose.Tasks 참조 추가: 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.Tasks"를 검색하고 최신 버전을 설치합니다.
4. Aspose.Tasks 네임스페이스 가져오기: C# 파일 상단에 다음 using 지시문을 추가합니다.
```csharp
using Aspose.Tasks;
using System;

```
## 1단계: 문서 디렉터리 정의
먼저 MS 프로젝트 파일이 포함된 디렉터리로 경로를 설정합니다.
```csharp
String DataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 프로젝트 파일의 실제 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
 새 인스턴스화`Project` MS 프로젝트 파일을 로드하여 개체를 만듭니다.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
지정된 파일을 사용하여 프로젝트 개체를 초기화합니다.
## 3단계: 개요 코드 읽기
프로젝트의 모든 작업을 반복하고 해당 작업의 개요 코드를 검색합니다.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
이 코드 조각은 각 작업을 반복하여 개요 코드가 있는지 확인하고 작업과 연결된 각 개요 코드에 대한 필드 ID, 값 GUID 및 값 ID와 같은 세부 정보를 인쇄합니다.

## 결론
결론적으로 Aspose.Tasks for .NET은 Microsoft Project 개요 코드를 프로그래밍 방식으로 관리하기 위한 강력한 기능을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 C#을 사용하여 MS 프로젝트 파일의 개요 코드를 효율적으로 읽고 조작할 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 사용하여 개요 코드를 수정할 수 있나요?
A: 예, .NET용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 개요 코드를 수정할 수 있습니다. 작업의 개요 코드에 액세스하고 필요에 따라 해당 값을 업데이트하기만 하면 됩니다.
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 2003, 2007, 2010, 2013, 2016 및 2019를 포함하여 광범위한 Microsoft Project 버전을 지원합니다.
### Q: Aspose.Tasks를 상업적으로 사용하려면 라이선스가 필요합니까?
A: 예, Aspose.Tasks를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 얻을 수 있습니다.
### Q: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?
A: 예, 웹사이트에서 Aspose.Tasks의 무료 평가판을 다운로드하여 기능을 평가할 수 있습니다.
### Q: Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 A: 다음 포럼을 방문하여 Aspose.Tasks에 대한 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).## 완전한 소스 코드
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
