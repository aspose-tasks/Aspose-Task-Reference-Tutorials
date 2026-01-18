---
date: 2026-01-18
description: Aspose.Tasks를 사용하여 MS Project 없이 기준선을 설정하고, Java에서 작업 목록을 만든 다음 작업을 Microsoft
  Project에 추가하는 방법을 배웁니다.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용한 Java 작업 목록 생성 – MS Project 기준선
url: /ko/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 작업 목록 만들기 – Aspose.Tasks를 사용한 MS Project 기준선

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 작업 기준선을 생성함으로써 **Java 작업 목록을 만들** 수 있습니다. Aspose.Tasks를 이용하면 Microsoft Project를 설치하지 않아도 Project 파일을 다룰 수 있어 **Microsoft Project에 작업을 추가**, 리소스를 조작하고 **MS Project 없이 기준선을 설정**할 수 있습니다—모두 순수 Java 코드만으로 가능합니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 하나요?** Microsoft Project 파일을 MS Project 없이 생성, 읽기 및 편집할 수 있는 Java API를 제공합니다.  
- **Microsoft Project를 설치해야 하나요?** 필요 없습니다. Aspose.Tasks는 독립적으로 동작합니다.  
- **필요한 Java 버전은?** JDK 8 이상.  
- **단일 작업에 기준선을 설정할 수 있나요?** 네, 작업 목록과 함께 `setBaseline`을 사용하면 됩니다.  
- **프로덕션에서 라이선스가 필요한가요?** 네, 상용 라이선스를 사용하면 평가 제한이 해제됩니다.

## 작업 기준선이란?
작업 기준선은 작업의 원래 계획된 시작일, 종료일 및 작업량 값을 기록합니다. 이는 실제 진행 상황을 원래 계획과 비교할 때 기준점으로 활용됩니다.

## 왜 Aspose.Tasks로 Java 작업 목록을 만들까요?
- **MS Project 의존성 없음** – 서버‑사이드 자동화에 이상적입니다.  
- **Java 코드로 작업, 리소스, 캘린더를 완전 제어**.  
- **Project 2007‑2024 파일과의 크로스‑버전 호환성**.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – JDK 8 이상을 설치합니다.  
2. **Aspose.Tasks for Java** – [download link](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드합니다.  

## 패키지 가져오기
Aspose.Tasks를 Java 프로젝트에서 사용하려면 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 단계 1: Project 객체 생성
```java
Project project = new Project();
```
여기서 새로운 `Project` 객체를 인스턴스화합니다—이 객체는 작업 목록을 보관할 MS Project 파일을 나타냅니다.

## 단계 2: 프로젝트에 작업 추가
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()`를 사용해 프로젝트 계층 구조의 루트에 접근하고 **Microsoft Project에 작업을 추가**합니다. 문자열 `"Task"`는 작업 이름이며, 필요에 따라 원하는 설명으로 교체할 수 있습니다.

## 단계 3: 지정된 작업에 기준선 설정
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**MS Project 없이 기준선을 설정**하려면 기준선을 적용할 작업 목록(여기서는 `myList`)을 만든 뒤 `setBaseline`에 전달합니다. 선택적인 기준선만 필요하다면 추가한 작업들을 `myList`에 채워 넣으세요.

## 단계 4: 전체 프로젝트에 기준선 설정
```java
project.setBaseline(BaselineType.Baseline);
```
전체 프로젝트에 한 번에 기준선을 적용하려면 원하는 `BaselineType`을 지정해 `setBaseline`을 호출하면 됩니다.

## Aspose.Tasks를 사용해 Microsoft Project에 작업을 추가하는 방법
위의 단일 작업 예시 외에도 여러 작업, 하위 작업을 추가하고 리소스를 할당할 수 있습니다. `add()` 호출마다 반환되는 `Task` 객체를 이용해 기간, 시작 날짜 등을 추가로 설정할 수 있습니다.

## MS Project 없이 기준선을 설정하는 방법
Aspose.Tasks는 코드만으로 기준선 생성을 완전 지원합니다. `BaselineType` 열거형을 변경해 Baseline, Baseline1‑Baseline10 등 다양한 기준선 유형을 설정할 수 있어, MS Project를 열지 않고도 여러 개의 수정 기준선을 추적할 수 있습니다.

## 일반적인 문제와 해결책
- **기준선이 표시되지 않음:** 기준선을 설정한 후 `project.save("output.mpp")` 호출을 반드시 수행하세요(예제에서는 간략히 생략).  
- **작업 목록이 비어 있음:** 올바른 부모(`getRootTask()` 또는 하위 작업)에 작업을 추가했는지 확인하세요.  
- **버전 불일치 오류:** 최신 Aspose.Tasks JAR를 사용해 최신 .mpp 형식과의 호환성을 보장하세요.

## 자주 묻는 질문

**Q: Microsoft Project를 설치하지 않고 Aspose.Tasks for Java를 사용할 수 있나요?**  
A: 네, Aspose.Tasks는 독립적으로 동작하며 호스트 머신에 Microsoft Project가 필요하지 않습니다.

**Q: Aspose.Tasks for Java는 다양한 버전의 Microsoft Project와 호환되나요?**  
A: 물론입니다. 이 라이브러리는 2007부터 최신 2024 버전까지의 Project 파일을 지원합니다.

**Q: Aspose.Tasks for Java를 사용해 프로젝트 리소스를 조작할 수 있나요?**  
A: 네, 작업과 마찬가지로 리소스를 프로그래밍 방식으로 추가, 업데이트 및 삭제할 수 있습니다.

**Q: Aspose.Tasks for Java가 작업 종속성 설정을 지원하나요?**  
A: 네, `TaskLink` 클래스를 사용해 선행‑후속 관계를 정의할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 기술 지원이 제공되나요?**  
A: 네, [support forum](https://forum.aspose.com/c/tasks/15)에서 Aspose 직원 및 커뮤니티가 질문에 답변합니다.

## 결론
이 단계들을 따라 하면 **Java 작업 목록을 만들고**, **Microsoft Project에 작업을 추가**하며, **MS Project 없이 기준선을 설정**하는 방법을 배웠습니다. 이 접근 방식은 프로젝트 자동화를 간소화하고 데스크톱 Project 설치 필요성을 없애며, 프로젝트 데이터를 완전하게 프로그래밍적으로 제어할 수 있게 해줍니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---