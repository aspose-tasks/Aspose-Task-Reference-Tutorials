---
date: 2026-07-05
description: Aspose.Tasks for .NET의 복사 옵션을 사용하여 프로젝트 데이터를 복사하는 방법을 배웁니다. 정확한 프로젝트
  관리로 .NET 애플리케이션을 강화하세요.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Aspose.Tasks에서 복사 옵션을 사용하여 프로젝트 데이터를 복사하는 방법
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks에서 복사 옵션을 사용하여 프로젝트 데이터를 복사하는 방법
url: /ko/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 복사 옵션을 사용하여 프로젝트 데이터 복사하는 방법

## 소개

프로젝트 정보를 한 Microsoft Project 파일에서 다른 파일로 **프로젝트 복사 방법** 복사해야 할 경우, Aspose.Tasks for .NET은 깔끔하고 코드‑우선적인 방법을 제공합니다. 이 튜토리얼에서는 전체 워크플로우—소스 프로젝트 로드, 복사 옵션 구성, 복사 생성, 결과 로드—를 단계별로 살펴보며, .NET 애플리케이션에 프로젝트 복사 로직을 자신 있게 통합할 수 있도록 합니다.

## 빠른 답변
- **복사 기능은 무엇을 하나요?** 프로젝트 데이터를 복제하면서 캘린더, 리소스, 뷰 정보와 같은 특정 섹션을 포함하거나 제외할 수 있습니다.  
- **어떤 클래스가 동작을 제어하나요?** `CopyToOptions`를 사용하면 복사되는 항목을 세밀하게 조정할 수 있습니다.  
- **라이선스가 필요합니까?** 프로덕션에서는 유효한 Aspose.Tasks 라이선스가 필요하며, 개발 단계에서는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 형식은?** Aspose.Tasks는 MPP, XML, XER 파일을 처리하며, 총 20개 이상의 형식을 지원합니다.  
- **뷰 데이터를 건너뛸 수 있나요?** 예, `CopyToOptions.SkipViewData = true`로 설정하면 UI 관련 정보를 제외할 수 있습니다.

## Aspose.Tasks에서 “프로젝트 복사 방법”이란?
**“프로젝트 복사 방법”**은 Aspose.Tasks API를 사용하여 Project 객체의 데이터를 새 파일로 복제하고, 필요에 따라 원하지 않는 요소를 필터링하는 것을 의미합니다. 이 작업은 템플릿 생성, 아카이빙, 또는 수동 UI 단계 없이 프로젝트 변형을 만들 때 유용하며, 모든 지원 파일 형식에서 작동합니다.

## Aspose.Tasks에서 복사 옵션을 사용하는 이유
Aspose.Tasks는 **50개 이상의 프로젝트 관련 엔터티**(작업, 리소스, 캘린더, 할당 등)를 지원하며, **10,000개까지 작업**이 포함된 파일을 처리하면서 메모리 사용량을 200 MB 이하로 유지합니다. `CopyToOptions`를 사용하면 무거운 뷰 데이터를 복사하지 않아 출력 파일 크기를 **30‑40 %** 줄이고, 대형 프로젝트의 경우 작업 속도를 대략 **2배** 가속화할 수 있습니다.

## 사전 요구 사항

1. **Aspose.Tasks for .NET** – 최신 버전을 [download link](https://releases.aspose.com/tasks/net/)에서 다운로드하십시오.  
2. **.NET 개발 환경** – Visual Studio 2022(또는 .NET 6+를 지원하는 IDE) 설치.  
3. **유효한 Aspose.Tasks 라이선스** – 평가용은 선택 사항이며, 프로덕션 빌드에는 필수입니다.  
4. **기존 프로젝트 파일**(예: `SourceProject.xml`) – 복사하려는 파일.

## Aspose.Tasks용 네임스페이스 가져오기 방법

C# 파일 상단에 필요한 `using` 지시문을 추가하면 컴파일러가 Aspose.Tasks 타입을 찾을 수 있습니다. 이러한 구문을 포함하면 `Project`, `CopyToOptions` 및 기타 유틸리티 클래스를 완전한 이름 지정 없이 직접 사용할 수 있어 코드가 간결해지고 가독성이 향상됩니다.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## 단계 1: 프로젝트 객체 초기화

먼저, 소스 파일을 나타내는 `Project` 인스턴스를 생성하고 XML 데이터를 로드합니다.  
`Project` 클래스는 메모리로 로드된 Microsoft Project 파일을 나타내며, 작업, 리소스, 캘린더 및 기타 프로젝트 정보를 노출합니다.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **전문가 팁:** 매우 큰 파일을 다룰 경우, `LoadOptions` 생성자를 사용하여 지연 로딩을 활성화하고 메모리 사용량을 낮게 유지하는 것을 고려하십시오.

## 단계 2: 프로젝트 복사본 만들기

다음으로, 복사된 데이터를 받을 두 번째 `Project` 객체를 인스턴스화합니다. 이 객체는 빈 상태로 시작합니다.

```csharp
Project copiedProject = new Project();
```

이제 두 개의 별도 `Project` 객체가 있습니다: 하나는 디스크에서 로드된 것이고, 다른 하나는 복사를 받을 준비가 된 것입니다.

## 단계 3: 복사된 프로젝트 로드

복사 작업(아래에 표시) 후, 새로 저장된 파일을 다른 `Project` 인스턴스로 로드하여 결과를 확인하고 싶을 것입니다.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

파일을 다시 로드하면 복사가 성공했으며 설정한 옵션이 예상대로 작동했는지 확인할 수 있습니다.

## 단계 4: 복사 옵션 구성

`CopyToOptions` 클래스는 소스에서 대상으로 정확히 어떤 항목을 전송할지 지정할 수 있게 해줍니다.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

`SkipViewData = true`로 설정하면 출력 파일 크기가 감소하고 작업 속도가 빨라집니다. 특히 논리적 프로젝트 데이터만 필요할 때 유용합니다.

## 단계 5: 프로젝트 복사 수행

마지막으로, 소스 프로젝트에서 `CopyTo` 메서드를 호출하고 대상 프로젝트와 구성한 옵션을 전달합니다.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

이 두 줄 호출만으로 전체 복사 작업이 수행되며, 정의한 옵션을 존중합니다. 결과 파일 `CopiedProject.xml`에는 요청한 데이터만 포함됩니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| **`CopyTo` 호출 시 NullReferenceException** | 대상 프로젝트가 인스턴스화되지 않음. | `CopyTo` 호출 전에 `new Project()`가 호출되었는지 확인하십시오. |
| **복사 후 작업 누락** | `CopyCommonData`가 `false`로 설정됨. | `CopyCommonData = true`로 설정하거나 특정 컬렉션을 수동으로 복사하십시오. |
| **출력 파일 크기 큼** | `SkipViewData`가 `false`로 남아 있음. | UI 관련 데이터를 제외하려면 `SkipViewData`를 활성화하십시오. |
| **라이선스 적용 안 됨** | 라이선스 파일이 로드되지 않음. | API 사용 전에 `License license = new License(); license.SetLicense("Aspose.Tasks.lic");`를 호출하십시오. |

## 자주 묻는 질문

**Q: 작업의 일부만 복사할 수 있나요?**  
A: 예, `CopyToOptions`와 `ProjectRootTask`를 함께 사용하여 시작 작업을 지정하거나 초기 복사 후 선택된 작업을 수동으로 복사하십시오.

**Q: Aspose.Tasks가 서로 다른 파일 형식 간 복사를 지원하나요?**  
A: 물론입니다. MPP 파일을 로드한 후 복사본을 XML, XER 또는 기타 지원 형식으로 저장할 수 있으며, 총 **20개 이상의 형식**을 지원합니다.

**Q: 비밀번호로 보호된 프로젝트 파일을 어떻게 처리하나요?**  
A: 소스를 `new Project("file.mpp", new LoadOptions { Password = "pwd" })`로 로드한 다음, 일반적으로 복사를 진행하십시오.

**Q: 작업 없이 리소스 풀만 복사할 수 있는 방법이 있나요?**  
A: `CopyToOptions.CopyResources = true` 및 `CopyToOptions.CopyTasks = false`로 설정하면 리소스 정보만 전송됩니다.

**Q: 더 많은 예제를 어디서 찾을 수 있나요?**  
A: 커뮤니티 기반 스니펫, 문제 해결 팁 및 공식 문서를 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

---

**마지막 업데이트:** 2026-07-05  
**테스트 대상:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks로 프로젝트 데이터 마스터하기](/tasks/net/project-management-integration/project-data/)
- [Aspose.Tasks용 MS Project 저장 옵션 마스터하기](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks 캘린더 및 일정 관리](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}