---
date: 2026-08-13
description: Aspose.Tasks for Java를 사용하여 calendar에 휴일을 추가하고, 해당 calendar를 프로젝트에 할당한
  뒤, MS Project 파일을 MPP로 저장하는 방법을 배웁니다.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aspose.Tasks에서 calendar를 MPP 형식으로 업데이트하기
og_description: Aspose.Tasks for Java를 사용하여 calendar에 휴일을 추가하고, 이를 프로젝트에 할당한 뒤, 일정을
  MPP로 변환합니다. 단계별 자동화 방법을 배워보세요.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Aspose.Tasks를 사용하여 calendar에 휴일을 추가하고 MPP로 저장하기
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks를 사용하여 calendar에 휴일을 추가하고 MPP로 저장하기
url: /ko/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 휴일을 캘린더에 추가하고 Aspose.Tasks로 MPP 저장

## 소개

현대 프로젝트 관리에서는 종종 **캘린더에 휴일 추가** 파일이 필요하고, **MS Project 캘린더**를 만들며, 그런 다음 기본 MPP 형식으로 일정을 공유합니다. 여러 소스에서 타임라인을 통합하거나 레거시 데이터를 마이그레이션하든, 프로그래밍 방식으로 캘린더를 생성하면 수동 오류를 없애고 전달 속도를 높일 수 있습니다. 이 튜토리얼에서는 MS Project에서 캘린더를 생성하고, 휴일로 사용자 지정하며, **프로젝트에 캘린더 할당**, 마지막으로 Aspose.Tasks Java API를 사용해 **프로젝트를 MPP로 변환**하는 전체 과정을 안내합니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** 캘린더에 휴일을 추가하고, 이를 프로젝트에 할당한 뒤, Aspose.Tasks for Java를 사용해 결과를 MPP 파일로 저장합니다.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **필요한 Java 버전은 무엇입니까?** Java 8 이상 (JDK 8+).  
- **캘린더를 사용자 지정할 수 있나요?** 예 – 작업 시간, 예외 및 휴일을 추가할 수 있습니다.  
- **구현에 얼마나 걸립니까?** 기본 캘린더의 경우 약 10‑15 분 정도 소요됩니다.  

## “create calendar MS Project”란 무엇인가요?
캘린더 MS Project를 생성한다는 것은 Microsoft Project 파일 내에서 작업 일정에 영향을 주는 작업일, 작업시간 및 예외를 정의하는 것을 의미합니다. Aspose.Tasks를 사용하면 코드를 통해 이 캘린더를 구축하고, 휴일을 설정하며, MS Project UI를 열지 않고도 프로젝트에 삽입할 수 있습니다.

## 이 작업에 Aspose.Tasks를 사용하는 이유는 무엇인가요?
Aspose.Tasks를 사용해야 하는 이유는 완전한 Java 호환성을 제공하고 Microsoft Office가 필요 없으며, 코드를 통해 직접 네이티브 MPP 파일을 생성·저장할 수 있기 때문입니다. 이 라이브러리는 모든 캘린더 기능을 지원하고, 어떤 서버 환경에서도 작동하며, 10,000개 작업까지의 프로젝트를 1초 미만에 처리합니다.

## 필수 조건
1. **Java Development Kit (JDK) 8+** – `java -version` 명령이 1.8 이상을 표시하는지 확인하십시오.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose website](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 기타 편집기.  
4. **Basic Java knowledge** – 클래스, 메서드 및 파일 I/O에 익숙해야 합니다.  

## 캘린더에 휴일을 추가하는 방법
휴일을 추가하려면 새 `Calendar` 객체를 생성하고, 해당 객체의 `Exceptions` 컬렉션을 가져온 다음 각 휴일 날짜에 대해 `DateException` 항목을 추가합니다. `DateException`은 캘린더에서 단일 비작업 날짜 또는 기간을 나타냅니다. Aspose.Tasks는 이러한 날짜를 비작업일로 처리하여 작업이 정의된 휴일을 피하도록 일정이 잡히게 합니다.

### 1단계: 필요한 패키지 가져오기
먼저, Aspose.Tasks 클래스와 Java 유틸리티를 범위에 포함시킵니다.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 2단계: 데이터 디렉터리 설정
입력 템플릿과 출력 파일이 저장될 위치를 정의합니다. 자리표시자를 실제 머신의 경로로 교체하십시오.

```java
String dataDir = "Your Data Directory";
```

### 3단계: 입력 및 출력 파일 이름 정의
기존 MPP 파일(또는 빈 프로젝트)을 로드하고 결과를 새 파일에 기록합니다.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 4단계: 프로젝트를 로드하고 새 캘린더 추가
`Project` 클래스는 메모리 내의 MS Project 파일을 나타내며 해당 파일의 캘린더, 작업 및 리소스에 접근할 수 있게 합니다.

소스 파일에서 `Project` 인스턴스를 생성하고 **“Calendar 1”**이라는 이름의 캘린더를 추가합니다.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 5단계: 캘린더 사용자 지정 (선택 사항)
`Calendar` 객체는 프로젝트 일정에 대한 작업일, 작업시간 및 예외를 정의합니다.

특정 작업시간, 휴일 또는 예외가 필요하면 자체 헬퍼 메서드를 호출하십시오. 샘플에서는 `GetTestCalendar`를 자리표시자로 사용합니다.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** `cal1.getWeekDays()`를 직접 조작하여 요일별 작업 시간을 설정하거나, `cal1.getExceptions()`를 사용해 **캘린더에 휴일 추가**할 수 있습니다.

### 6단계: 캘린더를 프로젝트에 할당
프로젝트가 모든 일정 계산에 새로 만든 캘린더를 사용하도록 지정합니다.

```java
project.set(Prj.CALENDAR, cal1);
```

### 7단계: 프로젝트를 MPP로 저장
`SaveFileFormat` 열거형은 출력 형식을 지정하며, `Mpp`는 네이티브 Microsoft Project 형식을 나타냅니다.

이제 `SaveFileFormat.Mpp` 옵션으로 저장하여 **프로젝트를 MPP로 변환**합니다.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 8단계: 성공 완료 확인
간단한 콘솔 메시지를 통해 프로세스가 오류 없이 완료되었음을 확인할 수 있습니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 사용 사례
- **자동 일정 생성** 반복 프로젝트(예: 주간 스프린트)용.  
- **레거시 CSV 또는 Excel 캘린더 마이그레이션**을 통해 완전한 기능을 갖춘 MS Project 파일로 변환.  
- **서버 측 보고** 웹 서비스가 필요 시 MPP 파일을 반환하는 경우.  

## 문제 해결 및 일반적인 함정
| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir`가 존재하지 않는 폴더를 가리킴 | 디렉터리가 존재하는지 확인하거나 프로그래밍 방식으로 생성하십시오. |
| Calendar not applied to tasks | Tasks still reference the default calendar | `Prj.CALENDAR`를 설정한 후, 이전에 재정의된 경우 각 작업의 `Task.CALENDAR`도 업데이트하십시오. |
| Output file is 0 KB | Missing write permissions | JVM을 적절한 파일 시스템 권한으로 실행하거나 쓰기 가능한 경로를 선택하십시오. |

## 자주 묻는 질문
**Q: Aspose.Tasks for Java가 다양한 버전의 MS Project와 호환되나요?**  
A: 네, Aspose.Tasks는 Project 2007부터 Project 2024까지의 모든 Microsoft Project 파일 형식을 지원하며, 10개 이상의 버전을 포괄합니다.

**Q: 특정 프로젝트 요구사항에 따라 캘린더를 사용자 지정할 수 있나요?**  
A: 물론입니다. 작업일을 정의하고, 사용자 지정 작업 주를 설정하며, 휴일을 추가하고, 단일 프로젝트 파일 내에 여러 캘린더를 만들 수도 있습니다.

**Q: Aspose.Tasks for Java가 문제 해결 및 지원을 제공하나요?**  
A: 네, Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Aspose.Tasks for Java에 대한 무료 체험판이 있나요?**  
A: 네, 완전한 기능을 갖춘 무료 체험판을 이용할 수 있습니다 [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Aspose.Tasks for Java에 대한 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: Aspose 웹사이트를 통해 임시 라이선스를 요청할 수 있습니다 [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**마지막 업데이트:** 2026-08-13  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼
- [Aspose.Tasks for Java를 사용하여 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [MS Project 캘린더에서 평일 정의 방법 – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks for Java로 사용자 지정 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}