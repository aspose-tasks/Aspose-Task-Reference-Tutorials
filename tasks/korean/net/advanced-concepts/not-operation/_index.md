---
date: 2026-03-14
description: Aspose.Tasks for .NET에서 작업을 제외하는 필터링 방법을 배우고, 유연한 작업 쿼리를 위해 적용되지 않은(not)
  조건과 함께 NOT 필터를 사용하는 방법을 알아보세요.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 작업 필터링이 작동하지 않음
url: /ko/net/advanced-concepts/not-operation/
weight: 20
---

Also ensure markdown formatting preserved.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 필터 NOT 연산

## 소개

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 **작업 필터 NOT 연산**을 수행하는 방법을 배웁니다. NOT 연산은 필터 조건을 반전시켜 특정 기준을 **충족하지 않는** 모든 작업을 선택할 수 있게 해줍니다. 값이 없는 작업을 제외하거나 추가 코드를 작성하지 않고 복잡한 쿼리를 구성해야 할 때 이 기능이 필수적입니다.

## 빠른 답변
- **NOT 연산은 무엇을 하나요?** 필터 조건을 반전시켜 원래 테스트에 실패한 항목을 반환합니다.  
- **왜 작업 필터 NOT 연산을 사용하나요?** 제외 로직을 단순화하고 코드를 읽기 쉽게 유지합니다.  
- **어떤 네임스페이스가 NOT 클래스를 제공하나요?** `Aspose.Tasks.Util`.  
- **프로덕션에 라이선스가 필요합니까?** 예, 비시험용으로는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **NOT를 다른 조건과 결합할 수 있나요?** 물론입니다—`AndCondition`, `OrCondition` 등과 결합할 수 있습니다.

## 필터 작업 NOT 연산이란?
**필터 작업 NOT 연산**은 작업 필터에 적용되는 논리적 부정입니다. 조건에 일치하는 작업을 선택하는 대신, 해당 조건에 *일치하지 않는* 작업을 선택합니다. 빈 필드, 특정 상태 또는 제외하고 싶은 다른 속성을 가진 작업을 무시하려는 경우에 특히 유용합니다.

## 작업을 필터링할 때 NOT 조건을 적용하는 이유는?
**NOT 조건**을 적용하면 프로젝트 데이터를 여러 번 순회할 필요가 줄어듭니다. 간결하고 유지 보수하기 쉬운 코드를 작성할 수 있으며, Aspose.Tasks의 최적화된 엔진에 평가를 위임함으로써 성능이 향상됩니다.

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. Visual Studio: 코드 예제를 따라하려면 Visual Studio가 설치되어 있어야 합니다.  
2. Aspose.Tasks for .NET: [website](https://releases.aspose.com/tasks/net/)에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.  
3. C# 기본 이해: C# 프로그래밍 언어에 익숙하면 코드 예제를 이해하는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저 코드에 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 단계 1: 프로젝트 및 작업 설정

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Aspose.Tasks에서 제공하는 `Project` 클래스를 사용하여 **Project2.mpp**라는 프로젝트 파일을 로드합니다. 지정된 디렉터리에 프로젝트 파일이 존재하는지 확인하세요.

## 단계 2: 프로젝트 작업 수집

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

여기서는 `ChildTasksCollector` 객체를 만들어 프로젝트 내 모든 작업을 수집합니다. 그런 다음 `TaskUtils.Apply`를 사용해 프로젝트의 작업 계층을 순회하며 모든 하위 작업을 모읍니다.

## 단계 3: 필터 조건 정의

```csharp
var filter = new NullCondition();
```

`NullCondition`이라는 사용자 정의 클래스를 사용해 필터 조건을 정의합니다. 이 조건은 **null** 값을 가진 작업을 선택합니다.  

> **Pro tip:** `NullCondition`을 다른 조건(예: `EqualsCondition`)으로 교체하면 다양한 속성을 대상으로 할 수 있습니다.

## 단계 4: NOT 연산 적용

```csharp
var condition = new Not<Task>(filter);
```

Aspose.Tasks에서 제공하는 `Not<T>` 클래스를 사용해 필터 조건에 **NOT 연산**을 적용합니다. 원래 조건을 반전시켜 이제 필터는 **null 값이 없는** 작업을 선택합니다. 이것이 **NOT 필터 사용 방법**의 핵심입니다.

## 단계 5: 작업 필터링

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

사용자 정의 `Filter` 메서드를 통해 적용된 조건에 따라 수집된 작업을 필터링합니다. 이 메서드는 작업 컬렉션과 필터 조건을 받아 **NOT 조건 적용**을 만족하는 작업 목록을 반환합니다.

## 단계 6: 필터링된 작업 처리

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

마지막으로 필터링된 작업을 순회하며 원하는 작업을 수행합니다. 예제에서는 작업 이름을 콘솔에 출력하지만, 이 블록을 확장해 필드 업데이트, 작업 이동, 보고서 생성 등을 구현할 수 있습니다.

## 일반적인 사용 사례

- **완료된 작업 제외**: 보류 중인 작업 목록을 생성할 때.  
- **사용자 정의 필드가 없는 작업 찾기** (예: null인 “Owner” 열).  
- **다른 조건과 결합**하여 정교한 쿼리를 구축합니다. 예: “null이 아니고 시작 날짜가 오늘 이전인 작업”.

## 문제 해결 및 팁

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| 작업이 반환되지 않음 | 원래 조건이 너무 제한적일 수 있습니다. | 조건 논리를 확인하거나 `new TrueCondition()`과 같은 더 간단한 필터로 테스트하세요. |
| `NullReferenceException` | `DataDir` 경로가 올바르지 않습니다. | `DataDir`이 *Project2.mpp*가 포함된 폴더를 가리키는지 확인하세요. |
| 예상치 못한 결과 | `Not<T>`를 다른 조건과 잘못 혼합했습니다. | 괄호를 사용하세요: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 .NET 프레임워크와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET Core, .NET Standard 및 기존 .NET Framework를 지원합니다.

**Q: Aspose.Tasks의 무료 체험판이 있나요?**  
A: 예, [website](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 지원을 어떻게 받을 수 있나요?**  
A: 지원 문의나 기술 지원이 필요하면 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하세요.

**Q: Aspose.Tasks 임시 라이선스를 구매할 수 있나요?**  
A: 예, [purchase page](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 구매할 수 있습니다.

**Q: Aspose.Tasks에 대한 포괄적인 문서를 어디서 찾을 수 있나요?**  
A: [Aspose.Tasks 문서 페이지](https://reference.aspose.com/tasks/net/)에서 전체 문서를 확인할 수 있습니다.

## 결론

**필터 작업 NOT 연산**과 **NOT 필터 사용 방법**을 마스터하면 Aspose.Tasks에서 작업 선택을 세밀하게 제어할 수 있습니다. 이를 통해 코드를 더 깔끔하게 작성하고, 수동 제외를 피하며, 강력한 프로젝트 관리 유틸리티를 구축할 수 있습니다.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}