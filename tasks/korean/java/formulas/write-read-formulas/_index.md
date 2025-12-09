---
date: 2025-12-07
description: Aspose.Tasks for Java를 사용하여 프로젝트 파일을 저장하고, MS Project 수식을 작성·읽으며, 사용자
  정의 필드 수식을 추가하는 방법을 배우세요.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks로 프로젝트 파일 저장 및 MS Project 수식 작성
url: /ko/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 파일 저장 및 Aspose.Tasks를 사용한 MS Project 수식 작성

## Introduction
프로젝트 관리 영역에서 데이터의 효율적인 처리는 매우 중요합니다. Aspose.Tasks for Java는 Microsoft Project 파일에서 데이터를 조작하고 추출할 수 있는 강력한 솔루션입니다. 이 라이브러리가 제공하는 강력한 기능 중 하나는 MS Project 수식을 **작성하고 읽는** 기능입니다. **수식을 적용한 후 프로젝트 파일을 *저장*하는 방법**도 배워서 변경 사항이 향후 분석을 위해 지속되도록 할 수 있습니다. 이 튜토리얼에서는 이 기능을 활용하여 프로젝트 관리 작업을 향상시키는 방법을 단계별로 안내합니다.

## Quick Answers
- **“프로젝트 파일 저장”은 무엇을 하나요?** 메모리 상의 모든 변경 사항을 디스크에 있는 .mpp 파일로 다시 씁니다.  
- **사용자 정의 필드 수식을 추가할 수 있나요?** 예 – “작업 비용을 두 배로”와 같은 수식을 가진 사용자 정의 필드를 만들 수 있습니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 평가용 무료 체험판으로도 가능하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **어떤 IDE가 가장 적합한가요?** IntelliJ IDEA, Eclipse, VS Code 등 모든 Java IDE에서 샘플을 컴파일할 수 있습니다.  
- **API가 최신 MS Project 버전과 호환되나요?** Aspose.Tasks는 최신 .mpp 형식을 모두 지원합니다.

## What is “save project file” in Aspose.Tasks?
프로젝트 파일을 저장한다는 것은 `Project` 객체의 현재 상태—작업, 리소스 및 모든 사용자 정의 수식—를 실제 Microsoft Project 파일(`.mpp`)에 영구적으로 기록하는 것을 의미합니다. 이 작업은 사용자 정의 필드를 추가하거나 작업 비용을 변경하는 등 데이터를 수정한 후 반드시 수행해야 합니다.

## Why add a custom field and create a custom field formula?
사용자 정의 필드를 추가하면 기본 필드로는 표현할 수 없는 추가 정보를 유연하게 저장할 수 있습니다. **작업 비용을 두 배로**와 같은 수식을 연결하면 계산을 자동화하고 수동 오류를 줄이며 일정 데이터의 일관성을 유지할 수 있습니다.

## Prerequisites
튜토리얼을 진행하기 전에 다음 사전 조건을 확인하세요:

1. **Java Development Kit (JDK)** – Java 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드 및 설치합니다.  
3. **Integrated Development Environment (IDE)** – Java 개발에 선호하는 IDE를 선택하세요 (IntelliJ IDEA, Eclipse, VS Code 등).  

## Importing Packages
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Step 1: Set Up Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
MS Project 파일이 위치할 폴더를 정의합니다. 여기에서 원본 파일을 로드하고 이후 **프로젝트 파일을 저장**하게 됩니다.

## Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
기존 Microsoft Project 파일을 `Project` 객체로 로드하여 내용을 읽거나 수정할 수 있습니다.

## Step 3: Add Custom Field and Create Custom Field Formula
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
이 단계에서는 **사용자 정의 필드** “Double Costs” 를 추가하고, 작업의 `[Cost]` 를 2배로 곱하는 **사용자 정의 필드 수식**을 생성합니다. `setFormula` 메서드는 계산식을 프로젝트 파일에 직접 삽입합니다.

## Step 4: Add Task and Set Cost
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
새 작업을 만든 뒤 기본 비용을 `100`으로 설정합니다. 프로젝트를 저장하면 앞서 정의한 수식에 의해 사용자 정의 필드에 `200`이 자동으로 표시됩니다.

## Step 5: Save Project File
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
마지막으로 모든 수정 사항을 포함해 **프로젝트 파일을 저장**합니다. `save` 메서드는 새 사용자 정의 필드와 계산된 값을 `saved.mpp` 파일에 기록합니다.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Formula not applied** | Custom field not added to the project’s `ExtendedAttributes` collection. | Ensure `project.getExtendedAttributes().add(attr);` is executed before saving. |
| **File not found** | Incorrect `dataDir` path. | Verify the directory string ends with a path separator (`/` or `\\`). |
| **Cost appears as 0** | Task cost not set before saving. | Call `task.set(Tsk.COST, ...)` before `project.save`. |

## Frequently Asked Questions
**Q: Aspose.Tasks가 모든 버전의 MS Project와 호환되나요?**  
A: 예, Aspose.Tasks는 오래된 .mpp 형식부터 최신 릴리스까지 다양한 MS Project 버전을 지원합니다.

**Q: 기존 Java 프로젝트에 Aspose.Tasks를 통합할 수 있나요?**  
A: 물론입니다. API는 원활한 통합을 위해 설계되었으며, Aspose.Tasks JAR 파일을 프로젝트 클래스패스에 추가하기만 하면 됩니다.

**Q: 만들 수 있는 수식 종류에 제한이 있나요?**  
A: 라이브러리는 산술, 논리 및 내장 함수 등을 포함한 대부분의 기본 MS Project 수식 구문을 지원합니다. 복잡한 사용자 정의 함수는 우회 방법이 필요할 수 있습니다.

**Q: Aspose.Tasks가 다중 플랫폼 배포를 지원하나요?**  
A: 예, Java를 지원하는 모든 플랫폼—Windows, Linux, macOS—에서 라이브러리를 사용할 수 있습니다.

**Q: Aspose.Tasks에 대한 기술 지원은 어떻게 받나요?**  
A: 커뮤니티 도움을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하거나, 상업용 라이선스를 보유하고 있다면 지원 티켓을 열 수 있습니다.

## Conclusion
이 튜토리얼에서는 **프로젝트 파일 저장**, **사용자 정의 필드 추가**, 그리고 **작업 비용을 두 배로** 만드는 **사용자 정의 필드 수식**을 Aspose.Tasks for Java를 사용해 구현하는 방법을 다루었습니다. 이 단계를 따르면 계산을 자동화하고 프로젝트 데이터를 풍부하게 만들며, 모든 변경 사항을 향후 보고 및 분석을 위해 지속적으로 저장할 수 있습니다.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}