---
date: 2026-01-28
description: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더를 생성하고, 캘린더 예외에 대한 평일을 정의하며, 비근무일
  일정을 관리하는 방법을 배웁니다.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: 프로젝트 캘린더 만들기 Aspose – 캘린더 예외를 위한 요일 정의
url: /ko/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 캘린더 Aspose 만들기 – 캘린더 예외를 위한 평일 정의

### 소개
프로젝트 캘린더를 **create project calendar aspose** 해야 할 때, 휴일, 특수 근무, 임시 폐쇄와 같은 비표준 근무일을 모델링할 수 있어야 합니다. Aspose.Tasks for Java는 캘린더 정의에 대한 완전한 제어를 제공하여 실제 일정에 맞는 예외를 추가할 수 있게 합니다. 이 튜토리얼에서는 캘린더 예외를 위한 평일을 정의하는 정확한 단계를 안내하므로 프로젝트 일정이 정확하고 신뢰할 수 있게 유지됩니다. 마지막에는 이러한 방법이 모든 기업 프로젝트에 적용되는 보다 넓은 **non‑working days schedule** 전략에 어떻게 맞는지 확인할 수 있습니다.

## 빠른 답변
- **“create project calendar aspose”는 무엇을 의미합니까?**  
  Aspose.Tasks를 사용하여 작업 일정에 영향을 주는 사용자 정의 캘린더 객체를 만드는 것을 의미합니다.
- **샘플을 실행하려면 라이선스가 필요합니까?**  
  개발에는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.
- **지원되는 IDE는 무엇입니까?**  
  IntelliJ IDEA, Eclipse, NetBeans 또는 Java 8+를 지원하는 모든 IDE.
- **같은 캘린더에 여러 예외를 추가할 수 있습니까?**  
  예 – 필요에 따라 `CalendarException` 객체를 원하는 만큼 추가할 수 있습니다.
- **프로젝트를 어떤 파일 형식으로 저장할 수 있습니까?**  
  XML, MPP 및 Aspose.Tasks에서 지원하는 여러 다른 형식.

## Aspose.Tasks에서 프로젝트 캘린더란 무엇인가요?
**project calendar**는 프로젝트의 작업 일과 시간을 정의합니다. 이는 작업의 시작/종료 날짜, 리소스 할당 및 전체 일정 계산에 영향을 미칩니다. 캘린더를 사용자 정의함으로써 회사 휴일이나 주말 근무 정책과 같은 실제 제약을 일정에 반영할 수 있습니다.

## 왜 캘린더 예외를 위한 평일을 정의해야 할까요?
- **정확한 일정:** 작업이 비근무일로 표시된 날짜에 예약되지 않습니다.
- **리소스 계획:** 리소스는 유효한 근무일에만 할당됩니다.
- **규정 준수:** 프로젝트 일정을 조직 정책이나 법정 휴일에 맞춥니다.

## 캘린더 예외를 활용한 비근무일 일정
**non‑working days schedule**을 관리할 때는 일반적으로 휴일, 유지보수 기간 또는 기타 차단 기간의 마스터 목록이 있습니다. 이러한 날짜를 `CalendarException` 객체로 추가하면, 크리티컬 경로 분석이든 리소스 레벨링이든 모든 계산이 자동으로 해당 제약을 반영합니다. 이 방법은 수동 날짜 조정을 없애고 일정 변동 위험을 줄여줍니다.

## 전제 조건
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 공식 [Aspose.Tasks Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans 또는 Java 호환 편집기.

## 프로젝트 캘린더 aspose 만들기 – 캘린더 예외를 위한 평일 정의

### 단계별 가이드

### Step 1: 필요한 패키지 가져오기
날짜 처리를 위해 핵심 Aspose.Tasks 클래스와 Java의 `GregorianCalendar`가 필요합니다.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Step 2: 데이터 디렉터리 정의
생성된 프로젝트 파일을 저장할 위치를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Project 인스턴스 생성
새 `Project` 객체를 인스턴스화합니다 – 이는 캘린더를 포함한 모든 프로젝트 데이터를 담는 컨테이너입니다.

```java
Project project = new Project();
```

### Step 4: 캘린더 정의
프로젝트에 사용자 정의 캘린더를 추가합니다. 이 캘린더가 예외를 보관하게 됩니다.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Step 5: 평일 예외 정의
`CalendarException`을 생성하여 특정 기간(예: 12월 마지막 주)을 비근무일로 표시합니다.  
예제에서는 예외를 **2009년 12월 24일**부터 **2009년 12월 31일**까지 설정하고, 해당 일들의 작업을 비활성화하며, 예외 유형을 일일(daily)로 지정합니다.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Step 6: 프로젝트 저장
사용자 정의 캘린더와 그 예외를 포함한 프로젝트를 XML 파일로 저장합니다.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
| Issue | Solution |
|-------|----------|
| **예외 날짜가 적용되지 않음** | `setEnteredByOccurrences(false)`와 올바른 `FromDate/ToDate` 값을 확인하십시오. |
| **저장된 파일이 비어 있음** | `dataDir`이 쓰기 가능한 폴더를 가리키고 파일 이름이 `.xml`로 끝나는지 확인하십시오. |
| **캘린더가 작업 일정에 반영되지 않음** | `task.setCalendar(cal)` 또는 `resource.setCalendar(cal)`을 사용하여 캘린더를 작업이나 리소스에 할당하십시오. |

## 자주 묻는 질문

**Q: 같은 캘린더 내에서 서로 다른 평일에 대한 여러 예외를 정의할 수 있나요?**  
A: 예. 각기 다른 기간이나 규칙마다 `cal.getExceptions()`에 추가 `CalendarException` 객체를 추가하면 됩니다.

**Q: Aspose.Tasks for Java는 다양한 Java IDE와 호환됩니까?**  
A: 물론입니다. 이 라이브러리는 IntelliJ IDEA, Eclipse, NetBeans 및 표준 Java 프로젝트를 지원하는 모든 IDE에서 작동합니다.

**Q: 일일 예외 외에 다른 예외 유형을 사용자 정의할 수 있나요?**  
A: 예. `CalendarExceptionType.Weekly`, `Monthly`, `Yearly`를 사용하여 일정 요구에 맞출 수 있습니다.

**Q: 프로젝트 요구에 따라 예외를 동적으로 처리하려면 어떻게 해야 하나요?**  
A: 예외 객체를 프로그래밍 방식으로 생성하십시오—예를 들어, 데이터베이스나 설정 파일에서 휴일 날짜를 읽어 루프에서 `CalendarException` 인스턴스를 생성합니다.

**Q: Aspose.Tasks for Java에 대한 체험판이 있나요?**  
A: 예, [Aspose.Tasks Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 무료 체험판을 다운로드할 수 있습니다.

## 결론
이 단계들을 따라 하면 이제 **create project calendar aspose** 방법과 휴일 또는 특수 비근무 기간을 정확히 반영하는 평일 예외를 정의하는 방법을 알게 됩니다. 적절한 캘린더 구성은 현실적인 일정, 리소스 할당 및 전체 프로젝트 성공에 필수적입니다. 사용자 정의 캘린더를 작업이나 리소스에 연결하고 다른 예외 유형을 실험해 보면서 모든 프로젝트에 적용 가능한 포괄적인 **non‑working days schedule**을 구축해 보세요.

**마지막 업데이트:** 2026-01-28  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}