---
title: Aspose.Tasks를 사용하여 달력 예외에 대한 평일 정의
linktitle: Aspose.Tasks를 사용하여 달력 예외에 대한 평일 정의
second_title: Aspose.Tasks 자바 API
description: 정확한 프로젝트 일정을 잡기 위해 Aspose.Tasks를 사용하여 Java 프로젝트에서 달력 예외에 대한 평일을 정의하는 방법을 알아보세요.
type: docs
weight: 11
url: /ko/java/calendar-exceptions/define-weekdays/
---
### 소개
프로젝트 관리에서 달력에 대한 예외를 정의하는 것은 프로젝트 타임라인 내에서 비표준 근무일이나 휴일을 정확하게 표현하는 데 중요합니다. Aspose.Tasks for Java는 휴일이나 특별 근무일과 같은 예외 정의를 포함하여 달력을 효율적으로 관리할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 달력 예외에 대한 평일을 정의하는 방법을 살펴보겠습니다.
### 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): Java 개발을 위해 선호하는 IDE를 선택하세요.

## 패키지 가져오기
시작하려면 Java 프로젝트에서 Aspose.Tasks에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;

```

## 1단계: 데이터 디렉터리 정의
프로젝트 파일이 저장될 데이터 디렉터리의 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: 프로젝트 인스턴스 생성
프로젝트 데이터 작업을 시작하려면 Project 클래스의 새 인스턴스를 초기화하세요.
```java
Project project = new Project();
```
## 3단계: 달력 정의
예외가 추가될 달력을 정의하는 달력 개체를 만듭니다.
```java
Calendar cal = project.getCalendars().add("Calendar1");
```
## 4단계: 평일 예외 정의
달력 내에서 공휴일 등 평일에 대한 예외를 정의합니다.
```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```
## 5단계: 프로젝트 저장
정의된 달력 예외와 함께 프로젝트 파일을 저장합니다.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 결론
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 프로젝트의 달력 예외에 대한 평일을 효율적으로 정의할 수 있습니다. 휴일이나 특별 근무일과 같은 예외를 관리하면 프로젝트 일정을 정확하게 계획하고 표시할 수 있습니다.
## 자주 묻는 질문
### Q: 동일한 달력 내에서 다양한 평일에 대해 여러 예외를 정의할 수 있습니까?
A: 예, Aspose.Tasks for Java를 사용하여 단일 달력 내에서 다양한 평일에 대한 여러 예외를 정의할 수 있습니다.
### Q: Aspose.Tasks for Java는 다른 Java IDE와 호환됩니까?
A: Aspose.Tasks for Java는 IntelliJ IDEA, Eclipse, NetBeans 등 널리 사용되는 Java IDE와 호환됩니다.
### Q: 일일 예외 이외의 예외 유형을 사용자 정의할 수 있습니까?
A: 물론 Aspose.Tasks for Java는 일일 예외에 국한되지 않고 다양한 기준에 따라 예외를 정의할 수 있는 유연성을 제공합니다.
### Q: 프로젝트 요구 사항에 따라 예외를 동적으로 처리하려면 어떻게 해야 합니까?
A: Aspose.Tasks for Java에서 제공하는 광범위한 API를 사용하여 동적 프로젝트 요구 사항에 따라 프로그래밍 방식으로 예외를 처리할 수 있습니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음 사이트에서 Aspose.Tasks for Java의 무료 평가판을 이용할 수 있습니다.[웹사이트](https://releases.aspose.com/).
