---
date: 2026-08-03
description: Aspose.Tasks for Java를 사용하여 ms project 캘린더를 만들고, 프로젝트에 캘린더를 추가하며, 프로젝트를
  XML로 저장하는 방법을 배웁니다.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Aspose.Tasks를 사용하여 프로젝트에 캘린더 추가
og_description: Aspose.Tasks for Java를 사용하여 ms project 캘린더를 프로그래밍 방식으로 생성합니다. 캘린더를
  추가하고, 일정을 맞춤 설정하며, 몇 분 안에 XML로 내보낼 수 있습니다.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Aspose.Tasks for Java를 사용하여 ms project 캘린더 만들기
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java를 사용하여 ms project 캘린더 만들기
url: /ko/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 MS Project 캘린더 만들기

## 소개
현대 프로젝트 관리 워크플로우에서 **create ms project calendar**를 프로그래밍 방식으로 생성하는 능력은 수동 편집 시간을 크게 절감할 수 있습니다. Aspose.Tasks for Java는 데스크톱 클라이언트를 열지 않고도 Microsoft Project 파일을 조작할 수 있는 깔끔하고 타입‑세이프한 API를 제공합니다. 이 튜토리얼에서는 캘린더를 추가하고, MS Project 캘린더를 생성하며, 프로젝트를 XML로 저장하는 방법을 몇 줄의 Java 코드만으로 배우게 됩니다.

## 빠른 답변
- **“create ms project calendar”가 의미하는 바는?**  
  코드를 통해 Microsoft Project 파일에 새로운 작업 시간 정의(캘린더)를 삽입하는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리합니까?**  
  Aspose.Tasks for Java는 캘린더를 관리하기 위해 `Calendar` 클래스와 `Project` 컨테이너를 제공합니다.  
- **라이선스가 필요합니까?**  
  테스트용 임시 평가 라이선스로 충분하지만, 실제 운영에서는 정식 라이선스가 필요합니다.  
- **파일을 XML로 저장할 수 있나요?**  
  예—`SaveFileFormat.Xml`을 사용하여 프로젝트를 XML 파일로 내보낼 수 있습니다.  
- **전제 조건은 무엇인가요?**  
  Java JDK 8 이상과 클래스패스에 Aspose.Tasks for Java JAR가 필요합니다.

## create ms project calendar란 무엇인가요?
MS Project 캘린더를 생성한다는 것은 프로젝트 파일에 새로운 캘린더 정의를 프로그래밍 방식으로 추가하고, 작업일, 예외 및 일일 작업 시간을 지정한 뒤, 해당 캘린더를 작업, 리소스 또는 전체 프로젝트에 할당하여 일정 계산이 정의된 작업 시간을 반영하도록 하는 것을 의미합니다.

## 프로젝트에 캘린더를 추가하기 위해 Aspose.Tasks for Java를 사용하는 이유는?
Aspose.Tasks for Java를 사용해야 하는 이유는 Microsoft Project가 설치되지 않은 환경에서도 작동하는 완전한 타입‑세이프 API를 제공하고, 주요 Project 버전(2007‑2021, 5개 이상 릴리스)을 모두 지원하며, XML, MPP 및 **10개 이상의** 다른 형식으로 내보낼 수 있어 서버에서 자동화된 대량 캘린더 생성을 가능하게 하기 때문입니다.

## 전제 조건
- **Java Development Kit (JDK) 8 이상**이 설치되고 **구성**되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리 – [공식 웹사이트](https://releases.aspose.com/tasks/java/)에서 다운로드하고 JAR를 프로젝트 클래스패스에 추가하십시오.  
- 원하는 IDE 또는 빌드 도구(Maven/Gradle).

## 단계별 가이드

### 단계 1: 필요한 Aspose.Tasks 패키지 가져오기
먼저, Aspose.Tasks 클래스를 가져와 프로젝트와 캘린더를 작업할 수 있도록 합니다.

```java
import com.aspose.tasks.*;
```

### 단계 2: 데이터 디렉터리 경로 설정
생성된 프로젝트 파일이 기록될 위치를 정의합니다. 자리표시자를 머신의 절대 경로나 상대 경로로 교체하십시오.

```java
String dataDir = "Your Data Directory";
```

### 단계 3: 새로운 Project 인스턴스 생성
`Project`는 메모리 내에서 Microsoft Project 파일을 나타내는 핵심 클래스입니다.

```java
Project prj = new Project();
```

### 단계 4: 추가하려는 캘린더 정의
`Calendar`는 프로젝트의 작업일, 예외 및 작업 시간을 정의하는 일정입니다.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **팁:** 캘린더를 추가한 후 `cal1.getWeekDays().add(...)`로 작업일을 맞춤 설정하고 `cal1.getBaseCalendar().setWorkingTime(...)`으로 일일 작업 시간을 설정할 수 있습니다.

### 단계 5: 프로젝트 저장 (XML로 저장)
`SaveFileFormat.Xml`은 Aspose.Tasks에게 프로젝트를 XML 형식으로 기록하도록 지시합니다.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 단계 6: 완료 메시지 표시
작업이 성공적으로 완료되었음을 사용자에게 알립니다.

```java
System.out.println("Process completed Successfully");
```

이 여섯 단계만 따라 하면 **프로젝트에 캘린더를 추가**하고 결과를 XML 파일로 저장할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **`prj.getCalendars()`에서 NullPointerException** | Project 객체가 올바르게 초기화되지 않았습니다. | `new Project()`를 호출한 후 캘린더에 접근하도록 하십시오. |
| **저장 시 파일을 찾을 수 없음** | `dataDir`이 존재하지 않는 폴더를 가리키고 있습니다. | 먼저 디렉터리를 생성하거나 절대 경로를 사용하십시오. |
| **캘린더 이름이 “no info”로 표시됨** | 샘플에서 자리표시자 이름을 사용했습니다. | 일정에 맞는 의미 있는 이름(예: “US Holiday Calendar”)으로 교체하십시오. |
| **저장된 XML을 MS Project에서 열 수 없음** | 구버전 Aspose.Tasks를 사용하고 있습니다. | 최신 Aspose.Tasks for Java 릴리스로 업데이트하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 여러 예외가 있는 복잡한 캘린더를 처리할 수 있나요?**  
A: 예 — 캘린더를 추가한 후 `WeekDay`와 `Exception` 클래스를 사용해 예외, 작업 시간 및 비작업일을 정의할 수 있습니다.

**Q: 새 캘린더를 특정 작업에 할당할 수 있나요?**  
A: 물론 가능합니다. `prj.getRootTask().getChildren().add("Task Name")`로 작업을 가져온 뒤 `task.set(Tsk.CALENDAR, cal3);`를 설정하십시오.

**Q: 라이브러리가 MPP와 같은 다른 형식으로 저장을 지원하나요?**  
A: 예. 필요에 따라 `SaveFileFormat.Xml`을 `SaveFileFormat.Mpp` 또는 `SaveFileFormat.P6`으로 교체하면 됩니다; Aspose.Tasks는 **12**개의 출력 형식을 지원합니다.

**Q: 개발 빌드에 라이선스가 필요합니까?**  
A: 테스트에는 임시 평가 라이선스로 충분하지만, 실제 배포에는 정식 라이선스가 필요합니다.

**Q: 문제가 발생하면 어디에서 도움을 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼이 훌륭한 자료입니다: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**마지막 업데이트:** 2026-08-03  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [MS Project 캘린더에서 평일 정의하기 – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks로 Java 프로젝트 캘린더 설정](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java로 사용자 정의 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}