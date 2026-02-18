---
date: 2026-02-18
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 그룹 정의 데이터를 읽는 방법을
  배웁니다. 이 튜토리얼에서는 그룹 세부 정보를 읽고 작업 그룹화 정보를 추출하는 방법을 보여줍니다.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 그룹 정의 데이터 읽는 방법
url: /ko/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 그룹 정의 데이터 읽기

## Introduction
Aspose.Tasks for Java은 개발자가 Microsoft Project 파일을 손쉽게 조작할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 **그룹 정의 데이터를 읽는 방법**을 단계별로 배워서 Java 애플리케이션에서 작업 그룹 정보를 추출하고 활용할 수 있게 됩니다. **그룹을 읽는 방법**을 이해하면 보고서를 자동화하고, 설정을 마이그레이션하며, 프로젝트 구조를 프로그래밍 방식으로 검증할 수 있습니다.

## Quick Answers
- **“read group definition”이란 무엇인가요?** Microsoft Project 파일에서 작업 그룹(이름, 기준, 서식)의 정의를 추출하는 것을 의미합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java.  
- **라이선스가 필요한가요?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 IDE는?** IntelliJ IDEA, Eclipse 등 모든 Java IDE.  
- **필요한 코드 양은?** 프로젝트를 로드하고 그룹 상세 정보를 표시하는 데 30줄 미만의 Java 코드면 충분합니다.

## How to Read Group Definition Data
아래는 `.mpp` 파일에서 **그룹 정보를 읽는** 방법을 간결하게 단계별로 안내하는 예시입니다. 각 단계마다 짧은 설명과 실행에 필요한 정확한 코드를 제공합니다.

## What is read group definition?
Microsoft Project에서 *그룹 정의*는 작업을 특정 기준(예: 상태, 우선순위)으로 묶는 방식을 설명합니다. 이 정의를 읽으면 프로젝트 파일에 적용된 그룹화 논리, 색상, 글꼴 및 정렬 순서를 프로그래밍적으로 확인할 수 있습니다.

## Why read group definition data?
- **Automation:** Project에서 보는 그룹과 동일한 맞춤형 보고서를 생성합니다.  
- **Migration:** 그룹 규칙을 다른 프로젝트나 다른 프로젝트 관리 시스템으로 이동합니다.  
- **Validation:** 대량 업데이트를 실행하기 전에 예상된 그룹이 존재하는지 확인합니다.  
- **Customization:** 그룹의 글꼴이나 색상 설정을 기반으로 추가 비즈니스 로직을 적용합니다.  
- **Insight:** **그룹을 읽는 방법**을 알면 예기치 않은 작업 레이아웃을 문제 해결하는 데 도움이 됩니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하세요.

1. **Java Development Kit (JDK)** – 최신 버전(8 이상).  
2. **Aspose.Tasks for Java Library** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 편집기.  

## Import Packages
먼저 Aspose.Tasks 핵심 패키지를 임포트합니다:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Data Directory
`.mpp` 파일이 들어 있는 폴더를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 프로젝트 파일이 위치한 절대 경로로 교체하세요.

### Step 2: Load the Project File
`.mpp` 파일을 가리키는 `Project` 인스턴스를 생성합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Task Groups Count
프로젝트에 정의된 작업 그룹의 총 개수를 출력합니다.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Step 4: Retrieve Specific Task Group Information
예시에서는 인덱스 1에 해당하는 특정 그룹을 가져와 이름과 포함된 기준 수를 표시합니다.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Step 5: Retrieve Group Criterion Information
각 그룹은 하나 이상의 기준을 가질 수 있습니다. 아래 스니펫은 그룹화에 사용된 필드, 그룹 모드, 셀 색상 및 패턴 등 상세 정보를 추출합니다.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Step 6: Check Parent Group
때때로 기준이 상위 그룹에 속합니다. 이 단계에서는 해당 관계를 확인합니다.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Step 7: Retrieve Criterion's Font Information
그룹 기준은 사용자 지정 글꼴 스타일을 가질 수 있습니다. 다음 코드는 글꼴 패밀리, 크기, 스타일 및 정렬 방향을 출력합니다.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | 기준에 상위 그룹이 없을 수 있습니다. | 비교하기 전에 null‑check를 추가하세요. |
| **File not found** | `dataDir` 경로가 올바르지 않습니다. | `Paths.get(dataDir, "project.mpp").toAbsolutePath()` 로 경로를 확인하세요. |
| **License not set** | Aspose 라이브러리가 평가 모드로 실행되어 출력이 제한될 수 있습니다. | `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 라이선스를 등록하세요. |

## Frequently Asked Questions

**Q: Aspose.Tasks for Java를 사용해 프로젝트 파일을 수정할 수 있나요?**  
A: 네, 이 라이브러리는 Microsoft Project 파일에 대한 완전한 읽기/쓰기 기능을 제공합니다.

**Q: Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환되나요?**  
A: MPP, XML 등 다양한 일반 Project 형식을 여러 버전에 걸쳐 지원합니다.

**Q: Aspose.Tasks for Java 사용 중 오류를 어떻게 처리하나요?**  
A: 파일 작업을 `try‑catch` 블록으로 감싸고 `TasksException`을 검사해 상세 메시지를 확인하세요.

**Q: Aspose.Tasks for Java가 프로젝트 데이터를 다른 형식으로 내보내는 기능을 제공하나요?**  
A: 물론입니다 – 라이브러리의 내보내기 API를 사용해 PDF, XLSX, CSV 등으로 변환할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 추가 자료와 지원은 어디서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)에서, 커뮤니티 지원은 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

## Conclusion
이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 Microsoft Project 파일에서 **그룹 정의 데이터를 읽는** 방법을 단계별로 살펴보았습니다. 위 절차를 따르면 그룹 이름, 기준, 서식 및 상위 그룹 관계를 추출할 수 있어, 맞춤형 보고서 작성, 설정 마이그레이션 또는 Java 애플리케이션에서의 자동 검증 로직 구현에 활용할 수 있습니다.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}