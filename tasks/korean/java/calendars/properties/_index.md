---
date: 2026-02-07
description: Aspose.Tasks를 사용하여 Java에서 프로젝트 캘린더를 설정하고 MS Project 캘린더 속성을 관리하는 방법을
  배우세요. 캘린더 작업 시간을 표시하고 일정을 맞춤 설정하는 단계별 가이드.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용한 Java 프로젝트 캘린더 설정 방법
url: /ko/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 Java 프로젝트 캘린더 설정 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 **how to set project calendar java** 를 프로그래밍 방식으로 설정하는 방법을 알아봅니다. 캘린더 속성을 제어하면 **display calendar working hours** 를 표시하고, 사용자 정의 작업일을 정의하며, 프로젝트 일정과 실제 제약 조건을 일치시킬 수 있습니다. 환경 설정부터 캘린더를 순회하고 속성을 읽는 단계까지 모두 자세히 안내하므로, 애플리케이션에서 **manage ms project calendar** 설정을 자신 있게 관리할 수 있습니다.

## 빠른 답변
- **“set project calendar”가 의미하는 것은?** MS Project 파일 내에서 캘린더의 작업 시간, 기본 캘린더 및 요일 유형을 생성하거나 업데이트하는 것을 의미합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **캘린더 작업 시간을 표시할 수 있나요?** 예—각 `WeekDay` 를 읽어 모든 요일 유형에 대한 시간을 출력할 수 있습니다.  
- **Maven/Gradle과 호환되나요?** 물론입니다—Aspose.Tasks JAR를 의존성으로 추가하면 됩니다.

## How to Set Project Calendar Java
이 섹션은 주요 키워드에 직접 답합니다. **set project calendar java** 값을 설정하고, 캘린더 작업일을 수정하며, Java 스타일로 작업 시간을 계산하는 정확한 단계들을 다룹니다.

## 프로젝트 캘린더란?
프로젝트 캘린더는 작업, 리소스 및 전체 프로젝트 일정에 대한 작업 일과 시간을 정의합니다. MS Project에서는 캘린더가 기본 캘린더를 상속할 수 있으며, 각 요일 유형(예: **Standard**, **Non‑working**)마다 고유한 작업 시간이 있을 수 있습니다. 이러한 설정을 프로그래밍 방식으로 관리하면 수동 편집 없이 동적인 일정 조정이 가능합니다.

## 왜 MS Project 캘린더를 프로그래밍 방식으로 관리할까?
- **자동화:** 하나의 스크립트로 다수 프로젝트의 캘린더를 조정합니다.  
- **일관성:** 조직 전체의 작업 시간 정책을 강제합니다.  
- **통합:** 캘린더를 외부 시스템(HR, ERP)과 동기화합니다.  
- **가시성:** 보고서나 디버깅을 위해 **display calendar working hours** 를 빠르게 **display calendar working hours** 할 수 있습니다.  
- **유연성:** 필요에 따라 **modify calendar working days** 를 즉시 추가하거나 예외를 설정할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하세요:

- **Java Development Kit (JDK) 8+** 가 설치되어 있고 `JAVA_HOME` 이 설정되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리를 [download page](https://releases.aspose.com/tasks/java/) 에서 다운로드합니다. JAR 파일을 프로젝트 클래스패스 또는 Maven/Gradle 의존성에 추가하세요.  

## 패키지 가져오기
튜토리얼 전반에 사용할 핵심 Aspose.Tasks 클래스를 먼저 가져옵니다:

```java
import com.aspose.tasks.*;
```

## 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. 자리표시자를 실제 경로로 교체하세요.

```java
String dataDir = "Your Data Directory";
```

## 단계 2: 시간 단위 정의
작업 시간은 밀리초 단위로 표현됩니다. 재사용 가능한 상수를 정의하면 코드를 읽기 쉽고 **calculate working hours java** 를 정확히 수행할 수 있습니다.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 단계 3: 프로젝트 데이터 로드
기존 MS Project XML 파일(`.xml` 또는 `.mpp`)을 로드하여 `Project` 인스턴스를 생성합니다. 이렇게 하면 파일에 저장된 모든 캘린더에 접근할 수 있습니다.

```java
Project project = new Project(dataDir + "project.xml");
```

## Iterate Through Calendars Java
이제 모든 캘린더를 순회하면서 고유 식별자, 이름, 기본 캘린더 및 각 요일 유형에 대한 작업 시간을 출력합니다. 이는 **how to set project calendar java** 값을 설정하고 **display calendar working hours** 를 표시하는 방법을 보여줍니다.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### 코드 설명
- **이름이 없는 캘린더 필터링** (일부 내부 캘린더는 `null` 이름을 가질 수 있음).  
- **UID와 이름 출력** – 이후 캘린더를 식별할 때 유용합니다.  
- **기본 캘린더 표시** – “Self”(캘린더 자체가 기본) 또는 상속된 캘린더 이름.  
- **각 `WeekDay` 를 순회**하여 총 작업 시간(`workingTime` 은 밀리초 단위) 을 계산하고 `OneHour` 로 나눠 출력합니다.  

## 일반적인 문제와 해결 방법
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | 캘린더가 자체가 기본 캘린더(`isBaseCalendar()` 가 `true`)인 경우. | 예시와 같이 삼항 연산자를 사용합니다 (`cal.isBaseCalendar() ? "Self" : ...`). |
| 작업 시간 출력 없음 | 프로젝트 파일이 다른 시간 단위(틱)를 사용함. | 파일 형식을 확인하세요; Aspose.Tasks는 밀리초로 정규화하지만 올바른 파일 유형을 로드했는지 확인합니다. |
| `project.xml` 을 찾을 수 없음 | `dataDir` 경로가 잘못됨. | 절대 경로나 `Paths.get(dataDir, "project.xml").toString()` 을 사용하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 캘린더 속성을 프로그래밍 방식으로 수정할 수 있나요?**  
A: 예, API는 캘린더에 대한 완전한 읽기/쓰기 접근을 제공하므로 작업 시간, 예외, 기본 캘린더 관계 등을 추가, 편집 또는 삭제할 수 있습니다.

**Q: Aspose.Tasks로 캘린더 커스터마이징에 제한이 있나요?**  
A: 라이브러리는 Microsoft Project의 기능을 그대로 반영하므로 사실상 모든 캘린더 요소를 커스터마이징할 수 있습니다. 매우 오래된 Project 파일 버전만 약간의 호환성 문제가 있을 수 있습니다.

**Q: 기존 Java 프로젝트에 캘린더 관리를 통합할 수 있나요?**  
A: 물론입니다. Aspose.Tasks JAR를 빌드 경로에 추가하고 여기서 보여준 코드 패턴을 그대로 사용하면 됩니다.

**Q: Aspose.Tasks가 캘린더 관리 외에 다른 프로젝트 관리 기능도 지원하나요?**  
A: 예, 작업, 리소스, 할당, 개요, 기준선 등 다양한 기능을 제공하므로 Java 기반 프로젝트 자동화에 포괄적인 솔루션이 됩니다.

**Q: Aspose.Tasks 개발자를 위한 기술 지원이 있나요?**  
A: 예, Aspose는 전용 포럼, 이메일 지원 및 모든 라이선스 사용자에게 제공되는 방대한 문서를 운영하고 있습니다.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}