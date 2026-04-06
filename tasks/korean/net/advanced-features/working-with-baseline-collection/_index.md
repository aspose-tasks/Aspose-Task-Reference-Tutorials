---
date: 2026-04-06
description: Aspose.Tasks for .NET에서 모든 기준선을 삭제하고 기준선 컬렉션을 관리하는 방법을 단계별 코드 예제로 배워보세요.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Aspose.Tasks 기준선 컬렉션으로 모든 기준선 삭제
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks 베이스라인 컬렉션을 사용하여 모든 베이스라인 삭제
url: /ko/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 베이스라인 컬렉션을 사용하여 모든 베이스라인 삭제

## 소개

Aspose.Tasks for .NET은 .NET 애플리케이션에서 Microsoft Project 파일을 직접 조작할 수 있게 해줍니다. 가장 강력한 기능 중 하나는 리소스에 대한 **delete all baselines** 기능으로, 프로젝트 추적 데이터를 재설정하거나 새로운 베이스라인 기간을 시작해야 할 때 필수적입니다. 이 튜토리얼에서는 프로젝트 파일을 로드하고 특정 리소스에 연결된 모든 베이스라인을 제거하는 전체 과정을 명확하고 대화형 설명과 바로 실행 가능한 C# 코드와 함께 단계별로 안내합니다.

## 빠른 답변
- **delete all baselines는 무엇을 하나요?** 선택된 리소스에 저장된 모든 베이스라인 레코드를 제거하여 과거 비용 및 작업 데이터를 지웁니다.  
- **왜 필요할까요?** 주요 프로젝트 변경 후 또는 원래 베이스라인이 더 이상 관련 없을 때 추적을 재설정하기 위해 필요합니다.  
- **어떤 라이브러리가 이 기능을 제공하나요?** Aspose.Tasks for .NET.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **코드가 .NET 6+와 호환되나요?** 네, API는 .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6에서 작동합니다.

## 베이스라인이란 무엇이며 모든 베이스라인을 삭제하는 이유는?

베이스라인은 특정 시점의 비용, 작업 및 일정에 대한 원래 계획을 캡처합니다. 프로젝트 진행 중에 여러 베이스라인(베이스라인 1, 베이스라인 2 등)을 만들어 실제 진행 상황을 다양한 계획 스냅샷과 비교할 수 있습니다. 그러나 프로젝트 범위 재조정이나 새 출발과 같은 상황에서는 이러한 과거 베이스라인이 혼란을 초래할 수 있습니다. 모든 베이스라인을 삭제하면 깨끗한 상태가 되어 현재 현실을 반영하는 새로운 베이스라인을 설정할 수 있습니다.

## 전제 조건

1. **Visual Studio** – 최신 버전 중 하나(Community, Professional, Enterprise).  
2. **Aspose.Tasks for .NET** – [download link](https://releases.aspose.com/tasks/net/)에서 다운로드하세요.  
3. **기본 C# 지식** – 변수, 루프, 콘솔 출력에 익숙해야 합니다.  
4. **Microsoft Project 파일** (`.mpp`) – 예제에서는 *WorkWithBaselineCollection.mpp* 샘플 파일을 사용합니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 범위에 가져와 컴파일러가 사용할 클래스들을 찾을 수 있도록 합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 1단계: 프로젝트 파일 로드

기존 Project 파일을 로드합니다. `DataDir`을 `.mpp` 파일이 들어 있는 폴더 경로로 조정하세요.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 2단계: 대상 리소스 가져오기

예시로 UID = 1인 리소스를 가져옵니다. 실제 상황에서는 이름이나 다른 식별자를 사용해 리소스를 찾게 됩니다.

```csharp
var resource = project.Resources.GetByUid(1);
```

## 3단계: 기존 베이스라인 정보 표시

삭제하기 전에 리소스에 현재 연결된 베이스라인을 확인하는 것이 좋습니다. 이렇게 하면 올바른 데이터를 제거하고 있다는 확신을 가질 수 있습니다.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 4단계: 모든 베이스라인 순회

여기서는 각 베이스라인을 순회하면서 비용, 작업, 획득 가치(BCWP/BCWS)와 같은 주요 지표를 출력합니다. 이 단계는 선택 사항이지만 로깅이나 감사 목적에 유용합니다.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 모든 베이스라인 삭제

이제 핵심 작업을 수행합니다: 선택된 리소스에 대해 **delete all baselines**를 수행합니다. 컬렉션을 리스트로 복사한 뒤 반복하면서 하나씩 제거하여 컬렉션을 수정하는 동안 발생할 수 있는 문제를 방지합니다.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

이 블록이 실행된 후 `resource.Baselines.Count`는 `0`이 되어 모든 베이스라인 레코드가 삭제되었음을 확인할 수 있습니다.

## 일반적인 문제 및 팁

- **NullReferenceException** – 프로젝트 파일에 대상 리소스가 실제로 포함되어 있는지 확인하세요; 그렇지 않으면 `GetByUid`가 `null`을 반환합니다.  
- **Licensing** – 유효한 Aspose.Tasks 라이선스가 없으면 출력에 워터마크가 표시되고 기능이 제한됩니다.  
- **Performance** – 매우 큰 프로젝트의 경우 `Parallel.ForEach`를 사용해 제거 과정을 가속화하는 것을 고려하세요. 단, 기본 컬렉션은 스레드 안전하지 않다는 점을 기억하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks가 대용량 프로젝트 파일을 처리할 수 있나요?**  
A: 네, Aspose.Tasks는 성능을 최적화했으며 멀티 기가바이트 `.mpp` 파일을 효율적으로 처리할 수 있습니다.

**Q: 라이브러리가 모든 Microsoft Project 버전과 호환되나요?**  
A: Aspose.Tasks는 Project 2000부터 Project 2024까지 지원하며, 오래된 `.mpp` 형식과 최신 XML 기반 파일 모두를 다룹니다.

**Q: 베이스라인을 삭제하기 전에 커스터마이즈할 수 있나요?**  
A: 물론입니다. 베이스라인을 제거하기 전에 비용, 작업, 날짜 등 원하는 속성을 읽거나 수정할 수 있습니다.

**Q: Aspose.Tasks가 클라우드 플랫폼에서 작동하나요?**  
A: 네, API는 Azure App Service, AWS Lambda(.NET Core 사용) 및 Docker 컨테이너 등 .NET 호환 환경 어디서든 실행됩니다.

**Q: 커뮤니티에 도움을 요청하려면 어디로 가면 되나요?**  
A: 다른 개발자와 Aspose 직원이 모여 있는 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하세요.

## 결론

이 가이드에서는 Aspose.Tasks for .NET을 사용해 리소스의 **delete all baselines**를 수행하는 방법을 보여주었습니다. 단계별 코드를 따라 하면 베이스라인 데이터를 재설정하고 프로젝트 추적을 깔끔하게 유지하며 새로운 계획 주기를 준비할 수 있습니다. 삭제 후 새로운 베이스라인을 생성해 보면서 라이브러리가 프로젝트 파일을 어떻게 업데이트하는지 실험해 보세요.

---

**마지막 업데이트:** 2026-04-06  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}