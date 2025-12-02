---
date: 2025-12-02
description: Aspose.Tasks for Java를 사용하여 캘린더를 설정하고, MS Project의 평일을 정의하며, 사용자 지정 작업일을
  지정하는 방법을 배웁니다. 몇 줄의 코드만으로 프로젝트를 XML로 저장합니다.
language: ko
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project에서 캘린더 설정 및 평일 정의 방법
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project에서 Aspose.Tasks를 사용해 캘린더 설정 및 평일 정의 방법

## 소개
이 튜토리얼에서는 **캘린더 설정**을 프로그래밍 방식으로 적용하고 Aspose.Tasks for Java 라이브러리를 사용해 Microsoft Project 파일에 평일을 정의하는 방법을 알아봅니다. 표준 작업 주를 만들든, 주말 근무일을 추가하든, 짧은 금요일 일정을 구성하든, 프로젝트 생성부터 XML 파일 저장까지 모든 단계를 자세히 안내합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Tasks for Java  
- **주말 근무일을 추가할 수 있나요?** 예 – 토요일과 일요일을 근무일로 지정하면 됩니다.  
- **프로젝트는 어떻게 저장하나요?** `prj.save(..., SaveFileFormat.Xml)`을 사용합니다.  
- **라이선스가 필요합니까?** 평가용 무료 체험판을 사용할 수 있지만, 실제 운영 환경에서는 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상.

## MS Project에서 “캘린더 설정”이란?
MS Project에서 캘린더를 설정한다는 것은 작업일, 일일 근무 시간 및 휴일과 같은 예외를 정의하는 것을 의미합니다. 이 캘린더는 작업 일정, 리소스 할당 및 전체 프로젝트 타임라인을 결정합니다.

## 캘린더 조작에 Aspose.Tasks를 사용하는 이유
- **전체 제어** – UI를 열지 않고도 프로그래밍 방식으로 캘린더를 생성, 수정 또는 삭제할 수 있습니다.  
- **크로스‑플랫폼** – Java를 지원하는 모든 OS에서 동작합니다.  
- **모든 파일 형식 지원** – MPP, MPT, XML 등 모든 포맷을 지원하므로 *프로젝트를 XML로 저장*하여 다른 시스템과 쉽게 연동할 수 있습니다.  
- **COM 의존성 없음** – Microsoft Project Interop 라이브러리와 달리 COM이 필요하지 않습니다.

## 사전 준비
시작하기 전에 다음을 준비하십시오:

1. **Java Development Kit (JDK) 8+** – [Oracle 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드합니다.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받습니다.  
3. 프로젝트 클래스패스에 Aspose.Tasks JAR를 추가할 IDE 또는 빌드 도구(Maven/Gradle).

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 이 임포트 구문을 통해 프로젝트, 캘린더 및 작업 시간 객체에 접근할 수 있습니다.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 단계별 가이드

### 단계 1: Project 인스턴스 생성
새 `Project` 객체를 만듭니다. 이 객체가 편집할 MS Project 파일을 나타냅니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 단계 2: 새 캘린더 정의
프로젝트에 새로운 캘린더를 추가합니다. 여러 캘린더를 사용할 경우 명확한 이름을 지정하면 관리가 편리합니다.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 단계 3: 표준 작업일 (월‑목) 추가
내장 헬퍼 `WeekDay.createDefaultWorkingDay`를 사용해 핵심 작업 주인 월요일‑목요일의 기본 9 am‑5 pm 일정을 설정합니다.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 단계 4: 주말 근무일 추가
프로젝트가 주말에도 진행된다면 토요일과 일요일을 일반 근무일로 추가하면 됩니다. 이는 **주말 근무일 추가**를 보여주는 예시입니다.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 단계 5: 맞춤형 짧은 근무일 (금요일) 설정
여기서는 금요일에 **맞춤형 근무일**을 설정합니다: 오전 근무 (9 am‑12 pm)와 오후 근무 (1 pm‑4 pm).

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

### 단계 6: 프로젝트를 XML로 저장
마지막으로 변경 내용을 영구 저장합니다. `SaveFileFormat.Xml` 옵션을 사용하면 **프로젝트를 XML로 저장**할 수 있어 다른 도구와의 연동에 유용합니다.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|------|--------|
| **작업 시간이 적용되지 않음** | 사용자 정의 `WeekDay`에 `setDayWorking(true)`가 호출되었는지 확인합니다. |
| **저장 시 파일을 찾을 수 없음** | `dataDir`가 존재하는 폴더를 가리키는지, 애플리케이션에 쓰기 권한이 있는지 확인합니다. |
| **캘린더가 작업에 반영되지 않음** | 새로 만든 캘린더를 리소스나 작업에 `task.setCalendar(cal)`을 통해 할당합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용해 사용자 정의 비근무일을 정의할 수 있나요?**  
A: 예. 비근무일로 지정하고 싶은 `WeekDay`의 `DayWorking` 속성을 `false`로 설정하면 됩니다.

**Q: 휴일이나 전사적인 예외를 추가하려면 어떻게 하나요?**  
A: `CalendarException` 객체를 생성하고 예외 날짜를 지정한 뒤 `cal.getExceptions()`에 추가합니다.

**Q: 라이브러리가 오래된 MS Project 버전과 호환되나요?**  
A: 물론입니다. Aspose.Tasks는 여러 버전의 MPP, MPT 및 XML 포맷을 지원합니다.

**Q: 가져온 프로젝트에서 기존 캘린더를 수정할 수 있나요?**  
A: `new Project("existing.mpp")`로 프로젝트를 로드한 뒤 원하는 캘린더를 가져와 변경하고 저장하면 됩니다.

**Q: Aspose.Tasks가 반복 작업도 처리하나요?**  
A: 예. `RecurringTask` 클래스를 사용해 반복 작업을 생성하고 편집할 수 있습니다.

## 결론
이제 **캘린더 설정** 방법, **MS Project에서 평일 정의**, 주말 근무일 추가, 짧은 금요일 일정 생성 등을 Aspose.Tasks for Java로 구현하는 방법을 알게 되었습니다. 결과를 XML로 저장하고 캘린더 로직을 모든 Java 기반 프로젝트 관리 솔루션에 통합해 보세요.

---

**마지막 업데이트:** 2025-12-02  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}