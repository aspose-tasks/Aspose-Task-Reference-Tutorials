---
date: 2026-02-23
description: Aspose.Tasks for Java를 사용하여 프로젝트 시작 날짜를 설정하고 작업 기간을 지정하며 프로젝트를 MPP 파일로
  저장하는 방법을 배워보세요. 상위 작업과 하위 작업을 효율적으로 관리하세요.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 프로젝트 시작 날짜 설정 및 상위·하위 작업 관리
url: /ko/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 프로젝트 시작 날짜 설정 및 부모·자식 작업 관리

## 소개
효과적인 작업 조직은 성공적인 프로젝트 관리의 핵심이며, **프로젝트 시작 날짜 설정**을 정확히 하는 것이 잘 구성된 일정의 첫 번째 단계입니다. 이 튜토리얼에서는 **프로젝트 시작 날짜 설정**, 작업 기간 구성 및 Aspose.Tasks for Java를 사용한 부모‑자식 관계 관리 방법을 보여줍니다. 끝까지 진행하면 **프로젝트를 MPP로 저장**, 작업 완료 비율 업데이트 및 실제 시나리오에 맞게 작업 속성을 사용자 정의할 준비가 됩니다.

## 빠른 답변
- **프로젝트 시작 날짜를 어떻게 설정하나요?** `Project` 객체를 초기화한 **후** `proj.set(Prj.START_DATE, startDate);`를 사용합니다.  
- **부모 작업 아래에 자식 작업을 추가할 수 있나요?** 예 – `parentTask.getChildren().add("Child Task")`를 호출합니다.  
- **Aspose.Tasks가 파일을 저장하는 형식은 무엇인가요?** `SaveFileFormat.Mpp`를 사용하여 **프로젝트를 MPP로 저장**합니다.  
- **작업 완료를 어떻게 업데이트하나요?** 작업 객체에 `Tsk.PERCENT_COMPLETE`를 설정합니다.  
- **임시 라이선스를 어디서 얻을 수 있나요?** FAQ에 링크된 임시‑라이선스 페이지를 방문하세요.

## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되는지 확인하세요:
- Java 프로그래밍에 대한 기본 이해.  
- Aspose.Tasks for Java 라이브러리가 설치되어 있어야 합니다. [여기](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
- 시스템에 Java 통합 개발 환경(IDE)이 설정되어 있어야 합니다.

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다. 이러한 패키지는 Aspose.Tasks for Java 기능과의 원활한 통합을 지원합니다.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## 단계 1: 프로젝트 시작 날짜 설정
프로젝트의 시작 날짜와 기타 관련 매개변수를 설정하는 것으로 시작합니다.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## 단계 2: 부모 작업 추가 (작업 1)
`Task 1`이라는 이름의 부모 작업을 만들고 **set task duration**을 포함한 속성을 구성합니다.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## 단계 3: 자식 작업이 있는 부모 작업 추가 (작업 2)
이제 `Task 2`라는 또 다른 부모 작업을 추가하고 자식 작업(Task 3 및 Task 4)을 포함합니다.
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## 단계 4: 자식 작업 구성
Task 3 및 Task 4에 대한 시작 날짜, 기간 및 제약 조건을 지정합니다.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## 단계 5: 작업 완료 비율 업데이트
Task 3 및 Task 4의 완료 비율을 조정합니다 – 이것이 **작업 완료 업데이트** 방법입니다.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## 단계 6: 프로젝트 저장
마지막으로 적용된 변경 사항과 함께 **프로젝트를 MPP로 저장**합니다.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

이 단계별 가이드는 Aspose.Tasks for Java를 사용하여 부모 및 자식 작업을 효과적으로 관리하는 방법을 보여줍니다. 프로젝트 요구 사항에 맞게 다양한 구성을 실험해 보세요.

## 작업 속성을 사용자 정의해야 하는 이유
시작 날짜, 기간, 제약 조건 및 완료 비율과 같은 작업 속성을 사용자 정의하면 일정 동작을 세밀하게 제어할 수 있습니다. 작업을 리소스 가용성에 맞추거나 비즈니스 규칙을 적용해야 할 경우, Aspose.Tasks를 사용하면 **작업 속성을 프로그래밍 방식으로 사용자 정의**할 수 있습니다.

## 일반적인 문제 및 해결책
| Issue | Solution |
|-------|----------|
| **시작 날짜가 적용되지 않음** | `Project` 객체를 생성한 **후** 작업을 추가하기 **전** `proj.set(Prj.START_DATE, …)`를 호출했는지 확인하세요. |
| **자식 작업이 잘못된 제약 조건을 상속** | Step 4에 표시된 대로 각 자식의 `ConstraintType` 및 `ConstraintDate`를 명시적으로 설정합니다. |
| **저장된 파일을 MS Project에서 열 수 없음** | 최신 Aspose.Tasks 버전을 사용하고 있는지 확인한 뒤 `SaveFileFormat.Mpp`로 저장하세요. |
| **UI에 비율이 반영되지 않음** | `Tsk.PERCENT_COMPLETE`를 설정한 후, 재계산된 날짜가 필요하면 `proj.calculateTaskSchedule()`를 호출하세요. |

## FAQ
### Aspose.Tasks for Java가 다양한 프로젝트 파일 형식과 호환되나요?
예, Aspose.Tasks for Java는 MPP 및 XML을 포함한 다양한 프로젝트 파일 형식을 지원합니다.

### 이 튜토리얼에서 다루는 것보다 더 많은 작업 속성을 사용자 정의할 수 있나요?
물론입니다! Aspose.Tasks for Java는 작업 속성에 대한 광범위한 사용자 정의 옵션을 제공합니다.

### Aspose.Tasks에 대한 커뮤니티 포럼이 있어 지원을 받을 수 있나요?
예, 커뮤니티 지원을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문할 수 있습니다.

### Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
[여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

### Aspose.Tasks for Java에 대한 포괄적인 문서는 어디서 찾을 수 있나요?
문서는 [여기](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

**Additional Q&A**

**Q: 프로그래밍 방식으로 임시 라이선스를 얻으려면 어떻게 해야 하나요?**  
A: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`를 사용하여 임시 라이선스 파일을 로드합니다.

**Q: 기본 작업 기간 단위를 변경할 수 있나요?**  
A: 예 – `proj.getDuration(value, TimeUnitType.YourChoice)`에서 `TimeUnitType` 인수를 수정합니다.

**Q: `SaveFileFormat.Mpp`를 사용하려면 어떤 버전의 Aspose.Tasks가 필요합니까?**  
A: 2022‑2026 모든 최신 버전이 MPP 저장을 지원합니다; 파괴적인 변경 사항이 있는지 릴리스 노트를 확인하세요.

---

**마지막 업데이트:** 2026-02-23  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}