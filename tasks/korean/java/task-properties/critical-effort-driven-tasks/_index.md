---
date: 2026-01-25
description: Aspose Tasks Java를 사용하여 Java 작업 관리를 수행하고, 프로젝트에서 중요하고 노력 중심적인 작업을 처리하는
  방법을 배우세요. 이 가이드를 통해 프로젝트 워크플로를 향상시키세요.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – 중요 작업 및 노력 기반 작업 관리
url: /ko/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: 중요 및 노력 기반 작업 관리

현대 프로젝트 관리에서 **aspose tasks java**는 Java 코드에서 직접 중요 및 노력토하여 중요 및 노력 기반 작업을요) 은 무엇을 의미합니까?** 지연될 경우 프로젝트 종료 날짜가 연장되는 작업.  
- **“effort‑driven”(노력 기반) 은 무엇입니까?** 작업량을 변경하면 자동으로 기간을 조정하는 작업.  
- **어떤 라이브러리가 이러한 기능을 제공합니까?** Aspose Tasks Java.  
- **개발에 라이선용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 라이선스가 필요합니다.  
 (Windows, Linux, macOS) 모두에서 동작합니다.

## 중요 및 노력 기반 작업이란?
중소스에 적합합니다.

## 왜 Aspose Tasks Java를 사용해야 할까요?
- **Java에서 완전한 .NET 스타일 API** – 언어를 전환할량 XML- **풍부한 속성 집합** – `IS_CRITICAL`, `IS_EFFORT_DRIVEN` 등 다양한 작업 속성에 접근할 수 있습니다.  
- **크로스 플랫폼** – JVM 호환 환경 어디서든 실행됩니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:
- Aspose.Tasks for Java 라이브러리: [Aspose.Tasks for Java 문서](https://reference.aspose합니다.

Java 프로젝트에서 Aspose.Tasks for Java의 기능을 활용하려면 필요한 패키지를 가져옵니다:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### 단계 1: `ChildTasksCollector`를 사용하여 작업 수집
`TaskUtils.apply`를 사용하여 루트 작업에서 모든 작업을 수집하기 위해 `ChildTasksCollector` 인스턴스를 생성합니다. 이를 통해 프로젝트 내 모든 작업에 접근할 수 있습니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### 단계 2: 수집된 작업 반복 처리
`for` 루프를 사용하여 수집된 모든 작업을 순회합니다. 각 작업에 대해 노력 기반인지와 중요 여부를 판단한 뒤 해당 상태를 출력합니다.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

이러한 단계를 따르면 **aspose tasks java**를 사용하여 프로젝트의 중요 및 노력 기반 작업을 효과적으로 관리할 수 있습니다.

## 일반적인 문제와 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|-----------|
| `tsk.get(Tsk.IS_CRITICAL)`에서 NullPointerException 발생 | 작업에 해당 속성이 설정되지 않음(예: 요약 작업). | `tsk.get(Tsk.TASK_TYPE)`을 확인한 후 플래그에 접근하거나, 요약 작업을 필터링합니다. |
| 프로젝트 파일을 찾을 수 없음 | `dataDir` 경로가 잘못되었거나 파일 확장자가 누락됨. | `Paths.get(dataDir, "project.xml").toString()`을 사용하고 파일이 존재하는지 확인합니다. |
| 라이선스가 적용되지 않음 | 라이브러리가 평가 모드로 실행되어 기능이 제한됨. | `Project` 객체를 생성하기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`와 같이 라이선스 파일을 로드합니다. |

## 자주 묻는 질문
### Q: Aspose.Tasks for Java를 Windows와 Linux 환경 모두에서 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 플랫폼에 독립적이며 Windows와 Linux 환경 모두에서 사용할 수 있습니다.

### Q: Aspose.Tasks for Java의 무료 체험판이 있나요?
A: 예, Aspose.Tasks for Java 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Q: Aspose.Tasks for Java에 대한 지원은 어디서 찾을 수 있나요?
A: 커뮤니티 지원 및 토론을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하세요.

### Q: Aspose.Tasks for Java 임시 라이선스는 어떻게 얻을 수 있나요?
A: 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 획득할 수 있습니다.

### Q: Aspose.Tasks for Java는 어디서 구매할 수 있나요?
A: [구매 페이지](https://purchase.aspose.com/buy)에서 Aspose.Tasks for Java를 구매할 수 있습니다.

**마지막 업데이트:** 2026-01-25  
**테스트 환경:** Aspose.Tasks Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}