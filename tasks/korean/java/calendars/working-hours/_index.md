---
date: 2025-12-05
description: Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 작업 시간을 추출함으로써 작업일을 결정하고
  작업 기간을 계산하는 방법을 배웁니다.
language: ko
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 작업일 및 작업시간 결정
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 작업일 및 작업시간 결정하기

## 소개
프로젝트 캘린더 관리​는 성공적인 프로젝트 계획의 핵심 요소입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **작업일을 결정**하고 **작업시간을 추출**하는 방법을 배웁니다. 가이드를 마치면 **작업 기간을 계산**하고, 작업 시간을 사용자 정의하며, 필요한 데이터를 가져오기 위해 **MPP 파일을 로드**하는 방법을 익히게 됩니다.

## 빠른 답변
- **“작업일을 결정한다”는 의미는?** 작업이 수행될 수 있는 캘린더 날짜를 식별하는 것을 의미합니다.  
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Tasks for Java는 MS Project 파일을 다루기 위한 완전한 API를 제공합니다.  
- **구현에 얼마나 걸리나요?** 기본 추출의 경우 일반적으로 10~15 분 정도 소요됩니다.  
- **라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **작업시간을 사용자 정의할 수 있나요?** 예 – 캘린더를 수정하고, 휴일을 추가하며, 사용자 정의 작업 시간 범위를 설정할 수 있습니다.

## “작업일을 결정한다”는 의미는?
작업이 일정에 배정될 때, 프로젝트 캘린더는 어떤 날이 작업일이고 어떤 날이 비작업일(주말, 휴일)인지를 정의합니다. 작업일을 결정한다는 것은 해당 캘린더를 조회하여 정확히 언제 작업이 가능한지를 파악하는 것으로, **작업 기간을 정확히 계산**하는 데 필수적입니다.

## 작업시간을 가져오기 위해 Aspose.Tasks를 사용하는 이유
- **Microsoft Project가 필요 없음** – 모든 플랫폼에서 .MPP 파일을 직접 다룰 수 있습니다.  
- **전체 캘린더 지원** – 기본 캘린더, 리소스 캘린더, 작업 캘린더를 모두 포함합니다.  
- **고성능** – 대규모 프로젝트도 빠르게 처리합니다.  
- **풍부한 문서** – 예제와 API 레퍼런스가 충분히 제공됩니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [여기](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. 기본적인 Java 프로그래밍 지식.

## 패키지 가져오기
먼저 Aspose.Tasks 핵심 네임스페이스를 가져옵니다:

```java
import com.aspose.tasks.*;
```

## 1단계: MPP 파일 로드
프로젝트 파일을 **로드**하여 캘린더에 접근할 수 있도록 합니다:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 2단계: 작업 및 캘린더 정보 가져오기
분석하려는 작업을 선택하고 해당 작업에 연결된 캘린더를 가져옵니다. 여기서 **작업시간을 추출**합니다:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 3단계: 시작 및 종료 날짜 정의
**작업일을 결정**하려는 기간의 시작과 끝 날짜를 설정합니다:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 4단계: 날짜 순회
작업 기간 동안 각 날짜를 순회합니다. 필요에 따라 **작업시간을 사용자 정의**할 수 있도록 돕는 루프입니다:

```java
java.util.Calendar tempDate = calStartDate;
```

## 5단계: 기간 계산
순회하면서 각 날짜가 작업일인지 확인하고, 작업 시간을 합산한 뒤 최종적으로 작업의 기간을 분, 시간, 일 단위로 계산합니다:

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

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|------|--------|
| **작업의 캘린더가 `null` 반환** | 작업에 캘린더가 실제로 할당되어 있는지 확인하세요. 할당되지 않은 경우 프로젝트의 기본 캘린더를 상속합니다. |
| **휴일 때문에 기간이 잘못 계산됨** | 작업 캘린더 또는 프로젝트 기본 캘린더에 휴일이 정의되어 있는지 확인하세요. |
| **시간대 불일치** | 필요에 따라 `java.util.TimeZone`을 사용해 캘린더의 시간대를 시스템과 맞추세요. |

## 자주 묻는 질문
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 작업, 리소스, 캘린더 등 복잡한 프로젝트 구조를 포괄적으로 지원합니다.

### Q: Aspose.Tasks for Java가 다양한 MS Project 버전과 호환되나요?
A: 물론입니다. Aspose.Tasks for Java는 여러 버전의 MS Project와 호환되어 다양한 환경에서 사용할 수 있습니다.

### Q: 프로젝트 캘린더에서 작업시간과 휴일을 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks for Java API를 사용하면 프로젝트 요구 사항에 맞게 작업시간과 휴일을 손쉽게 커스터마이징할 수 있습니다.

### Q: Aspose.Tasks for Java가 지원 및 문서를 제공하나요?
A: 예, Aspose.Tasks for Java는 풍부한 문서와 전용 지원 포럼을 제공하여 개발자가 기능을 효과적으로 활용할 수 있도록 돕습니다.

### Q: Aspose.Tasks for Java 체험판을 사용할 수 있나요?
A: 예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks for Java 무료 체험판을 다운로드할 수 있습니다.

## 결론
이 가이드에서는 Aspose.Tasks for Java를 사용하여 MS Project 캘린더에서 **작업일을 결정**, **작업시간을 추출**, 그리고 **작업 기간을 계산**하는 방법을 보여주었습니다. 위 단계들을 따라 하면 일정 분석을 자동화하고, 캘린더를 사용자 정의하며, 프로젝트 계획을 정확하고 최신 상태로 유지할 수 있습니다.

---

**마지막 업데이트:** 2025-12-05  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}