---
date: 2025-12-11
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 그룹 정의 데이터를 읽는 방법을
  배우세요. 단계별 튜토리얼을 따라해 보세요.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 그룹 정의 데이터 읽기
url: /ko/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 그룹 정의 데이터 읽기

## Introduction
Aspose.Tasks for Java은 개발자가 Microsoft Project 파일을 손쉽게 조작할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 **그룹 정의** 데이터를 단계별로 읽는 방법을 배우게 되며, 이를 통해 Java 애플리케이션에서 작업 그룹 정보를 추출하고 활용할 수 있습니다.

## Quick Answers
- **“read group definition”이 무엇을 의미하나요?** Microsoft Project 파일에서 작업 그룹(이름, 기준, 서식)의 정의를 추출하는 것을 의미합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 IDE는 무엇인가요?** IntelliJ IDEA 또는 Eclipse와 같은 모든 Java IDE.  
- **필요한 코드 양은 얼마인가요?** 프로젝트를 로드하고 그룹 세부 정보를 표시하는 데 30줄 미만의 Java 코드가 필요합니다.

## What is read group definition?
Microsoft Project에서 *그룹 정의*는 작업을 기준(예: 상태, 우선순위)에 따라 함께 묶는 방식을 설명합니다. 이 정의를 읽으면 프로젝트 파일에 적용된 그룹화 논리, 색상, 글꼴 및 정렬서를 프로그래밍 방식으로 확인할 수 있습니다.

## Why read group definition data?
- **자동화:** Project에서 보는 그룹화를 반영하는 맞춤형 보고서를 생성합니다.  
- **마이그레이션:** 그룹화 규칙을 다른 프로젝트나 다른 프로젝트 관리 시스템으로 이동합니다.  
- **검증:** 대량 업데이트를 실행하기 전에 예상된 그룹이 존재하는지 확인합니다.  
- **맞춤화:** 그룹의 글꼴이나 색상 설정을 기반으로 추가 비즈니스 로직을 적용합니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK)** – 최신 버전(8 이상) 중 하나.  
2. **Aspose.Tasks for Java Library** – [here](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 편집기.

## Import Packages
First, import the core Aspose.Tasks package:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Data Directory
Define the folder that contains the `.mpp` file you want to inspect.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path to your project file location.

### Step 2: Load the Project File
Create a `Project` instance by pointing it to your `.mpp` file.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Task Groups Count
Print the total number of task groups defined in the project.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Step 4: Retrieve Specific Task Group Information
Grab a particular group (index 1 in this example) and display its name and the number of criteria it contains.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Step 5: Retrieve Group Criterion Information
Each group can have one or more criteria. The snippet below extracts details such as the field used for grouping, the grouping mode, cell color, and pattern.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Step 6: Check Parent Group
Sometimes a criterion belongs to a parent group. This check confirms the relationship.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Step 7: Retrieve Criterion's Font Information
Group criteria can have custom font styling. The following code prints the font family, size, style, and sorting direction.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`criterion.getParentGroup()`에서 NullPointerException** | 해당 기준에 부모 그룹이 없을 수 있습니다. | 비교하기 전에 null 체크를 추가하십시오. |
| **파일을 찾을 수 없음** | `dataDir` 경로가 올바르지 않습니다. | `Paths.get(dataDir, "project.mpp").toAbsolutePath()`를 사용하여 확인하십시오. |
| **라이선스가 설정되지 않음** | Aspose 라이브러리가 평가 모드로 실행되어 출력이 제한될 수 있습니다. | `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 라이선스를 등록하십시오. |

## Frequently Asked Questions

**Q: Aspose.Tasks for Java를 사용하여 프로젝트 파일을 수정할 수 있나요?**  
A: 네, 이 라이브러리는 Microsoft Project 파일에 대한 완전한 읽기/쓰기 기능을 제공합니다.

**Q: Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환되나요?**  
A: MPP, XML 및 기타 일반적인 Project 형식을 여러 버전에서 지원합니다.

**Q: Aspose.Tasks for Java를 사용할 때 오류를 어떻게 처리할 수 있나요?**  
A: 파일 작업을 `try‑catch` 블록으로 감싸고 `TasksException`을 검사하여 자세한 메시지를 확인하십시오.

**Q: Aspose.Tasks for Java가 프로젝트 데이터를 다른 형식으로 내보내는 기능을 제공하나요?**  
A: 물론입니다 – 라이브러리의 내보내기 API를 사용하여 PDF, XLSX, CSV 등으로 내보낼 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 추가 리소스와 지원을 어디서 찾을 수 있나요?**  
A: 전체 API 레퍼런스를 보려면 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)을 방문하고, 커뮤니티 도움을 받으려면 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)을 이용하십시오.

## Conclusion
In this tutorial we walked through how to **read group definition** data from a Microsoft Project file using Aspose.Tasks for Java. By following the steps above you can extract group names, criteria, formatting, and parent‑group relationships, empowering you to build custom reports, migrate settings, or automate validation logic in your Java applications.

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}