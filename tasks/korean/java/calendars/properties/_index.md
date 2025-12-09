---
date: 2025-12-04
description: Aspose.Tasks를 사용하여 Java에서 프로젝트 캘린더를 설정하고 MS Project 캘린더 속성을 관리하는 방법을
  배웁니다. 캘린더 작업 시간을 표시하고 일정을 맞춤 설정하는 단계별 가이드.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더 설정하는 방법
url: /ko/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 프로젝트 캘린더 설정 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks 라이브러리를 사용해 **프로젝트 캘린더 설정 방법**을 프로그래밍 방식으로 알아봅니다. 캘린더 속성을 제어하면 **캘린더 작업 시간**을 표시하고, 사용자 정의 작업일을 정의하며, 프로젝트 일정과 실제 제약 조건을 맞출 수 있습니다. 환경 설정부터 캘린더 순회 및 속성 읽기에 이르는 모든 단계를 단계별로 안내하므로, Java 애플리케이션에서 MS Project 캘린더를 자신 있게 관리할 수 있습니다.

## 빠른 답변
- **“프로젝트 캘린더 설정”이란 무엇인가요?** MS Project 파일 내에서 캘린더의 작업 시간, 기본 캘린더 및 일 유형을 생성하거나 업데이트하는 것을 의미합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **캘린더 작업 시간을 표시할 수 있나요?** 예—각 `WeekDay`를 읽어 모든 일 유형에 대한 시간을 출력할 수 있습니다.  
- **Maven/Gradle과 호환되나요?** 물론—Aspose.Tasks JAR를 의존성으로 추가하면 됩니다.

## 프로젝트 캘린더란?
프로젝트 캘린더는 작업, 리소스 및 전체 프로젝트 일정에 대한 작업일 및 작업 시간을 정의합니다. MS Project에서는 캘린더가 기본 캘린더를 상속할 수 있으며, 각 일 유형(예: **Standard**, **Non‑working**)마다 고유한 작업 시간을 가질 수 있습니다. 이러한 설정을 프로그래밍 방식으로 관리하면 수동 편집 없이도 동적으로 일정 조정이 가능합니다.

## 왜 MS Project 캘린더를 프로그래밍 방식으로 관리할까요?
- **자동화:** 하나의 스크립트로 다수 프로젝트의 캘린더를 조정합니다.  
- **일관성:** 조직 전체의 작업 시간 정책을 강제합니다.  
- **통합:** 캘린더를 외부 시스템(HR, ERP)과 동기화합니다.  
- **가시성:** 보고서나 디버깅을 위해 **캘린더 작업 시간을 빠르게 표시**합니다.

## 전제 조건
시작하기 전에 다음을 준비하십시오:

- **Java Development Kit (JDK) 8+** 가 설치되어 있고 `JAVA_HOME`이 설정되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리를 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드합니다. JAR를 프로젝트 클래스패스 또는 Maven/Gradle 의존성에 추가하십시오.  

## 패키지 가져오기
튜토리얼 전반에 사용할 핵심 Aspose.Tasks 클래스를 먼저 가져옵니다:

```java
import com.aspose.tasks.*;
```

## 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 위치한 폴더를 정의합니다. 자리표시자를 실제 경로로 교체하십시오.

```java
String dataDir = "Your Data Directory";
```

## 단계 2: 시간 단위 정의
작업 시간은 밀리초 단위로 표현됩니다. 재사용 가능한 상수를 정의하면 코드 가독성이 향상됩니다.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 단계 3: 프로젝트 데이터 로드
기존 MS Project XML 파일(`.xml` 또는 `.mpp`)을 로드하여 `Project` 인스턴스를 생성합니다. 이를 통해 파일에 저장된 모든 캘린더에 접근할 수 있습니다.

```java
Project project = new Project(dataDir + "project.xml");
```

## 단계 4: 캘린더를 순회하고 작업 시간 표시
이제 모든 캘린더를 순회하면서 고유 식별자, 이름, 기본 캘린더 및 각 일 유형에 대한 작업 시간을 출력합니다. 이는 **프로젝트 캘린더 설정 방법**을 보여줄 뿐 아니라 **캘린더 작업 시간을 표시**하는 방법도 보여줍니다.

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

### 이 코드가 수행하는 작업
- **이름이 없는 캘린더 필터링**(일부 내부 캘린더는 `null` 이름을 가질 수 있음).  
- **UID와 이름 출력** – 나중에 캘린더를 식별할 때 유용합니다.  
- **기본 캘린더 표시** – “Self”(캘린더 자체가 기본 캘린더) 또는 상속된 캘린더 이름.  
- **각 `WeekDay`를 순회**하여 총 작업 시간(`workingTime`은 밀리초 단위이므로 `OneHour`로 나눔)을 계산하고 출력합니다.  

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | 캘린더 자체가 기본 캘린더(`isBaseCalendar()`가 `true`를 반환) | 예시와 같이 삼항 연산자를 사용하십시오 (`cal.isBaseCalendar() ? "Self" : ...`). |
| 작업 시간에 대한 출력 없음 | 프로젝트 파일이 다른 시간 단위(틱)를 사용 | 파일 형식을 확인하십시오; Aspose.Tasks는 밀리초로 정규화하지만 올바른 파일 유형을 로드하고 있는지 확인하십시오. |
| `project.xml`을 찾을 수 없음 | `dataDir` 경로가 올바르지 않음 | 절대 경로를 사용하거나 `Paths.get(dataDir, "project.xml").toString()`을 사용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 캘린더 속성을 프로그래밍 방식으로 수정할 수 있나요?**  
A: 예, API는 캘린더에 대한 전체 읽기/쓰기 접근을 제공하므로 작업 시간, 예외, 기본 캘린더 관계 등을 추가, 편집 또는 삭제할 수 있습니다.

**Q: Aspose.Tasks로 캘린더 맞춤 설정에 제한이 있나요?**  
A: 라이브러리는 Microsoft Project의 기능을 그대로 반영하므로 사실상 모든 캘린더 요소를 커스터마이즈할 수 있습니다. 매우 오래된 Project 파일 버전만 약간의 호환성 문제가 있을 수 있습니다.

**Q: 기존 Java 프로젝트에 캘린더 관리를 통합할 수 있나요?**  
A: 물론입니다. Aspose.Tasks JAR를 빌드 경로에 추가하고 여기서 보여준 코드 패턴을 그대로 사용하면 됩니다.

**Q: Aspose.Tasks가 캘린더 관리 외에 다른 프로젝트 관리 기능을 지원하나요?**  
A: 예, 작업, 리소스, 할당, 개요, 기준선 등 다양한 기능을 제공하므로 Java 기반 프로젝트 자동화에 포괄적인 솔루션이 됩니다.

**Q: Aspose.Tasks 개발자를 위한 기술 지원이 제공되나요?**  
A: 예, Aspose는 전용 포럼, 이메일 지원 및 모든 라이선스 사용자에게 제공되는 방대한 문서를 통해 지원합니다.

## 결론
이 가이드를 따라 **프로젝트 캘린더 설정 방법**을 익히고, **캘린더 작업 시간을 읽고 표시**하는 방법을 배우며, Aspose.Tasks를 활용해 Java 애플리케이션에 이러한 기능을 통합할 수 있게 되었습니다. 이를 통해 일정 조정을 자동화하고, 일관된 작업 정책을 적용하며, 보다 풍부한 프로젝트 관리 솔루션을 구축할 수 있습니다.

---

**마지막 업데이트:** 2025-12-04  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}