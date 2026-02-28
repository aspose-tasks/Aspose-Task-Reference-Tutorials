---
date: 2026-02-28
description: Aspose.Tasks for Java를 사용하여 프로젝트에 작업을 추가하고 Java용 작업 캘린더를 생성하는 방법을 배우세요
  – 프로젝트 관리에 강력한 라이브러리입니다.
linktitle: Tasks and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java로 프로젝트에 작업을 추가하고 캘린더를 관리하기
url: /ko/java/task-properties/tasks-and-calendars/
weight: 33
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 프로젝트에 작업 추가 및 캘린더 관리

## Introduction
프로젝트에 **작업을 추가**하고 일정이 완벽하게 정렬되도록 준비되셨나요? 이 가이드에서는 작업을 생성하고, 사용자 정의 캘린더에 연결하며, 업계 최고의 **java project management library**인 Aspose.Tasks를 활용하는 필수 단계를 안내합니다. 끝까지 읽으면 **create task calendar java**‑style로 프로젝트 일정에 대한 세밀한 제어를 할 수 있게 됩니다.

## Quick Answers
- **주요 목적은 무엇인가요?** 프로젝트에 작업을 추가하고 사용자 정의 캘린더와 연결합니다.  
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Tasks for Java – 전체 기능을 갖춘 project‑management API.  
- **라이선스가 필요합니까?** 무료 체험판을 이용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **필요한 JDK 버전은?** Java 8 이상.  
- **구현 소요 시간은?** 기본 시나리오의 경우 일반적으로 15 분 미만.

## What is “add task to project”?
프로젝트에 작업을 추가한다는 것은 `Project` 객체 내부에 작업 항목을 생성하고 해당 속성(기간, 시작 날짜, 캘린더 등)을 정의하는 것을 의미합니다. 이 작업은 일정 중심 애플리케이션의 기본 빌딩 블록입니다.

## Why use a Java project management library?
Aspose.Tasks와 같은 전용 라이브러리는 복잡한 MS‑Project 파일 형식, 리소스 레벨링 및 캘린더 계산을 자동으로 처리해 줍니다. 이를 통해 휠을 다시 만들 필요가 없으며, 업계 표준 도구와의 호환성을 보장합니다.

## Prerequisites
튜토리얼을 시작하기 전에 다음 전제 조건을 확인하세요:
- Java Development Kit (JDK): 시스템에 Java가 설치되어 있는지 확인합니다.
- Aspose.Tasks Library: Aspose.Tasks 라이브러리를 다운로드하여 프로젝트에 포함합니다. 라이브러리는 [here](https://releases.aspose.com/tasks/java/)에서 찾을 수 있습니다.

## Import Packages
Java 프로젝트에서 Aspose.Tasks에 필요한 패키지를 가져옵니다:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
새 Java 프로젝트를 생성하고 Aspose.Tasks JAR 파일을 빌드 경로에 추가합니다. 이렇게 하면 전체 API에 접근할 수 있습니다.

## Step 2: How to add task to project
새 `Project` 인스턴스를 만들고 **Task1**이라는 루트‑레벨 작업을 추가합니다. 이는 핵심 “add task to project” 작업을 보여줍니다.

```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```

## Step 3: How to create task calendar java
프로젝트에 표준 캘린더를 추가합니다. 캘린더는 작업일, 휴일 및 기타 일정 규칙을 정의합니다.

```java
Calendar cal = project.getCalendars().add("TaskCal1");
```

## Step 4: Associate Task with Calendar
앞서 만든 작업을 새 캘린더와 연결하여 작업 일정이 캘린더의 근무 시간을 따르도록 합니다.

```java
tsk.set(Tsk.CALENDAR, cal);
```

*Tip:* 필요한 각 추가 작업 및 캘린더에 대해 이 단계를 반복하세요. `Calendar` API를 사용하여 캘린더 예외(예: 비근무일)도 맞춤 설정할 수 있습니다.

## Common Issues and Solutions
- **작업이 캘린더 변경을 반영하지 않음:** 캘린더를 수정한 후 `project.updateStructure()`를 호출했는지 확인하세요.  
- **`set` 호출 시 NullPointerException:** 작업에 캘린더를 할당하기 전에 캘린더가 프로젝트에 정상적으로 추가되었는지 확인합니다.  
- **가져오기/내보내기 후 날짜가 올바르지 않음:** `project.save("output.mpp")`로 저장한 뒤 다시 열어 데이터가 유지되는지 확인합니다.

## Frequently Asked Questions
### Aspose.Tasks for Java를 어떻게 다운로드하나요?
라이브러리는 [this link](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

### Aspose.Tasks 문서는 어디서 찾을 수 있나요?
문서는 [here](https://reference.aspose.com/tasks/java/)에서 확인하세요.

### 무료 체험판이 있나요?
네, 무료 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Tasks 지원을 어떻게 받나요?
지원은 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) 커뮤니티에서 받을 수 있습니다.

### Aspose.Tasks 라이선스를 구매할 수 있나요?
네, 라이선스는 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Additional Q&A**

**Q: 기존 Microsoft Project 파일을 읽기 위해 Aspose.Tasks를 사용할 수 있나요?**  
A: 물론입니다. `Project` 클래스를 사용하면 `.mpp` 및 `.xml` 파일을 직접 로드할 수 있습니다.

**Q: 라이브러리가 프로젝트당 여러 캘린더를 지원하나요?**  
A: 예. 필요에 따라 원하는 만큼 `Calendar` 객체를 생성하고 각 작업에 할당할 수 있습니다.

## Conclusion
축하합니다! 이제 **add task to project** 방법, 사용자 정의 캘린더 생성 및 Aspose.Tasks for Java를 사용해 두 요소를 연결하는 방법을 성공적으로 익혔습니다. 이 강력한 조합을 활용하면 견고하고 일정에 민감한 애플리케이션을 빠르게 구축할 수 있습니다.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}