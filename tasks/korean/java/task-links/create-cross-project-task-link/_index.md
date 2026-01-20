---
date: 2026-01-20
description: Aspose.Tasks for Java를 사용하여 프로젝트를 연결하고 프로젝트 간 작업을 연결하는 방법을 배웁니다. 단계별
  가이드를 따라 교차 프로젝트 작업 링크를 생성하세요.
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: '프로젝트 연결 방법: Aspose.Tasks에서 교차 프로젝트 작업 링크 만들기'
url: /ko/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 연결 방법: Aspose.Tasks에서 교차 프로젝트 작업 링크 만들기

## Aspose.Tasks로 프로젝트 연결하는 방법
오늘날 빠르게 변화하는 프로젝트 관리 환경에서 **프로젝트를 연결하는 방법**을 아는 것은 여러 계획을 동기화하는 데 필수적입니다. Aspose.Tasks for Java은 교차 프로젝트 작업 링크를 생성할 수 있는 강력한 API를 제공하여 몇 줄의 코드만으로 **프로젝트 간 작업을 연결**할 수 있게 해줍니다. 이 튜토리얼에서는 정확한 단계들을 배우고, 필요한 코드 스니펫을 확인하며, 이 기술이 팀원 간 협업을 크게 향상시킬 수 있는 이유를 이해하게 됩니다.

## 빠른 답변
- **주요 이점은 무엇인가요?** 별도의 프로젝트 파일 간에 종속 작업 항목을 원활하게 동기화합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **구현에 걸리는 시간은?** 기본 링크는 대략 10–15분 정도 소요됩니다.  
- **다른 파일 형식 간에 작업을 연결할 수 있나요?** 예 – API는 MPP, XML 및 기타 형식을 지원합니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하세요:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Tasks for Java가 설치되어 있어야 합니다. [Aspose.Tasks for Java 릴리스 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
- 작업 종속성 및 요약 작업과 같은 프로젝트 관리 개념에 대한 기본 이해.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 이를 통해 Aspose.Tasks 핵심 기능에 접근할 수 있습니다:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## 1단계: 환경 설정
Java가 머신에 설치되어 있고 Aspose.Tasks JAR가 프로젝트의 classpath에 추가되어 있는지 확인하세요. 이 단계는 코드가 오류 없이 컴파일되도록 하는 데 중요합니다.

## 2단계: Project 인스턴스 생성
작업과 링크를 보관할 새로운 `Project` 객체를 생성합니다:

```java
Project project = new Project();
```

## 3단계: 요약 작업 추가
요약 작업은 연결할 작업들을 담는 컨테이너 역할을 합니다. 나중에 프로젝트를 볼 때 구조가 더 명확해집니다:

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## 4단계: 외부 작업 추가
다른 프로젝트 파일에 있는 작업을 가리키는 외부 작업을 추가합니다. 이것이 교차 프로젝트 링크의 “소스” 측입니다:

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## 5단계: 로컬 작업 추가
외부 작업에 연결될 로컬 작업을 생성합니다. 이것이 관계의 “대상” 측입니다:

```java
Task t = summary.getChildren().add("Task");
```

## 6 작업과 로컬 작업 사이에 링크를 설정합니다. `CrossProject`를 `true`로 설정하면 Aspose.Tasks에 두 개의 다른 프로젝트 파일을 아우르는 링크임을 알립니다:

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## 7단계: 결과 표시
마지막으로 간단한 확인 메시지를 출력하여 예외 없이 프로세스가 완료되었음을 알립니다:

```java
System.out.println("Process completed Successfully");
```

## 왜 프로젝트 간에 작업을 연결해야 할까요?
프로젝트 간에 작업을 연결하면 다음과 같은 이점을 얻을 수 있습니다:

- 수동 업데이트 없이 종속 작업 항목을 동기화합니다.  
- 동일한 작업이 여러 계획에 나타날 때 중복 작업을 줄입니다.  
- 팀 간 마일스톤 추적을 위한 단일 진실 소스를 제공합니다.  

## 일반적인 문제 및 해결책
| Issue | Solution |
|-------|----------|
| 외부 작업을 찾을 수 없음 | `EXTERNAL_TASK_PROJECT` 경로와 `EXTERNAL_ID`가 올바른지 확인하세요. |
| 링크 유형 불일치 | 원하는 종속성(예: Finish‑to‑Start)에 맞게 `TaskLinkType`을 설정하세요. |
| 라이선스 예외 | 프로젝트 인스턴스를 생성하기 전에 유효한 Aspose.Tasks 라이선스를 설치하세요. |

## 자주 묻는 질문

**Q: 동일한 요약 작업 안에 여러 외부 프로젝트의 작업을 연결할 수 있나요?**  
A: 예, 동일한 요약 작업 내에서 서로 다른 외부 프로젝트의 작업을 연결할 수 있으며, 절차는 동일합니다.

**Q: 연결된 프로젝트의 외부 작업이 수정되면 어떻게 되나요?**  
A: 외부 작업에 대한 모든 수정 사항이 현재 프로젝트의 연결된 작업에 반영됩니다.

**Q: 서로 다른 파일 형식 간에 작업을 연결할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다양한 파일 형식 간 작업 연결을 지원합니다.

**Q: 프로젝트 간에 연결된 작업을 해제할 수 있나요?**  
A: 예, 적절한 Aspose.Tasks 메서드를 사용하여 작업 링크를 제거하면 연결을 해제할 수 있습니다.

**Q: 프로젝트 간에 연결할 수 있는 작업 수에 제한이 있나요?**  
A: 연결 가능한 작업 수는 사용 중인 Aspose.Tasks 라이선스의 기능 및 제한에 따라 달라집니다.

## 결론
이제 **프로젝트를 연결하는 방법**과 **Aspose.Tasks for Java를 사용해 프로젝트 간 작업을 연결하는 방법**을 알게 되었습니다. 교차 프로젝트 작업 링크를 생성하면 협업이 원활해지고 수동 동기화 작업이 감소하며 프로젝트 계획을 일관되게 유지할 수 있습니다. 다양한 링크 유형을 실험하고 Aspose.Tasks의 추가 기능을 탐색하여 프로젝트 관리 워크플로우를 더욱 향상시켜 보세요.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}