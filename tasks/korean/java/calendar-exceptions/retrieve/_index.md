---
date: 2026-11-19
description: MS Project 파일에서 Java 캘린더 예외를 검색하고 Aspose.Tasks for Java를 사용하여 MPP 캘린더를
  읽는 방법을 배웁니다. 이 튜토리얼은 단계별 코드 예제를 제공합니다.
images:
- /java/calendar-exceptions/retrieve/og-image.png
keywords:
- retrieve calendar exceptions java
- Aspose.Tasks for Java
- MS Project calendar API
- read MPP calendar
- Java project scheduling
lastmod: 2026-11-19
linktitle: Aspose.Tasks를 사용하여 Java에서 캘린더 예외를 검색하는 방법
og_description: MS Project 파일에서 Java 캘린더 예외를 검색하고 Aspose.Tasks for Java를 사용하여 MPP
  캘린더를 읽는 방법을 배웁니다. 이 가이드는 Java 애플리케이션에 정확한 캘린더 처리를 추가하는 방법을 보여줍니다.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Aspose.Tasks를 사용하여 Java 캘린더 예외를 검색하는 방법
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Aspose.Tasks를 사용하여 Java에서 캘린더 예외를 검색하는 방법
url: /ko/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks와 함께 Java에서 캘린더 예외를 검색하는 방법

## 소개
이 **asp tasks java tutorial**에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project 파일에서 캘린더 예외를 검색하는 방법을 배웁니다. 캘린더 예외는 휴일이나 사용자 정의 근무 시간 규칙과 같은 비작업 기간을 나타내며, 이를 프로그래밍 방식으로 읽을 수 있는 능력은 자원 레벨링, 보고 및 맞춤 일정 로직에 필수적입니다. 전체 과정을 단계별로 안내하므로 여러분은 자신감 있게 이 기능을 Java 애플리케이션에 통합할 수 있습니다.

## 빠른 답변
- **이 튜토리얼에서 다루는 내용은?** Aspose.Tasks for Java를 사용하여 MPP 파일에서 캘린더 예외를 검색합니다.  
- **구현에 걸리는 시간은?** 기본 설정 기준으로 10‑15분 정도 소요됩니다.  
- **전제 조건은?** JDK, Aspose.Tasks for Java, 그리고 IDE(IntelliJ IDEA 또는 Eclipse).  
- **라이선스가 필요한가요?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 Project 버전은?** 모든 주요 MS Project 형식(MPP, MPT, XML)을 지원합니다.

## asp tasks java tutorial이란?
**asp tasks java tutorial**은 Java 프로젝트에서 Aspose.Tasks API를 활용하는 방법을 설명합니다. 구체적인 코드 스니펫, 모범 사례 설명, 실제 시나리오를 제공하여 개발자가 Microsoft Project를 설치하지 않고도 Project 파일을 조작할 수 있게 합니다. 이 튜토리얼을 따라 하면 API 구조, 일반 사용 패턴, 그리고 엔터프라이즈 애플리케이션에 통합하는 방법을 실습을 통해 명확히 이해할 수 있습니다.

## 캘린더 예외를 검색해야 하는 이유
캘린더 예외를 검색하면 휴일 및 사용자 정의 근무 일정에 맞춘 정확한 프로젝트 타임라인을 생성하고, 비작업일을 강조하는 보고 도구를 구축하며, ERP나 HR 플랫폼과 같은 외부 시스템과 Project 캘린더를 동기화할 수 있습니다. Aspose.Tasks는 **30개 이상의** 캘린더 유형에서 예외를 읽을 수 있으며, **3가지 주요** MS Project 파일 형식(MPP, MPT, XML)을 전체 파일을 메모리에 로드하지 않고도 지원해 수백 페이지 규모의 프로젝트도 효율적으로 처리할 수 있습니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하십시오:

1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – **[Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)**에서 다운로드하고 설치합니다.  
3. **통합 개발 환경 (IDE)** – IntelliJ IDEA, Eclipse 등 원하는 IDE를 사용합니다.

튜토리얼 중에 다시 필요하면 **[Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)**에서 Aspose.Tasks for Java를 얻을 수 있습니다.

## 데이터 디렉터리를 어떻게 설정하나요?
프로젝트 파일이 들어 있는 폴더를 정의합니다. 절대 경로나 프로젝트 리소스 폴더에 대한 상대 경로를 사용하면 `FileNotFoundException`을 방지할 수 있습니다. 파일은 전용 `resources` 폴더에 보관하고 `Paths.get(...)`를 사용해 플랫폼에 독립적인 경로를 지정하십시오.

## 패키지 가져오기
다음 import 문은 Aspose.Tasks 클래스를 Java 소스 파일에 포함시켜 프로젝트, 캘린더 및 예외를 다룰 수 있게 합니다.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Project 클래스란?
`Project`는 메모리로 로드된 MS Project 파일을 나타냅니다. Aspose.Tasks의 핵심 객체로, 캘린더, 작업, 리소스 및 기타 프로젝트 데이터를 깔끔한 객체 지향 API를 통해 접근할 수 있습니다. `Project` 클래스를 사용하면 Microsoft Project가 설치되지 않은 서버 환경에서도 프로젝트의 모든 요소를 조회·조작할 수 있어 자동화된 보고 및 서버‑사이드 처리에 적합합니다.

## 1단계: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. 절대 경로나 프로젝트 리소스 폴더에 대한 상대 경로를 사용하면 `FileNotFoundException`을 방지할 수 있습니다.

```java
String dataDir = "C:/Projects/Data/";
```

> **프로 팁:** Project 파일을 전용 resources 폴더에 보관하고 `Paths.get(...)`를 사용해 플랫폼‑독립적인 경로를 지정하십시오.

## 2단계: MS Project 파일 로드
`Project` 클래스는 MS Project 파일을 나타내며 캘린더, 작업, 리소스 등에 접근할 수 있습니다. Project 파일을 `Project` 객체에 로드하면 메모리 내에 전체 파일이 로드되어 캘린더, 작업, 리소스 등을 사용할 수 있습니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 로드된 프로젝트에서 캘린더 예외를 어떻게 검색하나요?
프로젝트의 각 캘린더를 순회한 뒤, 해당 캘린더 내의 각 캘린더 예외를 순회합니다. 각 예외의 시작 및 종료 날짜를 출력합니다. 이 이중 루프는 프로젝트에 여러 캘린더(표준, 리소스, 사용자 정의)가 있더라도 모든 예외를 포착하도록 보장합니다. `CalendarException`을 검사하면 맞춤 보고서를 만들거나 일정 조정, 또는 데이터를 다른 시스템으로 내보낼 수 있습니다.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **출력이 표시되지 않음** | 프로젝트 파일에 캘린더 예외가 정의되어 있지 않음 | MS Project에서 예외(예: 휴일)가 설정되어 있는지 확인하십시오. |
| **`NullPointerException`** | `dataDir` 경로가 잘못되었거나 파일을 찾을 수 없음 | 디렉터리 경로를 다시 확인하고 `project.mpp` 파일이 존재하는지 확인하십시오. |
| **시간대 불일치** | 날짜가 UTC로 표시됨 | 필요에 따라 `calExc.getFromDate().toLocalDateTime()`을 사용해 로컬 시간으로 변환하십시오. |

## 자주 묻는 질문
### Aspose.Tasks가 다양한 버전의 MS Project 파일을 처리할 수 있나요?
예, Aspose.Tasks는 **모든 주요** MS Project 형식(MPP, MPT, XML)을 지원하며 2000년 버전부터 최신 릴리스까지 호환됩니다.

### Aspose.Tasks 무료 체험판을 제공하나요?
예, **[Aspose 무료 체험 다운로드 페이지](https://releases.aspose.com/)**에서 Aspose.Tasks 무료 체험판을 다운로드할 수 있습니다.

### Aspose.Tasks for Java 문서는 어디서 찾을 수 있나요?
**[Aspose.Tasks Java API 레퍼런스](https://reference.aspose.com/tasks/java/)**를 참고하십시오.

### Aspose.Tasks 지원을 어떻게 받을 수 있나요?
**[Aspose.Tasks 커뮤니티 포럼](https://forum.aspose.com/c/tasks/15)**에서 커뮤니티 지원을 받을 수 있습니다.

### Aspose.Tasks 임시 라이선스 옵션이 있나요?
예, **[임시 라이선스 구매 페이지](https://purchase.aspose.com/temporary-license/)**에서 임시 라이선스를 얻을 수 있습니다.

**추가 Q&A**

**Q:** *캘린더 예외를 검색한 후 수정할 수 있나요?*  
**A:** 물론입니다. `CalendarException.setFromDate()`와 `setToDate()`를 사용해 날짜를 조정한 뒤 `project.save(...)`로 프로젝트를 저장하면 됩니다.

**Q:** *Aspose.Tasks가 캘린더의 사용자 정의 필드를 보존하나요?*  
**A:** 예, 로드 및 저장 시 모든 사용자 정의 필드와 확장 속성이 유지됩니다.

## 결론
이 **asp tasks java tutorial**에서는 Aspose.Tasks for Java를 사용해 MS Project에서 캘린더 예외를 검색하는 방법을 배웠습니다. 이 간단한 단계를 따라 하면 Java 애플리케이션에 이 기능을 원활히 통합하여 보다 풍부한 일정 기능과 정확한 프로젝트 분석을 구현할 수 있습니다.

---

**마지막 업데이트:** 2026-11-19  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## 관련 튜토리얼

- [Aspose.Tasks for Java로 사용자 정의 캘린더 예외 만들기](/tasks/java/calendar-exceptions/)
- [Aspose.Tasks를 사용해 MS Project 캘린더 정보 검색하기](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [MS Project 캘린더에서 Java로 작업 주 읽기](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}