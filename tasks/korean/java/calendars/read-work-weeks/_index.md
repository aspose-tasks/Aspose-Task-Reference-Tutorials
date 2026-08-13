---
date: 2026-08-13
description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 workweeks를 읽는 방법을 배웁니다.
  단계별 가이드를 따라 코드 예제와 문제 해결 팁을 확인하세요.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks로 캘린더에서 Work Weeks 읽기
og_description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 workweeks를 읽는 방법. 설정
  단계, 코드 스니펫 및 문제 해결 팁이 포함된 간결한 튜토리얼을 따라하세요.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Aspose.Tasks를 사용하여 MS 캘린더에서 workweeks를 읽는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Aspose.Tasks를 사용하여 MS 캘린더에서 workweeks를 읽는 방법
url: /ko/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS 캘린더에서 작업 주 읽는 방법

## 소개
이 튜토리얼에서는 Java용 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 캘린더에서 **작업 주를 읽는 방법**을 배웁니다. 보고 대시보드를 구축하든, ERP 시스템과 일정 동기화를 하든, 분석을 위한 데이터 추출을 자동화하든, 프로그램matically 작업 주 정의에 접근하면 수많은 수작업 시간을 절감할 수 있습니다. Aspose.Tasks는 **50개 이상의 입력 및 출력 형식**을 지원하며 전체 파일을 메모리에 로드하지 않고도 수백 페이지 규모의 프로젝트 파일을 처리할 수 있어 유연성과 성능을 모두 제공합니다.

## 빠른 답변
- **“작업 주 읽기”가 의미하는 것은 무엇인가요?** 프로젝트 파일에서 작업 주 정의(날짜 및 일일 작업 시간 규칙)를 Java 코드로 추출하는 것을 의미합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java(무료 체험 제공).  
- **개발에 라이선스가 필요합니까?** 테스트에는 체험판을 사용할 수 있지만, 실제 배포에는 상용 라이선스가 필요합니다.  
- **지원되는 파일 형식은 무엇인가요?** *.mpp*와 Project XML 파일을 모두 처리하며, 외에도 50개 이상의 가져오기/내보내기 형식을 지원합니다.  
- **구현에 걸리는 시간은 얼마나 되나요?** 라이브러리를 설정하면 보통 10분 미만 소요됩니다.

## MS Project에서 작업 주란 무엇인가요?
작업 주는 특정 기간 동안 리소스가 언제 사용 가능한지를 정의하는 캘린더 규칙입니다. 시작 날짜, 종료 날짜 및 일일 작업 시간 구간(예: 오전 9시–오후 5시)을 포함합니다. MS Project에서는 각 캘린더에 여러 작업 주를 포함시켜 휴일, 교대 근무 패턴 또는 계절 일정 등을 모델링할 수 있습니다.

## Aspose.Tasks는 캘린더에서 작업 주를 어떻게 읽나요?
Aspose.Tasks는 `Calendar` 객체의 `WorkWeekCollection`을 노출합니다. `Project` 인스턴스를 생성하고 원하는 캘린더(UID 또는 이름으로)를 선택한 뒤 `WorkWeekCollection`을 순회하면 각 작업 주의 레이블, 적용 날짜 범위 및 상세 일일 작업 시간 슬롯을 가져올 수 있습니다. API는 모든 날짜‑시간 변환을 자동으로 처리하고 프로젝트의 시간대 설정을 자동으로 적용합니다.

## 왜 Microsoft Project 캘린더에서 Java로 작업 주를 읽어야 할까요?
작업 주를 프로그래밍 방식으로 읽으면 수동 복사‑붙여넣기를 없앨 수 있을 뿐만 아니라, 하위 시스템(ERP, HR, 보고 등)이 정확히 동일한 일정 규칙을 사용하도록 보장하고, 여러 프로젝트에 걸쳐 일관성을 유지할 수 있습니다. 자동화는 인간 오류를 줄이고 통합 파이프라인 속도를 높이며, 특히 매일 밤 수십 개의 프로젝트 파일을 처리해야 할 때 큰 도움이 됩니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 버전 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 공식 사이트에서 최신 JAR를 다운로드하십시오: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **샘플 프로젝트 파일** (`ReadWorkWeeksInformation.mpp`)을 컴퓨터의 알려진 폴더에 배치합니다.

## 패키지 가져오기
먼저 캘린더와 작업 주와 상호 작용하는 데 필요한 클래스를 가져옵니다.

`Project`는 Microsoft Project 파일을 나타내고, `Calendar`는 해당 캘린더를 제공하며, `WorkWeek`는 작업 주를 정의하고, `WeekDay`는 하루를 나타냅니다.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 단계 1: 데이터 디렉터리 설정
`.mpp` 파일이 들어 있는 폴더를 정의합니다. 자리 표시자를 실제 머신의 경로로 교체하십시오.

```java
String dataDir = "Your Data Directory";
```

## 단계 2: Project 인스턴스를 생성하고 캘린더에 접근하기
`Project` 클래스는 Microsoft Project 파일을 나타내며 캘린더, 작업, 리소스 등 데이터 구조에 접근할 수 있게 해줍니다.  
`Project` 객체를 인스턴스화하고, 원하는 캘린더를 UID로 선택한 뒤 해당 캘린더의 `WorkWeekCollection`을 가져옵니다:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** 캘린더 UID가 확실하지 않다면 `project.getCalendars()`를 순회하면서 각 캘린더의 이름과 UID를 먼저 출력해 보세요.

## 단계 3: 작업 주 반복하기
`WorkWeek` 클래스는 시작/종료 날짜와 일일 작업 시간 설정을 포함하는 작업 주 정의를 캡슐화합니다.  
각 `WorkWeek`를 순회하면서 이름, 시작/종료 날짜 및 일일 작업 시간을 표시합니다:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**보게 될 내용:** 콘솔에 각 작업 주의 레이블(예: “Standard”), 적용 날짜 범위가 출력되고, 각 요일에 대한 정확한 작업 시간이 표시됩니다.

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| `calendar`에 접근할 때 NullPointerException | 잘못된 UID이거나 캘린더가 존재하지 않음 | `project.getCalendars().size()`로 UID를 확인하고 먼저 사용 가능한 캘린더를 나열하십시오. |
| 작업 주에 대한 출력이 없음 | 선택한 캘린더에 사용자 정의 작업 주가 없고(기본값 사용) | 기본 캘린더(`project.getDefaultCalendar()`)를 사용하거나 프로그래밍으로 작업 주를 생성하십시오. |
| 날짜 형식이 이상하게 보임 | `System.out.println`이 기본 `java.util.Date` 형식을 사용함 | 필요에 따라 `SimpleDateFormat`을 적용하여 날짜를 포맷하십시오. |

## 자주 묻는 질문
**Q: Aspose.Tasks for Java를 사용하여 작업 주 정보를 수정할 수 있나요?**  
A: 예. API는 `addWorkWeek()`, `removeWorkWeek()` 및 속성 세터를 제공하여 이름, 날짜 및 작업 시간을 변경할 수 있습니다.

**Q: Aspose.Tasks는 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. Project 98부터 최신 릴리스까지의 MPP 파일과 Project XML 파일을 모두 지원합니다.

**Q: Aspose.Tasks를 다른 Java 프레임워크와 통합할 수 있나요?**  
A: 예. 순수 Java 라이브러리이므로 Spring, Jakarta EE 또는 기타 프레임워크와 함께 사용할 수 있습니다.

**Q: Aspose.Tasks 체험판이 있나요?**  
A: 예, 공식 사이트에서 30일 무료 체험판을 다운로드할 수 있습니다: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks 지원을 어디서 받을 수 있나요?**  
A: Aspose 커뮤니티 포럼이 가장 좋은 곳입니다: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**마지막 업데이트:** 2026-08-13  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용하여 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose.Tasks를 사용한 캘린더 예외 가져오기 – Java 튜토리얼](/tasks/java/calendar-exceptions/retrieve/)
- [MS Project에서 Aspose.Tasks로 캘린더 설정 및 요일 정의 방법](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}