---
date: 2026-02-20
description: Aspose.Tasks for Java를 사용하여 프로젝트에 작업을 추가하고 기간을 관리하는 방법을 살펴보세요. 기간을 설정하는
  방법과 기간을 쉽게 변환하는 방법을 배워보세요.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 프로젝트에 작업 추가 및 기간 관리
url: /ko/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트에 작업 추가 및 기간 관리 (Aspose.Tasks)

## 소개
이 튜토리얼에서는 **프로젝트에 작업을 추가하는 방법**과 Aspose.Tasks for Java를 사용해 작업 기간을 제어하는 방법을 배웁니다. 새로운 프로젝트 계획 도구를 만들든 기존 솔루션을 확장하든, 작업‑기간 처리를 마스터하는 것은 정확한 일정 관리와 보고에 필수적입니다.

## 빠른 답변
- **“프로젝트에 작업을 추가한다”는 무슨 의미인가요?** 프로젝트의 루트 또는 특정 요약 작업 아래에 새로운 `Task` 객체를 생성합니다.  
- **기간을 나타내는 클래스는 무엇인가요?** `com.aspose.tasks.Duration`.  
- **기간을 설정하려면?** `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`를 사용합니다.  
- **기간을 다른 단위로 변환할 수 있나요?** 예, `duration.convert(TimeUnitType.Hour)` 또는 다른 `TimeUnitType`을 호출하면 됩니다.  
- **프로덕션에서 라이선스가 필요한가요?** 상업적 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## “프로젝트에 작업을 추가한다”는 의미
프로젝트에 작업을 추가한다는 것은 `Task` 객체를 생성하고 이를 프로젝트의 작업 계층 구조에 연결하는 것을 의미합니다. 이 작업은 해당 작업에 작업량, 리소스 또는 기간을 정의하기 전에 수행해야 하는 첫 단계입니다.

## 작업 기간을 관리해야 하는 이유
정확한 기간은 현실적인 타임라인, 리소스 할당 및 핵심 경로 분석을 가능하게 합니다. Aspose.Tasks를 사용하면 기간을 프로그래밍 방식으로 설정, 읽기, 변환 및 조정할 수 있어 프로젝트 일정에 대한 완전한 제어권을 가질 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- Java Development Kit (JDK): 머신에 Java가 설치되어 있어야 합니다. [여기](https://www.oracle.com/java/technologies/javase-downloads.html)에서 다운로드할 수 있습니다.  
- Aspose.Tasks 라이브러리: Aspose.Tasks 라이브러리를 다운로드하여 프로젝트에 포함하십시오. 라이브러리는 [여기](https://releases.aspose.com/tasks/java/)에서 찾을 수 있습니다.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks와 작업하기 위해 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 단계 1: 프로젝트 설정
```java
// Create a new project
Project project = new Project();
```

## 단계 2: 새 작업 추가 (프로젝트에 작업 추가)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## 기간 설정 방법
작업이 생성되었으므로 이제 길이를 정의할 수 있습니다. 기본적으로 기간은 일(day) 단위로 표현됩니다.

## 단계 3: 작업 기간 가져오기 및 변환
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## 기간 변환 방법
`convert` 메서드를 사용하면 `Duration`을 한 `TimeUnitType`에서 다른 `TimeUnitType`으로 변환할 수 있습니다(예: days → hours, weeks → days).

## 단계 4: 작업 기간을 1주로 업데이트
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## 단계 5: 작업 기간 감소
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

위 단계를 따라 **프로젝트에 작업을 추가**하고 Aspose.Tasks for Java를 사용해 기간을 관리했습니다.

## 일반적인 함정 및 팁
- **함정:** 연산을 수행하기 전에 기간을 변환하지 않으면 잘못된 결과가 나올 수 있습니다. 항상 `duration.getTimeUnit()`으로 단위를 확인하십시오.  
- **팁:** 나중에 변환하는 대신 `project.getDuration(value, TimeUnitType)`을 사용해 원하는 단위의 기간을 직접 생성하십시오.  
- **함정:** 음수 기간을 설정하면 예외가 발생합니다. 입력 값을 반드시 검증하십시오.

## 결론
이 가이드에서는 **프로젝트에 작업을 추가**하고, 기본 기간을 읽으며, **기간 설정** 및 **기간 변환**을 다양한 시간 단위로 수행하는 방법을 다루었습니다. 이제 이러한 기술을 더 큰 일정 관리 애플리케이션에 통합해 정확한 프로젝트 계획을 구현할 수 있습니다.

## FAQ
### Aspose.Tasks가 모든 Java 버전과 호환되나요?
Aspose.Tasks는 Java 6 이상 버전과 호환됩니다.

### 상업 프로젝트에 Aspose.Tasks를 사용할 수 있나요?
예, 개인 및 상업 프로젝트 모두에 사용할 수 있습니다. 라이선스 상세 정보는 [여기](https://purchase.aspose.com/buy)에서 확인하십시오.

### 추가 지원 및 리소스는 어디서 찾을 수 있나요?
커뮤니티 지원 및 토론은 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 확인하십시오.

### 테스트용 임시 라이선스는 어떻게 얻나요?
테스트 및 평가용 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.Tasks의 무료 체험판이 있나요?
예, 구매 전 Aspose.Tasks를 체험하려면 [여기](https://releases.aspose.com/)에서 무료 체험판에 접근하십시오.

## 자주 묻는 질문

**Q: 작업의 기간을 설정한 뒤에 어떻게 변경하나요?**  
A: `task.get(Tsk.DURATION)`으로 현재 기간을 가져오고, (`add`, `subtract`, `convert` 등) 원하는 대로 수정한 뒤 `task.set(Tsk.DURATION, newDuration)`으로 다시 설정합니다.

**Q: 분 단위로 기간을 설정할 수 있나요?**  
A: 예, `project.getDuration(value, TimeUnitType.Minute)`을 호출하면 됩니다.

**Q: 기간을 변경하면 작업의 시작 및 종료 날짜가 자동으로 업데이트되나요?**  
A: 프로젝트의 스케줄링 모드가 자동으로 설정된 경우에만 자동 업데이트됩니다. 그렇지 않다면 `project.calculateCriticalPath()`를 호출해 일정을 다시 계산해야 할 수 있습니다.

**Q: 기간을 원시 숫자로 가져올 수 있나요?**  
A: `duration.getTimeSpan()`을 호출하면 현재 시간 단위의 숫자 값을 얻을 수 있습니다.

**Q: 현재 기간보다 더 큰 값을 빼면 어떻게 되나요?**  
A: API가 `ArgumentOutOfRangeException`을 발생시킵니다. 결과 기간이 양수인지 항상 검증하십시오.

---

**마지막 업데이트:** 2026-02-20  
**테스트 환경:** Aspose.Tasks for Java (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}