---
title: Aspose.Tasks를 사용하여 달력에서 평일 정의
linktitle: Aspose.Tasks를 사용하여 달력에서 평일 정의
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS Project Calendar에서 평일을 정의하는 방법을 알아보세요. 근무일과 시간을 손쉽게 맞춤설정하세요.
weight: 12
url: /ko/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 달력에서 평일 정의

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력에서 평일을 정의하는 과정을 안내합니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 아직 하지 않았다면.
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/). 설명서에 제공된 설치 지침을 따르십시오.

## 패키지 가져오기
시작하려면 Java 프로젝트에서 Aspose.Tasks 작업에 필요한 필수 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## 1단계: 프로젝트 인스턴스 생성
작업할 MS 프로젝트 파일을 나타내는 Project 개체를 인스턴스화합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## 2단계: 달력 정의
새 달력 인스턴스를 만들고 프로젝트에 추가합니다.
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## 3단계: 근무일 추가
기본 시간을 사용하여 월요일부터 목요일까지 추가하여 근무일을 정의합니다.
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## 4단계: 맞춤형 근무일 설정
토요일과 일요일을 근무일로 정의합니다.
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## 5단계: 짧은 근무일 설정
맞춤형 근무 시간을 사용하여 금요일을 짧은 근무일로 설정하세요.
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## 6단계: 프로젝트 저장
수정된 프로젝트를 XML 파일에 저장합니다.
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 결론
축하해요! Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력에서 평일을 성공적으로 정의했습니다. 이제 이 기능을 Java 애플리케이션에 통합하여 프로그래밍 방식으로 MS 프로젝트 파일을 조작할 수 있습니다.
## FAQ
### Q1: Aspose.Tasks for Java를 사용하여 사용자 지정 휴무일을 정의할 수 있나요?
 A: 예, 다음을 설정하여 맞춤형 휴무일을 정의할 수 있습니다.`DayWorking` 재산`false` 해당 평일에 대해.
### Q2: 달력에 공휴일을 어떻게 추가하나요?
 A: 인스턴스를 생성하여 공휴일을 추가할 수 있습니다.`CalendarExceptions`휴무일을 지정합니다.
### Q3: Aspose.Tasks는 다른 버전의 MS 프로젝트 파일과 호환됩니까?
A: 예, Aspose.Tasks는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 MS 프로젝트 파일을 지원합니다.
### Q4: MS 프로젝트 파일의 기존 달력을 수정할 수 있습니까?
A: 예, 달력이 포함된 기존 프로젝트를 로드하고 수정한 다음 변경 사항을 원본 파일에 다시 저장할 수 있습니다.
### Q5: Aspose.Tasks는 반복 작업을 지원합니까?
A: 예, Aspose.Tasks를 사용하면 반복 패턴 및 기간 정의를 포함하여 반복 작업을 수행할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
