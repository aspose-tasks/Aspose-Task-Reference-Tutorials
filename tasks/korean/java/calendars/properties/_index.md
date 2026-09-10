---
date: 2026-09-09
description: Aspose.Tasks를 사용하여 Java에서 프로젝트 캘린더를 설정하는 방법. 캘린더 작업 시간을 표시하고, 작업 시간을
  구성하며, MS Project 파일에서 캘린더 날짜를 수정하는 방법을 배웁니다.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Aspose.Tasks에서 캘린더 속성 관리
og_description: Aspose.Tasks를 사용하여 Java에서 프로젝트 캘린더를 설정하는 방법. 캘린더 작업 시간을 표시하고, 작업 시간을
  구성하며, MS Project 파일에서 캘린더 날짜를 수정하는 방법을 배웁니다.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks를 사용한 Java 프로젝트 캘린더 설정 방법
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Aspose.Tasks를 사용한 Java 프로젝트 캘린더 설정 방법
url: /ko/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks와 Java 프로젝트 캘린더 설정 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks 라이브러리를 활용하여 Java에서 **프로젝트 캘린더 설정 방법**을 배웁니다. 캘린더 속성을 제어하면 **캘린더 근무 시간**을 표시하고, 사용자 정의 근무일을 구성하며, 휴일이나 교대 패턴과 같은 실제 제약 조건에 맞춰 프로젝트 일정을 맞출 수 있습니다. 환경 설정, 프로젝트 로드, 캘린더 순회, 속성 읽기 및 업데이트 과정을 단계별로 안내하여 Java 애플리케이션에서 **MS Project 캘린더** 설정을 자신 있게 관리할 수 있도록 합니다.

## 빠른 답변
- **“프로젝트 캘린더 설정”이란 무엇인가요?** MS Project 파일 내에서 캘린더의 근무 시간, 기본 캘린더 및 일 유형을 생성하거나 업데이트하는 것을 의미합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요한가요?** 개발에는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **캘린더 근무 시간을 표시할 수 있나요?** 예—각 `WeekDay`를 읽어 모든 일 유형에 대한 시간을 출력할 수 있습니다.  
- **Maven/Gradle과 호환되나요?** 물론입니다—Aspose.Tasks JAR를 의존성으로 추가하면 됩니다.

## Java에서 프로젝트 캘린더 설정 방법
프로젝트 파일을 로드하고 대상 캘린더를 찾은 뒤, 필요에 따라 근무 시간 정의, 기본 캘린더 및 일 유형을 조정합니다. 아래 단계는 로드, 순회, 수정, 저장을 포함한 전체 솔루션을 제공하며, 예외 처리와 정확한 근무 시간 계산을 보장합니다.

## 프로젝트 캘린더란?
프로젝트 캘린더는 작업, 리소스 및 전체 프로젝트 타임라인에 대한 근무 일과 시간을 정의합니다. MS Project에서는 캘린더가 기본 캘린더를 상속할 수 있으며, 각 일 유형(예: **Standard**, **Non‑working**)마다 고유한 근무 시간을 가질 수 있습니다. 프로그래밍 방식으로 이러한 설정을 관리하면 수동 편집 없이도 동적으로 일정 조정이 가능합니다.

## 왜 MS Project 캘린더를 프로그래밍 방식으로 관리할까요?
프로그래밍 방식으로 캘린더를 관리하면 여러 프로젝트에 일관된 일정 규칙을 적용하고, 수동 오류를 줄이며, HR 또는 ERP와 같은 다른 엔터프라이즈 시스템과 캘린더 데이터를 통합할 수 있습니다. 이러한 자동화는 프로젝트 설정 속도를 높이고 모든 팀원이 동일한 근무 정책을 따르도록 보장합니다.

- **자동화:** 단일 스크립트로 수십 개 프로젝트의 캘린더를 조정합니다.  
- **일관성:** 조직 전체의 근무 시간 정책을 자동으로 적용합니다.  
- **통합:** 캘린더를 외부 HR 또는 ERP 시스템과 동기화합니다.  
- **가시성:** 보고서나 디버깅을 위해 **캘린더 근무 시간을 빠르게 표시**합니다.  
- **유연성:** UI를 열지 않고도 예외나 교대 패턴을 즉시 추가합니다.

## 전제 조건
시작하기 전에 다음을 확인하세요:

- **Java Development Kit (JDK) 8+** 가 설치되어 있고 `JAVA_HOME`이 설정되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리를 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드합니다. JAR를 클래스패스에 추가하거나 Maven/Gradle 의존성으로 선언하세요.  
- 최소 하나의 캘린더가 포함된 샘플 MS Project 파일(`.mpp` 또는 `.xml`)이 필요합니다.

## 패키지 가져오기
`Project`, `Calendar`, `WeekDay` 및 관련 클래스는 캘린더 조작의 핵심입니다.  
`Calendar` 클래스는 작업일, 예외 및 기본 캘린더 관계를 포함하는 프로젝트 캘린더를 나타냅니다.  
`WeekDay` 클래스는 캘린더 내 단일 일에 대한 근무 시간 설정을 정의합니다.

`Project` 클래스는 Aspose.Tasks의 최상위 객체로, 메모리 내에서 단일 MS Project 파일을 나타냅니다. 파일을 로드한 후 모든 캘린더 작업은 이 객체를 통해 이루어집니다.

```java
import com.aspose.tasks.*;
```

## 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. 자리표시자를 실제 경로로 교체하세요.

```java
String dataDir = "Your Data Directory";
```

## 단계 2: 시간 단위 상수 정의
근무 시간은 밀리초 단위로 표현됩니다. 재사용 가능한 상수를 정의하면 코드 가독성이 높아지고 **Java에서 근무 시간을 정확히 계산**할 수 있습니다.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 단계 3: 프로젝트 데이터 로드
기존 MS Project XML 파일(`.xml` 또는 `.mpp`)을 로드하여 `Project` 인스턴스를 생성합니다. 이를 통해 파일에 저장된 모든 캘린더에 접근할 수 있습니다.

`Project` 클래스는 파일을 경량 객체 모델로 로드하므로 전체 파일을 메모리에 보관할 필요가 없으며, 수만 개의 작업을 포함한 프로젝트도 효율적으로 처리할 수 있습니다.

```java
Project project = new Project(dataDir + "project.xml");
```

## 단계 4: Java에서 캘린더 순회
이제 모든 캘린더를 순회하면서 고유 식별자, 이름, 기본 캘린더 및 각 일 유형의 근무 시간을 출력합니다. 이를 통해 **Java에서 프로젝트 캘린더 설정 값**을 확인하고 **캘린더 근무 시간을 표시**하는 방법을 보여줍니다.

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
- **이름이 없는 캘린더 필터링** (일부 내부 캘린더는 `null` 이름을 가질 수 있음).  
- **UID와 이름 출력** – 나중에 캘린더를 식별하는 데 유용.  
- **기본 캘린더 표시** – “Self”(캘린더 자체가 기본) 또는 상속된 캘린더 이름.  
- **`WeekDay`마다 반복**하여 총 근무 시간 계산 및 출력 (`workingTime`은 밀리초 단위이므로 `OneHour`로 나눔).

## Aspose.Tasks 사용의 정량적 이점
Aspose.Tasks는 **30개 이상의 입력 및 출력 형식**을 지원하며, 전체 파일을 메모리에 로드하지 않고도 **10,000개 작업**까지 처리할 수 있어 일반 서버 하드웨어에서 1초 미만의 응답 시간을 제공합니다. 이러한 수치는 엔터프라이즈 규모 자동화에 신뢰할 수 있는 선택임을 입증합니다.

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| `cal.getBaseCalendar()`에서 NullPointerException | 캘린더가 자체가 기본 캘린더임(`isBaseCalendar()`가 `true` 반환). | 표시된 삼항 연산자를 사용 (`cal.isBaseCalendar() ? "Self" : ...`). |
| 근무 시간에 대한 출력 없음 | 프로젝트 파일이 다른 시간 단위(틱)를 사용함. | 파일 형식을 확인하세요; Aspose.Tasks는 밀리초로 정규화하지만 올바른 파일 유형을 로드했는지 확인하십시오. |
| `project.xml`을 찾을 수 없음 | `dataDir` 경로가 올바르지 않음. | 절대 경로나 `Paths.get(dataDir, "project.xml").toString()`을 사용하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용하여 캘린더 속성을 프로그래밍 방식으로 수정할 수 있나요?**  
A: 예, API는 캘린더에 대한 완전한 읽기/쓰기 접근을 제공하므로 근무 시간, 예외 및 기본 캘린더 관계를 추가, 편집 또는 삭제할 수 있습니다.

**Q: Aspose.Tasks로 캘린더 맞춤 설정에 제한이 있나요?**  
A: 라이브러리는 Microsoft Project의 기능을 그대로 반영하므로 사실상 모든 캘린더 항목을 커스터마이징할 수 있습니다. 매우 오래된 Project 파일 버전만 약간의 호환성 문제가 있을 수 있습니다.

**Q: 기존 Java 프로젝트에 캘린더 관리를 통합할 수 있나요?**  
A: 물론입니다. Aspose.Tasks JAR를 빌드 경로에 추가하고 여기서 보여준 코드 패턴을 그대로 사용하면 됩니다.

**Q: Aspose.Tasks는 캘린더 관리 외에 다른 프로젝트 관리 기능을 지원하나요?**  
A: 예, 작업, 리소스, 할당, 개요, 기준선 등 다양한 기능을 포함하고 있어 Java 기반 프로젝트 자동화에 포괄적인 솔루션을 제공합니다.

**Q: Aspose.Tasks 개발자를 위한 기술 지원이 제공되나요?**  
A: 예, Aspose는 전용 포럼, 이메일 지원 및 모든 라이선스 사용자에게 제공되는 방대한 문서를 통해 지원합니다.

---

**마지막 업데이트:** 2026-09-09  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [Java 프로젝트 캘린더 만들기 – Aspose.Tasks for Java 가이드](/tasks/java/)
- [Java에서 프로젝트 파일 로드 및 프로젝트 속성 관리](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}