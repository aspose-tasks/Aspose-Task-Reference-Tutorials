---
date: 2025-12-23
description: Aspose.Tasks for Java를 사용하여 MS Project에서 작업 종속성을 만들고 중요 경로를 계산하는 방법을
  배우세요. 프로젝트 관리를 위한 단계별 가이드.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 작업 종속성을 생성하고 중요 경로를 계산
url: /ko/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 종속성 생성 및 중요 경로 계산

## 소개
이 튜토리얼에서는 **작업 종속성을 생성하고** Aspose.Tasks for Java를 사용하여 MS Project 파일에서 중요 경로를 계산하는 방법을 배웁니다. 중요 경로를 이해하고 시각화하면 프로젝트 일정을 유지하는 데 도움이 되며, 작업을 올바르게 연결하면 지연이 즉시 표시됩니다. 환경 설정부터 최종 중요 경로 표시까지 전체 과정을 단계별로 살펴보겠습니다.

## 빠른 답변
- **첫 번째 단계는?** Java 프로젝트를 설정하고 Aspose.Tasks 라이브러리를 추가합니다.  
- **어떤 모드를 활성화해야 하나요?** `CalculationMode.Automatic` (자동 계산 설정).  
- **작업을 어떻게 연결하나요?** `project.getTaskLinks().add(...)`를 사용하여 작업 종속성을 생성합니다.  
- **중요 경로는 어떻게 확인하나요?** `project.getCriticalPath()`를 순회하면서 각 작업 이름을 출력합니다.  
- **라이선스가 필요한가요?** 예, 프로덕션 사용을 위해 유효한 Aspose.Tasks 라이선스가 필요합니다.

## “작업 종속성 생성”이란?
작업 종속성을 생성한다는 것은 작업 간의 관계(예: Finish‑to‑Start)를 정의하여 일정이 실제 제약 조건을 반영하도록 만드는 것을 의미합니다. Aspose.Tasks에서는 `TaskLink` 객체를 통해 이를 수행합니다.

## MS Project에서 중요 경로를 계산하는 이유
**MS Project 중요 경로**는 프로젝트 최소 기간을 결정하는 가장 긴 종속 작업 순서를 보여줍니다. 이를 계산하면 전체 일정에 영향을 주지 않고는 지연될 수 없는 작업을 빠르게 식별할 수 있어 **Java 기반 프로젝트 관리** 애플리케이션에 필수적입니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하십시오:

1. 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java 라이브러리를 다운로드하여 프로젝트에 추가합니다. 다운로드는 [여기](https://releases.aspose.com/tasks/java/)에서 가능합니다.  

## 패키지 가져오기
Java 클래스에서 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.*;
```

## 자동 계산을 설정하는 방법
계산 모드를 자동으로 설정하면 작업이나 링크에 대한 모든 변경 사항이 즉시 일정에 반영되어 중요 경로도 자동으로 업데이트됩니다.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
MS Project 파일이 들어 있는 폴더 경로를 정의합니다.
```java
String dataDir = "Your Data Directory";
```

### 단계 2: MS Project 파일 로드
Aspose.Tasks를 사용하여 기존 프로젝트 파일(예: *New project 2013.mpp*)을 로드합니다.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### 단계 3: 작업 추가
나중에 연결할 세 개의 간단한 하위 작업을 생성합니다.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### 단계 4: 작업 링크 생성 (작업 종속성 생성)
작업 간의 종속성을 정의합니다. 여기서는 가장 일반적인 Finish‑to‑Start 링크를 사용합니다.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### 단계 5: 중요 경로 표시 (중요 경로 표시)
중요 경로를 가져와 출력합니다. `getCriticalPath()` 메서드는 중요 체인을 구성하는 작업 목록을 반환합니다.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### 단계 6: 완료 확인
프로세스가 끝나면 친절한 메시지를 표시합니다.
```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|------|--------|
| **중요 경로가 비어 있음** | 링크를 추가하기 전에 `CalculationMode.Automatic`이 설정되어 있는지 확인하십시오. |
| **작업이 연결되지 않음** | 각 종속성에 대해 `TaskLink` 객체를 추가했는지 확인하십시오. |
| **라이선스 예외** | `Project` 인스턴스를 생성하기 전에 유효한 Aspose.Tasks 라이선스를 로드하십시오. |

## FAQ
### Q: Aspose.Tasks for Java를 모든 버전의 MS Project 파일과 함께 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 MS Project 2003부터 MS Project 2019까지 다양한 .mpp 파일 버전을 지원합니다.  

### Q: Aspose.Tasks for Java의 무료 체험판이 있나요?
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.  

### Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.  

### Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
A: 예, [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 구매할 수 있습니다.  

### Q: Aspose.Tasks for Java를 어떻게 구매하나요?
A: [여기](https://purchase.aspose.com/buy)에서 Aspose.Tasks for Java를 구매할 수 있습니다.  

## 결론
이 단계들을 따라 **작업 종속성을 생성하고**, **자동 계산을 설정하며**, MS Project 파일에 대한 **중요 경로를 성공적으로 표시**했습니다. 이 워크플로우를 통해 일정 논리를 완전히 제어하고 Java 기반 **프로젝트 관리** 코드를 사용해 프로젝트를 원활히 진행할 수 있습니다.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}