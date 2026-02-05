---
date: 2026-02-05
description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 시간을 추출함으로써 작업일을 결정하고
  작업 기간을 계산하는 방법을 배워보세요.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks로 근무일 및 근무시간 결정
url: /ko/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 작업일 및 작업시간 결정하기

## 소개
프로젝트 캘린더 관리 는 성공적인 프로젝트 계획의 핵심 요소입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **작업일을 결정**하고 **작업시간을 추출**하는 방법을 배웁니다. 가이드를 끝까지 따라 하면 **작업 기간을 계산**하고, 작업시간을 사용자 정의하며, 필요한 데이터를 가져오기 위해 **MPP 파일을 로드**할 수 있게 됩니다. 또한 Microsoft Project가 설치되지 않은 상태에서도 **MS Project 파일을 읽을 수** 있어, 모든 플랫폼에서 자동화가 가능함을 확인할 수 있습니다.

## 빠른 답변
- **“작업일을 결정한다”는 무엇을 의미합니까?** 주어진 작업에 대해 캘린더 날짜 중 작업일로 간주되는 날짜를 식별하는 것을 의미합니다.  
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Tasks for Java는 MS Project 파일 작업을 위한 완전한 기능을 갖춘 API를 제공합니다.  
- **구현에 얼마나 걸리나요?** 기본 추출의 경우 일반적으로 10–15분 정도 소요됩니다.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **작업시간을 사용자 정의할 수 있나요?** 예 – 캘린더를 수정하고, 휴일을 추가하며, 사용자 정의 작업시간 범위를 설정할 수 있습니다.  

## “작업일을 결정한다”는 무엇인가요?
작업이 일정에 잡히면, 프로젝트 캘린더는 어떤 날이 작업일이고 어떤 날이 비작업일(주말, 휴일)인지를 정의합니다. 작업일을 결정한다는 것은 해당 캘린더를 조회하여 작업이 수행될 수 있는 정확한 날짜를 파악하는 것으로, 정확한 **작업 기간 계산**에 필수적입니다.

## 작업시간을 가져오기 위해 Aspose.Tasks를 사용하는 이유는?
- **Microsoft Project가 필요 없음** – Java 코드에서 직접 MS Project 파일을 읽을 수 있습니다.  
- **전체 캘린더 지원** – 기본, 리소스 및 작업 캘린더를 포함합니다.  
- **고성능** – 대규모 프로젝트를 빠르게 처리합니다.  
- **풍부한 문서** – 예제와 API 레퍼런스를 쉽게 확인할 수 있습니다.

## 전제 조건
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. 기본 Java 프로그래밍 지식.  

## 패키지 가져오기
First, import the core Aspose.Tasks namespace:

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks로 MPP 파일을 로드하는 방법은?
프로젝트 파일을 로드하는 것은 모든 캘린더 분석의 첫 단계입니다. API를 사용하면 **MPP 파일을 로드**하는 코드를 한 줄로 작성할 수 있으며, MS Project UI가 필요하지 않습니다.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 작업 및 캘린더 정보 가져오기
분석하려는 작업을 선택하고 해당 작업에 연결된 캘린더를 가져옵니다. 여기에서 작업의 **작업시간을 가져옵니다**.

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 시작 및 종료 날짜 정의
**작업일을 결정**하려는 시간 범위를 설정합니다. 작업의 시작 및 종료 날짜를 사용하면 관련 기간만 평가할 수 있습니다.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 날짜 순회
작업 기간의 각 날짜를 순회합니다. 필요에 따라 나중에 **작업시간을 사용자 정의**하는 데 도움이 되는 루프입니다.

```java
java.util.Calendar tempDate = calStartDate;
```

## 기간 계산
순회 중에 각 날짜가 작업일인지 확인하고, 작업시간을 합산한 뒤, 최종적으로 작업의 기간을 분, 시간, 일 단위로 계산합니다. 이 단계에서는 **작업일을 계산**하고 **작업 기간을 계산**하는 방법을 프로그래밍으로 보여줍니다.

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

## 작업시간 및 휴일을 사용자 정의하는 방법
Aspose.Tasks를 사용하면 캘린더의 작업시간 범위를 수정하고 휴일과 같은 예외를 추가할 수 있습니다. `taskCalendar.addWorkingTime()` 또는 `taskCalendar.addException()`을 호출하여 조직 정책에 맞게 일정을 조정할 수 있습니다. 기본 9‑5 일정이 실제와 맞지 않을 때 유용합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **작업의 캘린더가 `null` 반환** | 작업에 실제로 캘린더가 할당되어 있는지 확인하십시오; 그렇지 않으면 프로젝트의 기본 캘린더를 상속합니다. |
| **휴일 때문에 기간이 잘못 계산됨** | 휴일이 작업 캘린더 또는 프로젝트 기본 캘린더에 정의되어 있는지 확인하십시오. |
| **시간대 불일치** | 필요한 경우 `java.util.TimeZone`을 사용하여 캘린더의 시간대를 시스템과 맞추십시오. |

## 자주 묻는 질문
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 작업, 리소스 및 캘린더를 포함한 복잡한 프로젝트 구조를 처리하기 위한 포괄적인 지원을 제공합니다.

### Q: Aspose.Tasks for Java가 다양한 버전의 MS Project와 호환되나요?
A: 물론입니다. Aspose.Tasks for Java는 다양한 버전의 MS Project를 지원하여 다양한 환경에서 호환성을 보장합니다.

### Q: 프로젝트 캘린더에서 작업시간 및 휴일을 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks for Java API를 사용하여 프로젝트 요구사항에 맞게 작업시간 및 휴일을 쉽게 사용자 정의할 수 있습니다.

### Q: Aspose.Tasks for Java가 지원 및 문서를 제공하나요?
A: 예, Aspose.Tasks for Java는 풍부한 문서와 전용 지원 포럼을 제공하여 개발자가 기능을 효과적으로 활용할 수 있도록 돕습니다.

### Q: Aspose.Tasks for Java의 체험판이 있나요?
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험판을 이용할 수 있습니다.

## 결론
이 가이드에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **작업일을 결정**, **작업시간을 가져오기**, 그리고 **작업 기간을 계산**하는 방법을 보여주었습니다. 위 단계들을 따르면 일정 분석을 자동화하고, 캘린더를 사용자 정의하며, 프로젝트 계획을 정확하고 최신 상태로 유지할 수 있습니다. 이제 **MS Project** 데이터를 **읽고**, **MPP 파일을 로드**하며, Microsoft Project 없이도 정밀한 기간 계산을 수행할 수 있는 도구를 갖추게 되었습니다.

---

**마지막 업데이트:** 2026-02-05  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}