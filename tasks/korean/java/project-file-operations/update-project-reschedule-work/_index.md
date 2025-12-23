---
date: 2025-12-23
description: Aspose.Tasks for Java를 사용하여 MS Project 파일을 업데이트하고 완료되지 않은 작업을 재스케줄링하는
  방법을 배우세요. 또한 MS Project XML을 저장하는 방법도 확인하세요.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project 업데이트 및 작업 재스케줄링
url: /ko/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 업데이트 및 Aspose.Tasks로 작업 재스케줄링

## Introduction
Microsoft Project는 팀이 작업을 계획하고, 추적하며, 제때에 전달하도록 돕는 널리 사용되는 프로젝트 관리 도구입니다. 일정이 변경될 때, 종종 **MS Project** 파일을 프로그래밍 방식으로 **업데이트**해야 합니다—작업을 완료된 것으로 표시하고, 남은 작업을 이동하며, 프로젝트 기준선을 정확하게 유지합니다. Aspose.Tasks for Java는 GUI를 열지 않고도 정확히 그 작업을 수행할 수 있는 깔끔하고 타입‑안전한 API를 제공합니다. 이 튜토리얼에서는 프로젝트를 업데이트하고, 특정 날짜까지 작업을 완료된 것으로 표시한 다음, 아직 남아 있는 **MS Project** 작업을 **재스케줄링**하는 방법을 보여줍니다.

## Quick Answers
- **“MS Project 업데이트”는 무엇을 의미합니까?** 지정된 날짜까지 작업을 완료된 것으로 표시하고 변경 사항을 파일에 기록합니다.  
- **남은 작업을 자동으로 재스케줄링할 수 있나요?** 예—`rescheduleUncompletedWorkToStartAfter`를 사용하여 미완료 작업을 앞으로 이동합니다.  
- **어떤 파일 형식으로 저장되나요?** 예제에서는 프로젝트를 XML(`SaveFileFormat.Xml`) 형식으로 저장합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 개발용으로는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **필요한 Java 버전은?** JDK 8 이상.

## What is “update MS Project” in code?
프로젝트를 업데이트한다는 것은 작업 날짜, 기간, 혹은 완료 비율을 프로그래밍 방식으로 변경하고 그 변경 사항을 영구히 저장하는 것을 의미합니다. Aspose.Tasks는 제공된 기준 `Date`를 기반으로 변경을 적용하는 `updateProjectWorkAsComplete`와 같은 메서드를 노출합니다.

## Why use Aspose.Tasks for Java to update MS Project?
- **UI 의존성 없음** – 다수 파일에 대한 대량 변경을 자동화합니다.  
- **고충실도** – 라이브러리가 모든 기본 Project 데이터(리소스, 캘린더, 사용자 정의 필드)를 보존합니다.  
- **크로스‑플랫폼** – Windows, Linux, macOS에서 동일한 코드를 실행합니다.  
- **MS Project XML 저장** – 업데이트된 프로젝트를 널리 지원되는 XML 형식으로 내보내어 다운스트림 도구에서 사용할 수 있습니다.

## Prerequisites
1. Java Development Kit (JDK) 설치  
2. Aspose.Tasks for Java 라이브러리 – [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. Java 구문 및 객체 지향 개념에 대한 기본 지식  

## Import Packages
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| 작업이 업데이트된 날짜를 표시하지 않음 | 프로젝트가 다른 형식(예: `.mpp`)으로 저장됨 | `SaveFileFormat.Xml`을 사용하여 XML 구조를 유지합니다. |
| `updateProjectWorkAsComplete`가 아무 작업도 하지 않는 것처럼 보임 | 참조 날짜가 프로젝트 시작일보다 이전임 | `Calendar` 날짜가 프로젝트 일정 내에 있는지 확인합니다. |
| 재스케줄된 작업이 겹침 | 캘린더나 리소스 레벨링이 적용되지 않음 | `Project` 캘린더를 적용하거나 재스케줄링 후 `Task.setStart`를 수동으로 사용합니다. |

## Frequently Asked Questions (Extended)

**Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 작업, 종속성, 리소스 및 기타 프로젝트 요소를 효율적으로 관리할 수 있는 강력한 API를 제공합니다.

**Q: Aspose.Tasks for Java용 체험 버전이 있나요?**  
A: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 받을 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어떻게 받을 수 있나요?**  
A: 도움이 필요하거나 질문이 있으면 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 문의할 수 있습니다.

**Q: Aspose.Tasks for Java용 임시 라이선스를 구매할 수 있나요?**  
A: 예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 포괄적인 가이드와 API 레퍼런스는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## Conclusion
이 튜토리얼에서는 **MS Project** 파일을 업데이트하고 작업을 완료된 것으로 표시한 뒤, 아직 완료되지 않은 작업을 **재스케줄링**하는 전체 과정을 살펴보았습니다. 프로젝트를 XML로 저장하면 다른 도구와의 호환성을 유지하면서 변경 내역을 명확히 추적할 수 있습니다. 이러한 패턴을 활용해 대규모 포트폴리오의 일정 조정을 자동화하고, CI 파이프라인에 통합하거나 맞춤형 보고 대시보드를 구축해 보세요.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}