---
date: 2026-01-25
description: Aspose.Tasks for Java에서 작업을 생성하는 방법을 배우세요. 프로젝트를 관리하고, 요약 작업을 만들며, 문서
  디렉터리를 설정하는 등 이 단계별 가이드를 통해 다양한 기능을 활용할 수 있습니다.
linktitle: Create Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 작업 생성 방법
url: /ko/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 만들기

## Introduction
환영합니다! 이 튜토리얼에서는 **작업 만들기** 방법을 Aspose.Tasks for Java에서 문서 디렉터리 설정부터 요약 작업 및 하위 작업 추가까지 단계별로 알아봅니다. 간단한 할 일 목록을 만들든 전체 프로젝트 일정표를 만들든, 아래 단계는 프로젝트 계층 구조를 빠르게 구축하고 실행할 수 있는 명확하고 실용적인 방법을 제공합니다.

## Quick Answers
- **주된 목적은 무엇인가요?** Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에 작업을 프로그래밍 방식으로 생성하고 구성하기 위함입니다.  
- **필요한 라이브러리 버전은?** 최신 Aspose.Tasks for Java 릴리스라면 어느 버전이든 사용 가능하며, API는 버전 간에 안정적입니다.  
- **라이선스가 필요한가요?** 평가용 임시 라이선스로도 사용 가능하지만, 실제 운영 환경에서는 정식 라이선스가 필요합니다.  
- **요약 작업을 만들 수 있나요?** 예 – 루트 작업의 children 컬렉션에서 `add` 메서드를 사용하면 됩니다.  
- **파일은 어디에 저장되나요?** *set document directory* 단계에서 지정한 디렉터리에 저장됩니다.

## What is “how to create tasks” in Aspose.Tasks?
작업 만들기는 `Project` 인스턴스에 `Task` 객체를 프로그래밍 방식으로 추가하고, 계층 구조(요약 작업, 하위 작업)를 정의한 뒤 이를 MPP 파일로 저장하는 과정을 의미합니다. 이를 통해 자동화된 프로젝트 생성, 대량 업데이트 및 다른 시스템과의 연동이 가능해집니다.

## Why use Aspose.Tasks for Java?
- **Full control** over project data without needing Microsoft Project installed.  
- **Cross‑platform** compatibility – works on Windows, Linux, and macOS.  
- **Rich API** for task attributes, resources, calendars, and more.  
- **Scalable** – suitable for small utilities or enterprise‑level scheduling engines.

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- **Java Development Kit (JDK)** 가 머신에 설치되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리를 [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
- **Eclipse** 또는 **IntelliJ IDEA** 와 같은 IDE를 사용해 Java 코드를 작성하고 실행합니다.

## Import Packages
Java 소스 파일 상단에 필요한 Aspose.Tasks 클래스를 추가합니다:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Step 1: Set the Document Directory
프로젝트 파일을 읽거나 쓸 폴더를 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

*이 단계는 **set document directory** 요구사항을 충족시키며, API에 MPP 파일 위치를 명확히 알려줍니다.*

## Step 2: Create a New Project
기존 MPP 파일을 로드하거나 빈 템플릿에서 시작하여 `Project` 객체를 인스턴스화합니다.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

## Step 3: Add a Summary Task
요약 작업은 관련 하위 작업을 그룹화합니다. 여기서는 **summary task** “Summary1”을 생성합니다.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

## Step 4: Add a Subtask
이제 요약 작업 아래에 하위 작업을 추가하여 계층 구조를 구축합니다.

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

필요에 따라 추가 작업 및  
-(dataDir + "updated_project.mpp");`를 호출하여 변경 사항을 저장합니다.

## Frequently Asked Questions

### Is Aspose.Tasks suitable for small‑scale projects?
Absolutely! The API scales from simple task lists to massive enterprise schedules.

### Where can I find detailed documentation for Aspose.Tasks for Java?
Refer to the documentation [here](https://reference.aspose.com/tasks/java/).

### How do I obtain a temporary license for Aspose.Tasks?
Visit [this link](https://purchase.aspose.com/temporary-license/) for a trial license that works for evaluation.

### Can I customize task attributes using Aspose.Tasks?
Yes, you can set start dates, durations, resources, custom fields, and many other properties on each `Task` object.

### Is there a support community for Aspose.Tasks users?
Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

---