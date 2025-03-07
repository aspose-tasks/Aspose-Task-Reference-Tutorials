---
title: Aspose.Tasks를 사용하여 달력에서 근무 시간 가져오기
linktitle: Aspose.Tasks를 사용하여 달력에서 근무 시간 가져오기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력에서 작업 시간을 쉽게 추출하세요. 프로젝트 관리 작업을 단순화합니다.
weight: 13
url: /ko/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 달력에서 근무 시간 가져오기

## 소개
효과적인 프로젝트 관리를 위해서는 프로젝트 일정을 관리하고 근무 시간을 추출하는 것이 필수적입니다. Aspose.Tasks for Java는 MS 프로젝트 달력에서 작업 시간을 쉽게 검색할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 라이브러리용 Aspose.Tasks가 다운로드되어 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍 언어에 대한 기본 이해.
## 패키지 가져오기
먼저 Aspose.Tasks for Java를 사용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
```
## 1단계: 프로젝트 파일 로드
MS 프로젝트 파일을 로드하여 시작하세요.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 2단계: 작업 및 달력 정보 검색
프로젝트에서 작업 및 일정 세부정보를 추출합니다.
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## 3단계: 시작 및 종료 날짜 정의
작업의 시작 및 종료 날짜를 설정합니다.
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## 4단계: 날짜 반복
작업 기간 내의 날짜를 반복합니다.
```java
java.util.Calendar tempDate = calStartDate;
```
## 5단계: 기간 계산
기간을 분, 시간, 일 단위로 계산합니다.
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
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력에서 근무 시간을 검색하는 방법을 다뤘습니다. 이러한 단계를 따르면 프로젝트 일정을 효율적으로 관리하고 작업 기간을 쉽게 계산할 수 있습니다.
## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있습니까?
A: 예, Aspose.Tasks for Java는 작업, 리소스 및 달력을 포함하여 복잡한 프로젝트 구조를 처리하기 위한 포괄적인 지원을 제공합니다.
### Q: Aspose.Tasks for Java는 다른 버전의 MS Project와 호환됩니까?
A: 물론 Aspose.Tasks for Java는 다양한 버전의 MS Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Q: 프로젝트 달력에서 근무 시간과 휴일을 맞춤 설정할 수 있나요?
A: 예, Aspose.Tasks for Java API를 사용하여 프로젝트 요구 사항에 따라 근무 시간과 휴일을 쉽게 사용자 정의할 수 있습니다.
### Q: Aspose.Tasks for Java는 지원과 문서를 제공합니까?
A: 예, Aspose.Tasks for Java는 개발자가 해당 기능을 효과적으로 활용하는 데 도움이 되는 광범위한 문서와 전용 지원 포럼을 제공합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 Aspose.Tasks for Java의 무료 평가판 버전에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
