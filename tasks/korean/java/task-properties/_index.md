---
date: 2026-10-15
description: Aspose.Tasks를 사용하여 Java에서 작업을 생성하는 방법을 배웁니다. 작업 속성, 우선순위, 비용 등에 대한 포괄적인
  튜토리얼을 탐색하여 Java 프로젝트 관리 최적화에 도움을 줍니다.
keywords:
- how to create tasks
- Aspose.Tasks Java
- task properties Java
lastmod: 2026-10-15
linktitle: 작업 속성
og_description: Aspose.Tasks for Java를 사용하여 작업을 생성하는 방법을 배웁니다. 이 가이드는 작업 속성, 우선순위,
  비용 및 Java 프로젝트 관리 모범 사례를 다룹니다.
og_image_alt: Developer guide showing how to create tasks using Aspose.Tasks Java
  library
og_title: Aspose.Tasks for Java를 사용하여 작업 생성 – 작업 속성
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create tasks aspose java using Aspose.Tasks. Explore comprehensive
    tutorials on task properties, priorities, costs, and more to optimize your Java
    project management.
  headline: How to create tasks with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create tasks aspose java using Aspose.Tasks. Explore comprehensive
    tutorials on task properties, priorities, costs, and more to optimize your Java
    project management.
  name: How to create tasks with Aspose.Tasks for Java
  steps:
  - name: '**Create a new project** – start with an empty `Project` object or load
      an existing file.'
    text: '**Create a new project** – start with an empty `Project` object or load
      an existing file.'
  - name: '**Add a task** – instantiate `Task`, set `Name`, `Duration`, and any custom
      fields you need.'
    text: '**Add a task** – instantiate `Task`, set `Name`, `Duration`, and any custom
      fields you need.'
  - name: '**Configure task properties** – adjust priority, cost, or extended attributes
      as required.'
    text: '**Configure task properties** – adjust priority, cost, or extended attributes
      as required.'
  - name: '**Save the project** – write the updated schedule back to `.mpp`, `.xml`,
      or any supported format.'
    text: '**Save the project** – write the updated schedule back to `.mpp`, `.xml`,
      or any supported format.'
  type: HowTo
- questions:
  - answer: No. The Aspose.Tasks Java API includes full support for task priorities;
      you can set them directly on the `Task` object.
    question: Do I need a separate library to handle task priorities?
  - answer: Yes. Use `Project project = new Project("input.mpp");` modify tasks, then
      `project.save("output.mpp");`.
    question: Can I import an existing .mpp file, modify tasks, and save it back?
  - answer: Absolutely. Iterate over `project.getRootTask().getChildren()` and apply
      changes in a loop for bulk operations.
    question: Is it possible to batch‑update many tasks at once?
  - answer: Create an `ExtendedAttributeDefinition`, add it to the project, then assign
      values to each task via `task.getExtendedAttributes().add(...)`.
    question: How do I handle custom extended attributes?
  - answer: Any Aspose.Tasks version released after 2022 fully supports Java 11 and
      newer.
    question: What version of Aspose.Tasks is required for Java 11?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create tasks
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java를 사용하여 작업 생성하는 방법
url: /ko/java/task-properties/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 작업 속성

## 소개

`Aspose.Tasks`는 Microsoft Project 파일을 프로그래밍 방식으로 생성하고 조작할 수 있는 Java 라이브러리입니다. **how to create tasks** 접근 방식을 사용하면 Java 애플리케이션에서 직접 프로젝트 일정을 구축, 수정 및 미세 조정할 수 있어 각 작업 속성을 완벽히 제어할 수 있습니다. 이 튜토리얼은 작업 속성을 손쉽게 관리할 수 있도록 필수 개념, 실제 사용 사례 및 모범 사례 팁을 안내합니다.

**왜 중요한가:** Aspose.Tasks는 30개 이상의 파일 형식을 지원하며 전체 파일을 메모리에 로드하지 않고도 10,000개의 작업이 포함된 프로젝트를 처리할 수 있어 엔터프라이즈 규모 계획에 유연성과 성능을 제공합니다.

## 빠른 답변
- **“create tasks aspose java”가 무엇을 가능하게 하나요?** Aspose.Tasks Java 라이브러리를 사용하여 Microsoft Project 파일에서 작업 정보를 프로그래밍 방식으로 추가, 업데이트 및 읽을 수 있게 해줍니다.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있지만, 실제 운영을 위해서는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇입니까?** Aspose.Tasks는 Java 8 이상에서 작동합니다.  
- **샘플 코드가 있나요?** 예—아래 각 튜토리얼에 실행 가능한 예제가 포함되어 있습니다.  
- **MPP로 내보낼 수 있나요?** 물론입니다; 라이브러리는 기본 .mpp 파일을 읽고 쓸 수 있습니다.

## Aspose.Tasks for Java에서 작업을 만드는 방법은?

Aspose.Tasks for Java를 사용하여 작업을 만들려면 Project 객체를 초기화하고, Task 인스턴스를 생성한 뒤, 이름, 기간, 리소스와 같은 필수 속성을 할당하고, 작업을 프로젝트 계층에 연결한 후, 지원되는 형식으로 프로젝트를 저장하면 됩니다. 이 간단한 흐름은 새 프로젝트 파일과 기존 프로젝트 파일 모두에 적용됩니다.

`Project` 인스턴스를 로드하고, 새로운 `Task`를 인스턴스화한 뒤, 필요한 속성을 설정하고, 작업을 프로젝트 루트에 추가하고, 마지막으로 파일을 저장합니다. 이 네 단계 패턴이 **how to create tasks**의 핵심이며 모든 프로젝트 규모에 적용됩니다.

### 단계별 안내

1. **새 프로젝트 만들기** – 빈 `Project` 객체로 시작하거나 기존 파일을 로드합니다.  
2. **작업 추가** – `Task`를 인스턴스화하고 `Name`, `Duration` 및 필요한 사용자 정의 필드를 설정합니다.  
3. **작업 속성 구성** – 필요에 따라 우선순위, 비용 또는 확장 속성을 조정합니다.  
4. **프로젝트 저장** – 업데이트된 일정을 `.mpp`, `.xml` 또는 지원되는 형식으로 기록합니다.

> **팁:** 루프에서 많은 작업을 생성할 때 자동 저장(`project.setAutoSave(false)`)을 비활성화하고 루프가 끝난 후 한 번 `project.save(...)`를 호출하면 성능이 향상됩니다.

## “how to create tasks”란 무엇인가요?

“how to create tasks”라는 용어는 Aspose.Tasks Java API를 사용하여 Microsoft Project 파일에 새로운 작업 항목을 추가하는 데 필요한 프로그래밍 단계들을 설명합니다. 여기에는 객체 생성, 속성 할당, 계층 배치 및 저장이 포함되어 있어 개발자가 각 작업의 모든 속성을 세밀하게 제어할 수 있습니다.

## 작업 생성에 Aspose.Tasks를 사용하는 이유는?

Aspose.Tasks는 **정량적인 이점**을 제공합니다: 30개 이상의 파일 형식을 지원하고, 최대 10,000개의 작업이 포함된 프로젝트를 처리할 수 있으며, 일반 하드웨어에서 500개의 작업 일정도 2초 미만에 처리합니다. 이 라이브러리는 Microsoft Project를 설치할 필요 없이 작동하므로 자동화된 서버‑사이드 워크플로에 이상적입니다.

## 사전 요구 사항

- 개발 머신에 Java 8 이상이 설치되어 있어야 합니다.  
- `aspose-tasks` 종속성을 관리하기 위한 Maven 또는 Gradle.  
- 유효한 Aspose.Tasks 라이선스(평가용 체험판 사용 가능).

## Aspose.Tasks에서 작업에 확장 속성 추가

Aspose.Tasks Java를 사용하여 Microsoft Project 파일을 확장 속성으로 맞춤화하는 강력함을 탐색하세요. 프로젝트 관리 능력을 손쉽게 향상시킬 수 있습니다. [자세히 알아보기](./add-extended-attributes/).

## Aspose.Tasks에서 작업 진행률 변경

Aspose.Tasks를 활용한 Java 프로젝트 관리 강화: 이 단계별 튜토리얼에서 작업 진행률을 원활하게 수정하는 방법을 배워보세요. 지금 다운로드! [자세히 보기](./change-progress/).

## Aspose.Tasks에서 작업 만들기

Aspose.Tasks를 사용해 Java 프로젝트를 손쉽게 관리하세요: 작업, 하위 작업 등을 생성합니다. 원활한 프로젝트 관리를 위한 단계별 가이드를 따라보세요. [시작하기](./create-tasks/).

## Aspose.Tasks에서 중요 및 노력 기반 작업 관리

Aspose.Tasks로 Java 프로젝트에서 중요 및 노력 기반 작업을 손쉽게 관리하세요. 라이브러리를 다운로드하고 프로젝트 관리 능력을 향상시키세요. [지금 다운로드](./critical-effort-driven-tasks/).

## Aspose.Tasks에서 추정 및 마일스톤 작업 처리

Aspose.Tasks for Java를 활용한 효과적인 프로젝트 관리를 탐색하세요. 추정 작업 및 마일스톤 작업을 손쉽게 처리합니다. 지금 라이브러리를 다운로드하세요! [자세히 보기](./estimated-milestone-tasks/).

## Aspose.Tasks의 확장 작업 속성

Aspose.Tasks for Java에서 확장 작업 속성을 살펴보세요. 단계별 가이드, FAQ 및 지원이 제공됩니다. 오늘 프로젝트 관리를 최적화하세요! [자세히 알아보기](./extended-task-attributes/).

## Aspose.Tasks에서 작업 우선순위 처리

Aspose.Tasks for Java로 작업 우선순위를 손쉽게 마스터하세요. 원활한 처리를 위한 가이드를 따라보세요. 프로젝트 관리 역량을 높이세요! [우선순위 마스터](./handle-priorities/).

## Aspose.Tasks에서 작업 변동성 처리

Aspose.Tasks for Java를 사용해 프로젝트 작업 변동성을 관리하는 강력함을 탐색하세요. 원활한 통합과 효율적인 처리를 위한 포괄적인 가이드를 따라보세요. [자세히 알아보기](./handle-variances/).

## Aspose.Tasks에서 작업 기간 관리

Aspose.Tasks for Java를 탐색하고 작업 기간을 손쉽게 관리하는 방법을 배우세요. 효과적인 프로젝트 계획 및 실행을 위한 단계별 가이드를 따라보세요. [기간 관리](./manage-durations/).

## Aspose.Tasks에서 작업 비용 관리

Aspose.Tasks를 사용해 Java 애플리케이션에서 작업 비용을 관리하는 방법을 배우세요. 효과적인 프로젝트 비용 관리를 위한 단계별 가이드를 따라보세요. [비용 관리](./manage-task-cost/).

## Aspose.Tasks에서 작업 메모 관리

Aspose.Tasks for Java에서 작업 메모 관리 기능을 살펴보세요. 효율적인 Java 개발을 위한 단계별 가이드입니다. 지금 무료 체험판을 다운로드하세요! [메모 살펴보기](./task-notes/).

## Aspose.Tasks에서 작업 초과근무 관리

Aspose.Tasks for Java를 사용해 프로젝트 작업의 초과근무를 효율적으로 관리하세요. 추적 및 리소스 할당을 손쉽게 단순화합니다. [초과근무 관리](./overtimes-in-tasks/).

## Aspose.Tasks에서 상위 및 하위 작업 관리

Aspose.Tasks for Java로 프로젝트 관리 효율성을 높이세요. 상위 및 하위 작업을 단계별로 관리하는 방법을 배우세요. 지금 시작하세요! [자세히 알아보기](./parent-child-tasks/).

## Aspose.Tasks에서 작업 완료 비율 계산

Aspose.Tasks for Java를 탐색하고 프로젝트 진행 상황 추적을 간소화하세요. 효율적인 프로젝트 관리를 위해 작업 완료 비율을 손쉽게 계산합니다. [계산 살펴보기](./percentage-complete-calculations/).

## Aspose.Tasks에서 작업 일반 속성 읽기 및 쓰기

Aspose.Tasks for Java를 사용해 작업 속성을 손쉽게 관리하는 강력함을 살펴보세요. 단계별 가이드를 통해 쉽게 읽고 쓸 수 있습니다. [속성 읽기·쓰기](./read-write-general-properties/).

## Aspose.Tasks에서 작업 시트 렌더링

Aspose.Tasks for Java로 효율적인 프로젝트 관리를 구현하세요. 작업 시트를 원활하게 렌더링합니다. 포괄적인 가이드를 지금 확인하세요! [작업 시트 렌더링](./render-task-sheet/).

## Aspose.Tasks에서 작업 종료 날짜 분할

Aspose.Tasks for Java를 사용해 작업 종료 날짜를 손쉽게 분할하는 방법을 배우세요. 정확한 일정으로 프로젝트 관리를 향상시킵니다. [종료 날짜 분할](./split-task-finish-date/).

## Aspose.Tasks에서 작업 분할

Aspose.Tasks와 함께 Java에서 작업 관리를 마스터하세요! 프로젝트 일정을 최적화하기 위해 작업을 효율적으로 분할하는 방법을 배우세요. 지금 다운로드! [작업 분할](./split-tasks/).

## Aspose.Tasks에서 작업 중지 및 재개

Aspose.Tasks for Java의 강력함을 활용해 작업 중지 및 재개에 대한 단계별 가이드를 살펴보세요. 프로젝트 관리를 원활하게 향상시킵니다! [작업 중지·재개](./stop-resume-task/).

## Aspose.Tasks에서 작업 예산, 작업량 및 비용 관리

Aspose.Tasks를 사용해 Java 프로젝트에서 효율적인 예산 및 비용 관리를 구현하세요. 원활한 통합을 위한 단계별 가이드를 확인하세요. [관리 살펴보기](./task-budget-work-cost/).

## Aspose.Tasks에서 다양한 단위의 작업 기간

Aspose.Tasks를 활용해 Java 프로젝트에서 작업 기간 관리를 탐색하세요. 분, 일, 시간, 주, 월 단위로 기간을 정확히 계산하고 변환합니다. [기간 관리](./task-duration-different-units/).

## Aspose.Tasks에서 작업 및 캘린더

Aspose.Tasks for Java를 사용해 작업 및 캘린더를 효율적으로 관리하는 강력함을 탐색하세요. 원활한 프로젝트 관리 경험을 위해 지금 다운로드! [작업 및 캘린더 살펴보기](./tasks-and-calendars/).

## Aspose.Tasks에서 작업 시계열 데이터

Aspose.Tasks for Java를 탐색하고 작업 시계열 데이터 관리를 마스터하세요. 라이브러리를 다운로드하고 무료 체험판을 이용해 프로젝트 추적을 간소화하세요. [시계열 데이터 살펴보기](./task-timephased-data/).

## Aspose.Tasks에서 작업 데이터를 MPP 형식으로 업데이트

Aspose.Tasks for Java를 사용해 작업 데이터를 MPP 형식으로 업데이트하는 방법을 배우세요. 효율적인 프로젝트 관리를 위한 단계별 가이드를 따라보세요. [작업 데이터 업데이트](./update-task-data/).

## Aspose.Tasks에서 작업과 연관된 WBS

Aspose.Tasks for Java와 함께 WBS를 마스터하세요 - 작업 WBS 코드를 읽고 번호를 재지정하는 방법을 배우세요. 프로젝트 관리 효율성을 높이세요! [WBS 마스터](./wbs-associated-with-task/).

## 작업 속성 튜토리얼
### [Aspose.Tasks에서 작업에 확장 속성 추가](./add-extended-attributes/)
Aspose.Tasks Java를 사용해 Microsoft Project 파일을 확장 속성으로 맞춤화하는 강력함을 탐색하세요. 프로젝트 관리 능력을 손쉽게 향상시킬 수 있습니다.

### [Aspose.Tasks에서 작업 진행률 변경](./change-progress/)
Aspose.Tasks를 활용한 Java 프로젝트 관리 강화: 이 단계별 튜토리얼에서 작업 진행률을 원활하게 수정하는 방법을 배워보세요. 지금 다운로드!

### [Aspose.Tasks에서 작업 만들기](./create-tasks/)
Aspose.Tasks를 사용해 Java 프로젝트를 손쉽게 관리하세요: 작업, 하위 작업 등을 생성합니다. 원활한 프로젝트 관리를 위한 단계별 가이드를 따라보세요.

### [Aspose.Tasks에서 중요 및 노력 기반 작업 관리](./critical-effort-driven-tasks/)
Aspose.Tasks를 사용해 Java 프로젝트에서 중요 및 노력 기반 작업을 손쉽게 관리하세요. 라이브러리를 다운로드하고 프로젝트 관리 능력을 향상시키세요.

### [Aspose.Tasks에서 추정 및 마일스톤 작업 처리](./estimated-milestone-tasks/)
Aspose.Tasks for Java를 활용한 효과적인 프로젝트 관리를 탐색하세요. 추정 작업 및 마일스톤 작업을 손쉽게 처리합니다. 지금 라이브러리를 다운로드하세요!

### [Aspose.Tasks의 확장 작업 속성](./extended-task-attributes/)
Aspose.Tasks for Java에서 확장 작업 속성을 살펴보세요. 단계별 가이드, FAQ 및 지원이 제공됩니다. 오늘 프로젝트 관리를 최적화하세요!

### [Aspose.Tasks에서 작업 우선순위 처리](./handle-priorities/)
Aspose.Tasks for Java로 작업 우선순위를 손쉽게 마스터하세요. 원활한 처리를 위한 가이드를 따라보세요. 프로젝트 관리 역량을 높이세요!

### [Aspose.Tasks에서 작업 변동성 처리](./handle-variances/)
Aspose.Tasks for Java를 사용해 프로젝트 작업 변동성을 관리하는 강력함을 탐색하세요. 원활한 통합과 효율적인 처리를 위한 포괄적인 가이드를 따라보세요.

### [Aspose.Tasks에서 작업 기간 관리](./manage-durations/)
Aspose.Tasks for Java를 탐색하고 작업 기간을 손쉽게 관리하는 방법을 배우세요. 효과적인 프로젝트 계획 및 실행을 위한 단계별 가이드를 따라보세요.

### [Aspose.Tasks에서 작업 비용 관리](./manage-task-cost/)
Aspose.Tasks를 사용해 Java 애플리케이션에서 작업 비용을 관리하는 방법을 배우세요. 효과적인 프로젝트 비용 관리를 위한 단계별 가이드를 따라보세요.

### [Aspose.Tasks에서 작업 메모 관리](./task-notes/)
Aspose.Tasks for Java에서 작업 메모 관리 기능을 살펴보세요. 효율적인 Java 개발을 위한 단계별 가이드입니다. 지금 무료 체험판을 다운로드하세요!

### [Aspose.Tasks에서 작업 초과근무](./overtimes-in-tasks/)
Aspose.Tasks for Java를 사용해 프로젝트 작업의 초과근무를 효율적으로 관리하세요. 추적 및 리소스 할당을 손쉽게 단순화합니다.

### [Aspose.Tasks에서 상위 및 하위 작업 관리](./parent-child-tasks/)
Aspose.Tasks for Java로 프로젝트 관리 효율성을 높이세요. 상위 및 하위 작업을 단계별로 관리하는 방법을 배우세요. 지금 시작하세요!

### [Aspose.Tasks에서 작업 완료 비율 계산](./percentage-complete-calculations/)
Aspose.Tasks for Java를 탐색하고 프로젝트 진행 상황 추적을 간소화하세요. 효율적인 프로젝트 관리를 위해 작업 완료 비율을 손쉽게 계산합니다.

### [Aspose.Tasks에서 작업 일반 속성 읽기 및 쓰기](./read-write-general-properties/)
Aspose.Tasks for Java를 사용해 작업 속성을 손쉽게 관리하는 강력함을 살펴보세요. 단계별 가이드를 통해 쉽게 읽고 쓸 수 있습니다.

### [Aspose.Tasks에서 작업 시트 렌더링](./render-task-sheet/)
Aspose.Tasks for Java로 효율적인 프로젝트 관리를 구현하세요. 작업 시트를 원활하게 렌더링합니다. 포괄적인 가이드를 지금 확인하세요!

### [Aspose.Tasks에서 작업 종료 날짜 분할](./split-task-finish-date/)
Aspose.Tasks for Java를 사용해 작업 종료 날짜를 손쉽게 분할하는 방법을 배우세요. 정확한 일정으로 프로젝트 관리를 향상시킵니다.

### [Aspose.Tasks에서 작업 분할](./split-tasks/)
Aspose.Tasks와 함께 Java에서 작업 관리를 마스터하세요! 프로젝트 일정을 최적화하기 위해 작업을 효율적으로 분할하는 방법을 배우세요. 지금 다운로드!

### [Aspose.Tasks에서 작업 중지 및 재개](./stop-resume-task/)
Aspose.Tasks for Java의 강력함을 활용해 작업 중지 및 재개에 대한 단계별 가이드를 살펴보세요. 프로젝트 관리를 원활하게 향상시킵니다!

### [Aspose.Tasks에서 작업 예산, 작업량 및 비용 관리](./task-budget-work-cost/)
Aspose.Tasks를 사용해 Java 프로젝트에서 효율적인 예산 및 비용 관리를 구현하세요. 원활한 통합을 위한 단계별 가이드를 확인하세요.

### [Aspose.Tasks에서 다양한 단위의 작업 기간](./task-duration-different-units/)
Aspose.Tasks를 활용해 Java 프로젝트에서 작업 기간 관리를 탐색하세요. 분, 일, 시간, 주, 월 단위로 기간을 정확히 계산하고 변환합니다.

### [Aspose.Tasks에서 작업 및 캘린더](./tasks-and-calendars/)
Aspose.Tasks for Java를 사용해 작업 및 캘린더를 효율적으로 관리하는 강력함을 탐색하세요. 원활한 프로젝트 관리 경험을 위해 지금 다운로드!

### [Aspose.Tasks에서 작업 시계열 데이터](./task-timephased-data/)
Aspose.Tasks for Java를 탐색하고 작업 시계열 데이터 관리를 마스터하세요. 라이브러리를 다운로드하고 무료 체험판을 이용해 프로젝트 추적을 간소화하세요.

### [Aspose.Tasks에서 작업 데이터를 MPP 형식으로 업데이트](./update-task-data/)
Aspose.Tasks for Java를 사용해 작업 데이터를 MPP 형식으로 업데이트하는 방법을 배우세요. 효율적인 프로젝트 관리를 위한 단계별 가이드를 따라보세요.

### [Aspose.Tasks에서 작업과 연관된 WBS](./wbs-associated-with-task/)
Aspose.Tasks for Java와 함께 WBS를 마스터하세요 - 작업 WBS 코드를 읽고 번호를 재지정하는 방법을 배우세요. 프로젝트 관리 효율성을 높이세요!

## 자주 묻는 질문

**Q: 작업 우선순위를 처리하기 위해 별도의 라이브러리가 필요합니까?**  
A: 아닙니다. Aspose.Tasks Java API는 작업 우선순위에 대한 전체 지원을 포함하고 있어 `Task` 객체에 직접 설정할 수 있습니다.

**Q: 기존 .mpp 파일을 가져와 작업을 수정하고 다시 저장할 수 있나요?**  
A: 예. `Project project = new Project("input.mpp");` 로 파일을 로드하고 작업을 수정한 뒤 `project.save("output.mpp");` 로 저장하면 됩니다.

**Q: 여러 작업을 한 번에 일괄 업데이트할 수 있나요?**  
A: 물론입니다. `project.getRootTask().getChildren()` 를 반복하면서 루프 내에서 변경을 적용하면 일괄 작업을 수행할 수 있습니다.

**Q: 사용자 정의 확장 속성을 어떻게 처리하나요?**  
A: `ExtendedAttributeDefinition` 을 생성하고 프로젝트에 추가한 뒤, `task.getExtendedAttributes().add(...)` 로 각 작업에 값을 할당합니다.

**Q: Java 11에 필요한 Aspose.Tasks 버전은 무엇인가요?**  
A: 2022년 이후에 출시된 모든 Aspose.Tasks 버전은 Java 11 이상을 완전히 지원합니다.

**마지막 업데이트:** 2026-10-15  
**테스트 환경:** Aspose.Tasks 24.11 for Java  
**작성자:** Aspose

## 관련 튜토리얼

- [프로젝트 만들기 – 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks for Java로 작업 우선순위 읽기 및 설정](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}