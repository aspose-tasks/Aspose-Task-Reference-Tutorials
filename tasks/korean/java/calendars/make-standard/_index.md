---
date: 2026-08-13
description: Aspose.Tasks를 사용하여 Java에서 표준 MS Project 캘린더를 만드는 방법을 배웁니다. 이 단계별 가이드는
  표준 MS Project 캘린더를 생성하고 기본값으로 설정한 뒤 파일을 저장하는 방법을 보여줍니다.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks에서 표준 캘린더 만들기
og_description: Aspose.Tasks와 Java를 사용하여 캘린더를 만드는 방법. 표준 MS Project 캘린더를 구축하고 기본값으로
  설정한 뒤 몇 분 안에 프로젝트 파일을 저장하는 방법을 배웁니다.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: 캘린더 만드는 방법 – Aspose.Tasks에서 표준 캘린더 만들기
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: 캘린더 만드는 방법 – Aspose.Tasks에서 표준 캘린더 만들기
url: /ko/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 캘린더 만들기 – Aspose.Tasks에서 표준 캘린더 만들기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project 파일용 **캘린더 만들기** 객체를 만드는 방법을 배웁니다. 표준 MS Project 캘린더를 생성하고, 이를 기본(표준) 캘린더로 설정한 뒤 프로젝트 파일을 저장하는 과정을 단계별로 안내합니다. 가이드를 마치면 Java 기반 프로젝트 관리 솔루션에 캘린더 생성을 통합할 수 있게 됩니다.

## 빠른 답변
- **표준 캘린더**란 무엇인가요? 사용자 지정 캘린더가 할당되지 않은 작업에 적용되는 기본 작업 시간 정의입니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java – Microsoft Project가 설치되지 않아도 동작하는 순수 Java API입니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 프로덕션 배포 시에는 상용 라이선스가 필요합니다.  
- **생성되는 파일 형식은?** XML 기반 Microsoft Project 파일(`.xml`)입니다.  
- **구현 소요 시간은?** 기본 캘린더 설정을 위해 약 5‑10분 정도 소요됩니다.

## Microsoft Project에서 표준 캘린더란?
표준 캘린더는 프로젝트의 기본 작업 일과 시간을 정의합니다. 일반적으로 월요일부터 금요일까지, 오전 8시부터 오후 5시까지가 기본값이며, 표준 캘린더를 추가하면 사용자 지정 캘린더가 할당되지 않은 모든 작업이 이 작업 시간을 상속받아 일정이 일관되게 유지됩니다.

## 캘린더 생성에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks for Java는 **50개 이상의 입력 및 출력 형식**을 지원하고, 전체 파일을 메모리에 로드하지 않고도 **10,000개 이상의 작업**을 처리할 수 있습니다. 이 순수 Java 라이브러리를 사용하면 서버, CI 파이프라인 또는 모든 Java 애플리케이션에서 Project 파일 생성을 자동화할 수 있어, 별도의 Microsoft Project 라이선스가 필요하지 않습니다.

## 사전 요구 사항
시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오:

### Java Development Kit (JDK) 설치
Oracle 웹사이트 또는 OpenJDK 배포판에서 최신 JDK를 설치하십시오.

### Aspose.Tasks for Java 라이브러리
[download page](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하고 JAR 파일을 프로젝트 클래스패스에 추가하십시오.

## 패키지 가져오기
이 튜토리얼에서는 하나의 import만 필요합니다:

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
생성된 프로젝트 파일을 저장할 위치를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 머신의 절대 경로(예: `C:/Projects/Output/`)로 교체하십시오.

### 단계 2: 프로젝트 인스턴스 생성
`Project`는 Aspose.Tasks의 최상위 객체로, 메모리 내에서 단일 Microsoft Project 파일을 나타냅니다. 이를 인스턴스화하면 캘린더, 작업, 리소스 및 기타 프로젝트 데이터를 담을 컨테이너가 생성됩니다.

```java
Project project = new Project();
```

### 단계 3: 캘린더 정의 및 표준으로 설정
`Calendar` 클래스는 작업 시간 일정을 모델링합니다. 새 캘린더 **“My Cal”**을 추가하고 `makeStandardCalendar`를 호출하면 전체 프로젝트의 기본 캘린더로 승격됩니다.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro tip:** `makeStandardCalendar` 메서드는 제공된 캘린더를 프로젝트의 기본 캘린더로 자동 지정하므로 **표준 캘린더** 기능을 추가하려는 경우 정확히 필요한 동작입니다.

### 단계 4: 프로젝트 저장
`SaveFileFormat`은 프로젝트를 저장할 때 사용할 파일 형식을 지정하는 열거형입니다.  
새 캘린더를 포함한 프로젝트를 XML 파일로 영구 저장합니다.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

다른 Project 버전을 원한다면 파일 이름이나 형식(`SaveFileFormat.Pp`)을 변경할 수 있습니다.

### 단계 5: 완료 메시지 표시
프로세스가 오류 없이 끝났음을 시각적으로 알려줍니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| **파일을 찾을 수 없음** | `dataDir`이 존재하지 않는 폴더를 가리킴 | 폴더를 생성하거나 절대 경로를 사용하십시오 |
| **라이선스 예외** | 프로덕션 환경에서 유효한 Aspose.Tasks 라이선스 없이 실행 | 다음 코드를 사용하여 라이선스 파일을 적용하십시오: `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **빈 캘린더** | 작업 시간 정의를 추가하지 않음 | 필요에 따라 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 등을 사용하여 사용자 정의 시간을 추가하십시오 |

## 자주 묻는 질문

**Q: Aspose.Tasks가 모든 버전의 Microsoft Project와 호환됩니까?**  
A: 예, Aspose.Tasks는 2000 버전부터 최신 릴리스까지 다양한 Microsoft Project 버전을 지원합니다.

**Q: 캘린더 설정을 더 맞춤화할 수 있나요?**  
A: 물론입니다! `WeekDay`와 `WorkingTime` 클래스를 사용하여 작업 요일을 수정하고, 예외를 추가하며, 특정 작업 시간을 정의할 수 있습니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준 애플리케이션에 적합합니까?**  
A: 확실히 그렇습니다. 이 라이브러리는 고성능·확장성을 염두에 두고 설계되었으며, 대용량 Project 파일에 대한 포괄적인 지원을 제공합니다.

**Q: Aspose.Tasks가 개발자를 위한 기술 지원을 제공합니까?**  
A: 예, Aspose는 전용 포럼, 티켓 기반 지원 및 방대한 문서를 제공하여 문제 해결을 빠르게 도와줍니다.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 예, [website](https://purchase.aspose.com/buy)에서 무료 체험 버전을 이용해 모든 기능을 평가해볼 수 있습니다.

---

**마지막 업데이트:** 2026-08-13  
**테스트 대상:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java로 프로젝트에 캘린더 추가](/tasks/java/calendars/create/)
- [Aspose.Tasks를 사용한 Java 프로젝트 캘린더 설정 방법](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java로 사용자 정의 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}