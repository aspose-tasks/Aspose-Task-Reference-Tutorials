---
date: 2026-03-03
description: Aspose.Tasks for Java에서 WBS를 재번호 매기는 방법을 배우고, 작업 분류를 관리하며 단계별 예제로 WBS
  코드를 효율적으로 맞춤 설정하세요.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java에서 WBS를 재번호 매기기
url: /ko/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java에서 WBS 번호 재지정하는 방법

## Introduction
Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 **WBS 번호를 재지정하는 방법**이 필요하다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 기존 WBS 코드를 읽고, 사용자 정의한 뒤, 계층 구조를 재번호 매겨 프로젝트를 정돈된 상태로 유지하는 방법을 단계별로 안내합니다. 레거시 일정을 정리하든 새 일정을 처음부터 구축하든, 이 과정을 마스터하면 **작업 분류 구조**를 자신 있게 관리할 수 있습니다.

## Quick Answers
- **What does renumbering WBS do?** 작업 구조 변경을 반영하도록 작업의 계층 번호를 다시 계산합니다.  
- **Which class performs the renumbering?** `Project.renumberWBSCode`.  
- **Do I need a license to run the code?** 프로덕션 환경에서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **Can I customize the WBS format?** 예—`Task.set(Tsk.WBS, "...")`를 사용해 원하는 문자열을 할당할 수 있습니다.  
- **What are the main prerequisites?** Java JDK, Aspose.Tasks for Java 라이브러리, 그리고 유효한 프로젝트 파일(.mpp).

## What is a Work Breakdown Structure (WBS)?
Work Breakdown Structure (WBS)는 프로젝트의 산출물과 작업을 계층적으로 표현한 구조입니다. 각 작업은 계층 위치를 나타내는 코드(예: 1.2.3)를 부여받습니다. 작업이 추가·삭제·재정렬될 때 번호를 재지정하면 코드가 논리적이고 읽기 쉬운 상태를 유지할 수 있습니다.

## Why manage work breakdown and customize WBS codes?
- **Clarity:** 명확한 WBS 코드는 이해관계자가 작업을 쉽게 찾을 수 있게 합니다.  
- **Reporting:** 많은 보고 도구가 일관된 번호 체계를 기반으로 합니다.  
- **Flexibility:** 사용자 정의 코드를 통해 프로젝트 구조를 내부 표준에 맞출 수 있습니다.  

## Prerequisites
코드를 진행하기 전에 다음이 준비되어 있는지 확인하세요:

- 머신에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
- 프로젝트에 Aspose.Tasks for Java 라이브러리가 추가되어 있어야 합니다. 라이브러리는 [here](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  

## Import Packages
프로젝트를 시작하기 위해 필요한 패키지를 임포트하세요:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Read WBS Codes
먼저 기존 WBS 코드를 읽어 현재 작업 상황을 확인합니다.

### Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Step 2: Collect Tasks
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Step 3: Parse and Customize
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

위 스니펫은 각 작업의 현재 WBS와 레벨을 출력한 뒤, **customize wbs codes**를 위해 새로운 문자열을 할당하는 예시를 보여줍니다.

## Renumber Task WBS Codes
이제 실제로 WBS 계층을 재번호 매깁니다.

### Step 1: Load the Project (Renumber Example)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Step 2: Select All Tasks
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Step 3: Output Initial WBS Codes
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Step 4: Renumber WBS Codes
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Step 5: Output Updated WBS Codes
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

이 단계들을 따라 하면 프로젝트 파일 내 모든 작업에 대해 **WBS 번호를 재지정하는 방법**을 효과적으로 적용할 수 있습니다.

## Common Issues and Solutions
- **WBS not changing after `set` call:** 올바른 작업 인스턴스를 사용하고, 수정 후 프로젝트를 저장했는지 확인하세요.  
- **`renumberWBSCode` throws an exception:** ID 목록이 최상위 작업 수와 일치하는지 확인하십시오. 일치하지 않으면 새 번호를 매핑할 수 없습니다.  
- **Missing WBS values:** 파일에서 WBS가 정의되지 않은 경우 일부 작업에 `null` 값이 있을 수 있습니다. 출력하기 전에 대체 값을 사용하세요.

## Frequently Asked Questions

**Q: Where can I find the documentation for Aspose.Tasks for Java?**  
A: 문서는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

**Q: How can I download Aspose.Tasks for Java?**  
A: 다운로드는 [here](https://releases.aspose.com/tasks/java/)에서 가능합니다.

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: 예, 무료 체험은 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: 지원은 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 받을 수 있습니다.

**Q: Can I obtain a temporary license for Aspose.Tasks for Java?**  
A: 예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

**Q: Can I rename the WBS format after renumbering?**  
A: 물론입니다. `renumberWBSCode` 호출 후 작업을 순회하면서 `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))`와 같이 원하는 명명 규칙을 적용할 수 있습니다.

**Q: Does renumbering affect task dependencies?**  
A: 영향을 주지 않습니다. 이 메서드는 WBS 문자열만 업데이트하며, 작업 링크와 제약 조건은 그대로 유지됩니다.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}