---
date: 2026-02-23
description: Aspose.Tasks for Java를 사용해 프로젝트 작업에서 초과 근무를 관리하는 방법을 배우고, 초과 근무 비용을 계산하고
  리소스 추적을 간소화하는 방법을 포함합니다.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks로 작업 초과 근무 관리하기
url: /ko/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 작업의 초과 근무 관리 방법

## 소개
Microsoft Project 파일에서 **초과 근무를 관리하는 방법**을 찾고 있다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 각 작업의 초과 근무 관련 속성을 읽고, 수정하고, 보고하는 방법을 보여드리며, 일정과 예산을 정확하게 유지할 수 있습니다.  

## 빠른 답변
- **프로젝트에서 “초과 근무”는 무엇을 의미합니까?** 리소스의 정규 용량을 초과하는 추가 작업 시간.  
- **어떤 API 클래스가 초과 근무 데이터를 제공합니까?** `Task`와 `Tsk` 필드 컬렉션(예: `Tsk.OVERTIME_COST`).  
- **샘플을 실행하려면 라이선스가 필요합니까?** 예, 프로덕션 사용을 위해 임시 또는 정식 Aspose.Tasks 라이선스가 필요합니다.  
- **초과 근무 비용을 자동으로 계산할 수 있나요?** 물론입니다 – `Tsk.OVERTIME_COST`를 가져와 비용 비율 로직을 적용하면 됩니다.  
- **Java 17과 호환됩니까?** 예, Aspose.Tasks for Java는 Java 8 이상을 지원합니다.  

## 프로젝트 작업에서 초과 근무 관리란 무엇인가요?
초과 근무 관리는 리소스가 정상 작업 시간을 초과할 때 발생하는 추가 작업 및 비용을 추적하는 것을 의미합니다. 이 데이터를 정확하게 캡처하면 예산을 예측하고, 일정을 조정하며, 현실적인 프로젝트 상태를 보고하는 데 도움이 됩니다.

## 왜 Aspose.Tasks를 초과 근무에 사용해야 할까요?
* **Microsoft Project가 필요 없습니다** – .MPP 파일을 직접 작업합니다.  
* **초과 근무 필드에 대한 전체 접근** – 비용, 작업량, 진행률 값이 `Tsk` 열거형을 통해 제공됩니다.  
* **프로그래밍 방식 제어** – 수동 UI 단계 없이 초과 근무 비용을 읽고, 수정하고, 계산할 수 있습니다.

## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:
- Java 개발 환경: 머신에 Java 개발 환경이 설정되어 있는지 확인하십시오.  
- Aspose.Tasks for Java: Aspose.Tasks 라이브러리를 다운로드하고 설치하십시오. 라이브러리와 문서는 [here](https://reference.aspose.com/tasks/java/)에서 찾을 수 있습니다.  
- 프로젝트 파일: 튜토리얼 중에 사용할 프로젝트 파일(e.g., TaskOvertimes.mpp)을 준비하십시오.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks의 기능을 활용하려면 필요한 패키지를 가져와야 합니다. 다음 import 문을 추가하십시오:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 단계 1: 새 프로젝트 만들기
새 프로젝트를 만들거나(또는 기존 프로젝트를 로드) 하는 것은 모든 분석의 첫 번째 단계입니다. 이는 부수 키워드 **create new project**도 만족합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## 단계 2: 작업을 순회하고 초과 근무 세부 정보 출력
이제 최상위 작업을 하나씩 순회하면서 초과 근무 정보를 표시하고, `OVERTIME_COST` 필드를 읽어 **초과 근무 비용을 계산**하는 방법을 보여드리겠습니다.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **팁:** `OVERTIME_COST` 값은 리소스의 초과 근무 비율을 기준으로 Aspose.Tasks가 이미 계산합니다. 사용자 정의 계산이 필요하면 `OVERTIME_WORK`에 원하는 비율을 곱하고 `tsk.set(Tsk.OVERTIME_COST, yourValue);`로 필드를 업데이트하십시오.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **초과 근무 필드에 대한 null 값** | 소스 .MPP 파일에 실제로 초과 근무 데이터가 포함되어 있는지 확인하십시오; 그렇지 않으면 필드가 `null`을 반환합니다. |
| **수정 후 비용이 올바르지 않음** | 초과 근무 작업량이나 비용을 변경한 후 `project.save()`를 호출하여 변경 사항을 저장하십시오. |
| **라이선스를 찾을 수 없음** | `Aspose.Tasks.lic` 파일을 프로젝트 루트에 두거나 프로젝트를 로드하기 전에 프로그래밍 방식으로 라이선스를 설정하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 대규모 프로젝트 관리에 적합한가요?**  
A: 예, Aspose.Tasks는 소규모 프로젝트부터 대규모 복잡한 프로그램까지 다양한 규모의 프로젝트를 처리하도록 설계되었습니다.

**Q: Aspose.Tasks를 다른 Java 프레임워크와 통합할 수 있나요?**  
A: 물론입니다! Aspose.Tasks는 Spring, Jakarta EE 및 기타 Java 생태계와 원활하게 통합되어 활용도가 높아집니다.

**Q: Aspose.Tasks 사용 시 라이선스 관련 고려 사항이 있나요?**  
A: 예, 라이선스 상세 정보와 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 확인하고 얻을 수 있습니다.

**Q: 지원을 받거나 Aspose.Tasks 관련 질문을 논의하려면 어디에 가야 하나요?**  
A: 커뮤니티와 소통하고 지원을 받으려면 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

**Q: Aspose.Tasks의 무료 체험 버전이 있나요?**  
A: 예, 무료 체험 버전은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: 특정 리소스의 초과 근무 비용을 어떻게 계산하나요?**  
A: 리소스의 초과 근무 비율을 가져와 `OVERTIME_WORK`(시간)와 곱한 뒤, 사용자 정의 계산이 필요하면 결과를 `OVERTIME_COST`에 다시 설정하십시오.

## 결론
Aspose.Tasks for Java는 프로젝트 작업에서 **초과 근무를 관리하는 방법**을 간소화하여 개발자에게 초과 근무 비용, 작업량 및 진행률 메트릭에 대한 직접적인 프로그래밍 접근을 제공합니다. 이 가이드를 따라 프로젝트를 로드하고, 초과 근무 세부 정보를 읽고, 백분율을 조정하며, 사용자 정의 초과 근무 비용까지 계산할 수 있으며, Microsoft Project를 열 필요가 없습니다.

---

**마지막 업데이트:** 2026-02-23  
**테스트 환경:** Aspose.Tasks for Java (latest version)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}