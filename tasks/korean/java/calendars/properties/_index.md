---
title: Aspose.Tasks에서 MS 프로젝트 달력 속성 관리
linktitle: Aspose.Tasks에서 달력 속성 관리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java에서 MS Project 달력 속성을 관리하는 방법을 알아보세요. 이는 Java 애플리케이션 내의 달력에 대한 단계별 지침을 제공합니다.
weight: 10
url: /ko/java/calendars/properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 달력 속성 관리

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS Project 달력 속성을 관리하는 방법을 살펴보겠습니다. 달력 속성을 조작하는 방법을 이해하면 특정 요구 사항을 효율적으로 충족하도록 프로젝트 일정을 조정할 수 있습니다.
## 전제조건
계속하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### JDK(Java 개발 키트) 설치
시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
### Java 라이브러리용 Aspose.Tasks
 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설정하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.*;
```

## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 데이터 디렉토리 경로로.
## 2단계: 시간 단위 정의
```java
long OneSec = 1000; // 1000밀리초
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
여기서는 편의상 시간 단위를 정의합니다.
## 3단계: 프로젝트 데이터 로드
```java
Project project = new Project(dataDir + "project.xml");
```
지정된 XML 파일에서 MS 프로젝트 데이터를 로드합니다.
## 4단계: 달력을 통해 반복
```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // 기본 달력이 있는지 표시
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // 평일까지 반복
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```
이 루프는 프로젝트의 각 달력을 반복하여 UID, 이름, 기본 달력 및 각 날짜 유형의 작업 시간과 같은 속성을 표시합니다.

## 결론
이 튜토리얼을 따라 Aspose.Tasks for Java를 사용하여 MS Project 달력 속성을 관리하는 방법을 배웠습니다. 이러한 지식을 통해 프로젝트 일정을 효과적으로 맞춤화하고 프로젝트 요구 사항에 맞게 조정할 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 사용하여 프로그래밍 방식으로 달력 속성을 수정할 수 있나요?
A: 예, Aspose.Tasks는 Java 애플리케이션 내에서 달력 속성을 동적으로 조작할 수 있는 포괄적인 API를 제공합니다.
### Q: Aspose.Tasks를 사용한 캘린더 사용자 정의에 제한 사항이 있나요?
A: Aspose.Tasks는 사용자 정의 옵션에 대한 제한을 최소화하면서 달력 관리에 광범위한 유연성을 제공합니다.
### Q: 달력 관리 기능을 기존 Java 프로젝트에 통합할 수 있습니까?
답: 물론이죠! Aspose.Tasks의 달력 관리 기능을 Java 프로젝트에 원활하게 통합하여 프로젝트 일정 관리 기능을 향상시킬 수 있습니다.
### Q: Aspose.Tasks는 달력 관리 외에 다른 프로젝트 관리 기능을 지원합니까?
A: 예, Aspose.Tasks는 작업, 리소스 및 프로젝트 구조를 관리하기 위한 광범위한 기능을 제공하여 Java 프로젝트 관리를 위한 포괄적인 솔루션을 만듭니다.
### Q: Aspose.Tasks를 사용하는 개발자에게 기술 지원이 제공됩니까?
A: 예, 개발자는 Aspose.Tasks 포럼을 통해 기술 지원에 액세스하여 구현 중에 발생하는 모든 쿼리나 문제에 대한 지원을 받을 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
