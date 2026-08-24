---
date: 2026-08-24
description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 working hours를 추출함으로써 holidays
  calendar를 추가하고 working days를 결정하며 task duration을 계산하는 방법을 배웁니다.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: 휴일 캘린더를 추가하고 근무일을 결정하는 방법
og_description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 working hours를 추출함으로써
  holidays calendar를 추가하고 working days를 결정하며 task duration을 계산하는 방법을 배웁니다.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: 휴일 캘린더를 추가하고 근무일을 결정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: 휴일 캘린더를 추가하고 근무일을 결정하는 방법
url: /ko/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 휴일 캘린더 추가 및 작업일 결정 방법

프로젝트 캘린더 관리는 성공적인 프로젝트 계획의 핵심 부분입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **휴일 캘린더 추가**, **작업일 결정**, **작업 시간 추출**을 수행합니다. 가이드가 끝날 때쯤이면 **작업 기간 계산**, 작업 시간 사용자 정의, 그리고 Microsoft Project를 설치하지 않고도 필요한 데이터를 가져오기 위해 **MPP 파일 로드**를 신뢰할 수 있게 됩니다.

## 빠른 답변
- **“작업일 결정”이 의미하는 바는?** 주어진 작업에 대해 작업일로 간주되는 캘린더 날짜를 식별하는 것을 의미합니다.  
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Tasks for Java는 MS Project 파일 작업을 위한 완전한 기능의 API를 제공합니다.  
- **구현에 얼마나 걸리나요?** 기본 추출의 경우 일반적으로 10–15분 정도 소요됩니다.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 사용을 위해서는 상업용 라이선스가 필요합니다.  
- **작업 시간을 사용자 정의할 수 있나요?** 예 – 캘린더를 수정하고, 휴일을 추가하며, 사용자 정의 작업 시간 범위를 설정할 수 있습니다.  

## “작업일 결정”이란 무엇인가요?
**작업일 결정**은 프로젝트 캘린더를 조회하여 날짜가 작업일인지 비작업일(주말, 휴일 또는 사용자 정의 예외)인지 확인하는 것을 의미합니다. 이 정보는 **작업 기간 계산**의 정확성을 위해 필수적인데, 작업일만이 작업의 경과 시간에 기여하기 때문입니다.

## 작업 시간을 가져오기 위해 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks는 Microsoft Project를 설치하지 않고도 MS Project 파일을 읽을 수 있게 하여 모든 플랫폼에서 자동화를 가능하게 합니다. 또한 고성능 처리, 광범위한 형식 지원 및 자세한 문서를 제공합니다.  

- **전체 캘린더 지원** – 기본, 리소스 및 작업 캘린더 모두에 접근할 수 있습니다.  
- **고성능** – 표준 2.5 GHz CPU에서 **10,000개 이상의 작업**을 2초 미만으로 처리할 수 있습니다.  
- **광범위한 형식 지원** – **50개 이상의 입력 및 출력 형식**을 지원하며, 여기에는 MPP, MPX, XML, Primavera 등이 포함됩니다.  
- **포괄적인 문서** – 코드 샘플, API 레퍼런스 및 커뮤니티 포럼이 모두 제공됩니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR를 [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. 기본 Java 프로그래밍 지식.  

## 패키지 가져오기
`Project` 클래스는 메모리 내에서 단일 MS Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 시작하기 전에 필요한 네임스페이스를 가져오세요:

패키지 가져오기

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks로 MPP 파일을 로드하는 방법은?
`Project` 클래스는 MS Project 파일을 로드하고 해당 데이터에 접근할 수 있게 합니다. 한 줄의 코드로 프로젝트 파일을 로드하면 UI나 COM 상호 운용이 필요하지 않습니다. 이 간단한 단계로 캘린더, 작업 및 리소스에 완전히 접근할 수 있습니다.

MPP 파일 로드

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 작업 및 캘린더 정보 가져오기
`Task`는 프로젝트 작업을 나타내며, `Calendar`는 작업 시간 규칙을 정의합니다. 분석하려는 작업을 선택하고 해당 캘린더를 가져옵니다. `Task` 객체는 `getStart()` 및 `getFinish()` 메서드를 제공하고, `Calendar` 객체는 작업 시간 정의를 노출합니다.

작업 및 캘린더 가져오기

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 시작 및 종료 날짜 정의
`Date` 객체는 캘린더 분석을 위한 시간 창을 지정합니다. **작업일을 결정**하려는 시간 창을 설정하십시오. 작업의 시작 및 종료 날짜를 사용하면 관련 기간만 평가하게 됩니다.

날짜 정의

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 날짜 반복
`for` 루프를 사용하여 날짜 범위의 각 날짜를 반복할 수 있습니다. 작업 기간의 각 날짜를 순회합니다. 이 루프를 통해 필요에 따라 **작업 시간을 사용자 정의**할 수 있으며, 총 작업 시간을 계산하는 기반이 됩니다.

날짜 순회

```java
java.util.Calendar tempDate = calStartDate;
```

## 기간 계산
`Duration`은 반복을 통해 계산된 총 작업 시간을 집계합니다. 반복 중에 각 날짜가 작업일인지 확인하고, 작업 시간을 합산한 뒤, 최종적으로 작업의 기간을 분, 시간, 일 단위로 계산합니다. 이는 프로그램matically **작업일을 계산**하고 **작업 기간을 계산**하는 방법을 보여줍니다.

기간 계산

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## 작업 시간 및 휴일 사용자 정의 방법은?
캘린더의 작업 시간 범위를 수정하고 휴일과 같은 예외를 추가할 수 있습니다. `taskCalendar.addWorkingTime()`을 사용하여 새로운 작업 기간을 설정하고 `taskCalendar.addException()`을 사용하여 휴일을 삽입하십시오. 기본 9‑5 일정이 조직 정책과 일치하지 않을 때 유용합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **작업이 캘린더에 대해 `null`을 반환** | 작업에 실제로 캘린더가 할당되어 있는지 확인하십시오. 그렇지 않으면 프로젝트의 기본 캘린더를 상속합니다. |
| **휴일 때문에 기간이 잘못 계산됨** | 휴일이 작업 캘린더 또는 프로젝트 기본 캘린더에 정의되어 있는지 확인하십시오. |
| **시간대 불일치** | 필요한 경우 `java.util.TimeZone`을 사용하여 캘린더의 시간대를 시스템과 맞추십시오. |

## 자주 묻는 질문
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 작업, 리소스 및 캘린더를 포함한 복잡한 프로젝트 구조를 처리하기 위한 포괄적인 지원을 제공합니다.

### Q: Aspose.Tasks for Java가 다양한 MS Project 버전과 호환되나요?
A: 물론입니다. Aspose.Tasks for Java는 다양한 MS Project 버전을 지원하여 다양한 환경에서 호환성을 보장합니다.

### Q: 프로젝트 캘린더에서 작업 시간 및 휴일을 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks for Java API를 사용하여 프로젝트 요구 사항에 따라 작업 시간 및 휴일을 쉽게 사용자 정의할 수 있습니다.

### Q: Aspose.Tasks for Java가 지원 및 문서를 제공하나요?
A: 예, Aspose.Tasks for Java는 풍부한 문서와 전용 지원 포럼을 제공하여 개발자가 기능을 효과적으로 활용하도록 돕습니다.

### Q: Aspose.Tasks for Java의 체험 버전이 있나요?
A: 예, [Aspose releases page](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험 버전을 이용할 수 있습니다.

## 결론
이 가이드에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **휴일 캘린더 추가**, **작업일 결정**, **작업 시간 조회**, **작업 기간 계산**을 수행하는 방법을 보여주었습니다. 위 단계들을 따라 하면 일정 분석을 자동화하고, 캘린더를 사용자 정의하며, 프로젝트 계획을 정확하고 최신 상태로 유지할 수 있습니다. 이제 **MS Project** 데이터를 **읽고**, **MPP 파일을 로드**하며, Microsoft Project 없이도 정밀한 기간 계산을 수행할 수 있는 도구를 갖추었습니다.

---

**마지막 업데이트:** 2026-08-24  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose.Tasks로 캘린더에 휴일 추가 및 MPP로 저장](/tasks/java/calendars/update-to-mpp/)
- [Aspose.Tasks for Java로 사용자 정의 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}