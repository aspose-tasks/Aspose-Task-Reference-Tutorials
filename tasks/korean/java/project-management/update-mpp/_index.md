---
date: 2026-06-25
description: Aspose.Tasks for Java를 사용하여 작업을 추가하고 MPP 파일을 업데이트하는 방법을 배우세요. 이 Java
  프로젝트 관리 라이브러리를 사용하면 작업 Microsoft Project 파일을 생성하고 프로젝트를 MPP 형식으로 저장할 수 있습니다.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Aspose.Tasks에서 작업 추가 및 MPP 파일 업데이트 방법
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 작업 추가 및 MPP 파일 업데이트 방법
url: /ko/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 추가 및 MPP 파일 업데이트 방법

## 소개
이 튜토리얼에서는 기존 Microsoft Project (MPP) 파일에 **작업 추가**하는 방법을 배우고, 선도적인 **java 프로젝트 관리 라이브러리**인 Aspose.Tasks for Java를 사용해 업데이트된 일정을 저장하는 방법을 알아봅니다. 맞춤형 스케줄러를 구축하든, 대량 업데이트를 자동화하든, 프로젝트 데이터를 더 큰 시스템에 통합하든, 아래 단계별 가이드는 프로젝트를 로드하고, 새 작업을 삽입하고, 날짜를 설정한 뒤, 결과를 새로운 MPP 문서로 저장하는 정확한 방법을 보여줍니다.

## 빠른 답변
- **“작업 추가”가 이 문맥에서 의미하는 것은?** 기존 MPP 파일 내부에 새로운 작업 항목을 프로그래밍 방식으로 생성하는 것을 의미합니다.  
- **어떤 라이브러리가 이 작업을 수행하나요?** Aspose.Tasks for Java, 강력한 java 프로젝트 관리 라이브러리.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **결과를 MPP로 저장할 수 있나요?** 예—`project.save(..., SaveFileFormat.Mpp)`를 사용해 **프로젝트를 mpp로 저장**합니다.  
- **필요한 Java 버전은?** Java 8 이상.

## MPP 파일에서 “작업 추가”란 무엇인가요?
작업을 추가한다는 것은 프로젝트 계층 구조에 새로운 작업 항목을 삽입하고, 시작/종료 날짜를 정의한 뒤, 변경 사항을 MPP 파일에 다시 저장하는 것을 의미합니다. Aspose.Tasks는 파일 형식의 저수준 세부 사항을 추상화하여 비즈니스 로직에 집중할 수 있게 해 주며, 리소스 할당, 캘린더, 종속성 계산 등을 자동으로 처리합니다. 또한 관련 할당을 업데이트하고 프로젝트 일정을 재계산해 종속 작업 간 일관성을 유지합니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
- **전체 호환성**: Microsoft Project 2007‑2021 전 기능 100% 지원(150개 이상의 작업 유형 및 200개 이상의 리소스 필드).  
- **Zero‑dependency**: COM, Office, 네이티브 라이브러리 불필요—순수 Java API가 JRE가 실행되는 어디서든 동작합니다.  
- **풍부한 기능**: 작업 연결, 리소스 할당, 사용자 정의 필드, 내장 보고서 포함.  
- **고성능**: 10,000개 작업까지 200 MB 미만 메모리 사용으로 처리, 서버‑사이드 자동화에 최적.

## 전제 조건
1. **Java 개발 환경** – JDK 8+ 설치 및 설정.  
2. **Aspose.Tasks for Java** – [다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **기본 Java 지식** – 클래스, 객체, 날짜 처리에 익숙함.  

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 이를 통해 프로젝트 조작, 작업 속성, 날짜 처리 기능에 접근할 수 있습니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project`는 메모리에서 로드된 Microsoft Project 파일을 나타냅니다. `SaveFileFormat`은 MPP 또는 PDF와 같이 저장할 수 있는 형식을 열거합니다. `Task`는 프로젝트 계층 구조 내 개별 작업 항목을 모델링합니다. `Tsk`는 값 설정 또는 조회 시 사용되는 작업 필드 상수를 제공합니다. `Calendar`는 일정 정의를 위한 날짜‑시간 유틸리티를 제공합니다.

## 단계 1: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```  
`"Your Data Directory"`를 소스 MPP 파일이 위치한 절대 경로로 교체하십시오.

## 단계 2: 기존 프로젝트 읽기
`Project` 클래스는 메모리에서 Microsoft Project 파일을 나타내는 Aspose.Tasks 핵심 객체입니다.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
생성자는 **SampleMSP2010.mpp**를 로드하여 완전히 조작 가능한 객체 모델을 제공합니다.

## 단계 3: 새 작업 만들기 (작업 추가)
`Task` 클래스는 프로젝트 계층 구조 내 개별 작업 항목을 나타냅니다.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
이 코드는 루트 작업에 *Task1*이라는 자식을 추가하여 **MPP에 작업을 생성**합니다.

## 단계 4: 시작 및 종료 날짜 설정
`Calendar` 클래스는 날짜‑시간 유틸리티를 제공하며, 월은 0부터 시작합니다(예: `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
여기서는 새로 추가된 작업의 일정을 정의합니다. 프로젝트 일정에 맞게 날짜를 조정하십시오.

## 단계 5: 프로젝트 저장 (프로젝트를 mpp로 저장)
`SaveFileFormat.Mpp`는 Aspose.Tasks에 파일을 네이티브 Microsoft Project 형식으로 다시 기록하도록 지시합니다.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
업데이트된 프로젝트는 이제 새 작업을 포함하고 **AfterLinking.mpp**로 저장됩니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **파일을 찾을 수 없음** | `dataDir`가 경로 구분자(`/` 또는 `\\`)로 끝나는지, 파일 이름이 정확한지 확인하십시오. |
| **날짜가 올바르지 않음** | `Calendar` 월은 0부터 시작한다는 점을 기억하십시오; `Calendar.JULY`가 7월을 의미합니다. |
| **라이선스 예외** | 평가 워터마크를 방지하려면 API 호출 전에 유효한 Aspose.Tasks 라이선스를 설치하십시오. |

## 자주 묻는 질문
**Q: 한 번에 여러 작업을 추가하려면 어떻게 해야 하나요?**  
A: 작업 이름 컬렉션을 순회하면서 “작업 생성” 블록을 루프 안에서 반복하십시오.

**Q: 새 작업에 사용자 정의 필드를 설정할 수 있나요?**  
A: 예—`task.set(Tsk.CUSTOM_FIELD_x, value)`에서 *x*는 필드 인덱스입니다.

**Q: 기존 작업을 템플릿으로 복사할 수 있나요?**  
A: 원본 작업을 복제(`Task cloned = sourceTask.clone();`)한 뒤 원하는 부모에 추가하십시오.

**Q: 새 작업을 추가하는 대신 기존 작업을 업데이트해야 하면 어떻게 하나요?**  
A: ID로 작업을 조회(`Task existing = project.getRootTask().getChildren().getById(id);`)하고 속성을 수정하십시오.

**Q: Aspose.Tasks가 PDF나 PNG와 같은 다른 형식으로 저장을 지원하나요?**  
A: 예—`project.save("output.pdf", SaveFileFormat.Pdf);` 또는 `SaveFileFormat.Png`를 사용해 시각적 표현을 저장할 수 있습니다.

**마지막 업데이트:** 2026-06-25  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [MPP 파일 만들기 – Aspose.Tasks로 빈 프로젝트를 만들고 MPP 형식으로 저장](/tasks/java/project-configuration/create-save-mpp/)
- [프로젝트 만들기 – Aspose.Tasks로 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Java 작업 목록 만들기 – Aspose.Tasks를 사용한 MS Project 기준선](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}