---
date: 2025-11-29
description: Aspose.Tasks for Java를 사용하여 MS Project에서 캘린더 예외를 검색하는 방법을 배웁니다. 이 Aspose.Tasks
  Java 튜토리얼은 단계별 코드 예제를 제공합니다.
language: ko
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용한 캘린더 예외 가져오기 – ASP Tasks Java 튜토리얼
url: /java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks로 캘린더 예외 가져오기 – asp tasks java tutorial

## Introduction
이 **asp tasks java tutorial**에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project 파일에서 캘린더 예외를 가져오는 방법을 배웁니다. 캘린더 예외는 휴일이나 사용자 정의 근무 시간 규칙과 같은 비작업 기간을 나타내며, 이를 프로그래밍 방식으로 읽을 수 있는 능력은 자원 레벨링, 보고 및 사용자 정의 일정 로직에 필수적입니다. 전체 과정을 단계별로 안내하므로 자신만의 Java 애플리케이션에 이 기능을 자신 있게 통합할 수 있습니다.

## Quick Answers
- **What does this tutorial cover?** Aspose.Tasks for Java를 사용하여 MPP 파일에서 캘린더 예외를 가져오는 방법.  
- **How long does implementation take?** 기본 설정에 약 10‑15분 소요.  
- **Prerequisites?** JDK, Aspose.Tasks for Java, 그리고 IDE(IntelliJ IDEA 또는 Eclipse).  
- **Do I need a license?** 개발 단계에서는 무료 체험판으로 충분하며, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **Supported Project versions?** 모든 주요 MS Project 포맷(MPP, MPT, XML) 지원.

## What is asp tasks java tutorial?
**asp tasks java tutorial**는 Java 프로젝트 내에서 Aspose.Tasks API를 활용하는 방법을 설명합니다. 구체적인 코드 스니펫, 모범 사례 설명, 실제 시나리오를 제공하여 개발자가 Microsoft Project를 설치하지 않고도 Project 파일을 조작할 수 있도록 돕습니다.

## Why retrieve calendar exceptions?
캘린더 예외를 이해하면 다음을 수행할 수 있습니다:
- 휴일 및 사용자 정의 근무 일정에 맞춘 정확한 프로젝트 타임라인 생성
- 비작업일을 강조하는 맞춤형 보고 도구 구축
- ERP, HR 등 외부 시스템과 Project 캘린더 동기화

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [here](https://releases.aspose.com/tasks/java/)에서 다운로드 및 설치.  
3. **Integrated Development Environment (IDE)** – IntelliJ IDEA, Eclipse 등 원하는 IDE를 사용할 수 있습니다.

## Import Packages
Aspose.Tasks를 사용하기 위해 필요한 패키지를 먼저 가져와야 합니다:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **Pro tip:** `FileNotFoundException`을 방지하려면 절대 경로나 프로젝트 리소스 폴더에 상대적인 경로를 사용하세요.

## Step 2: Load MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```

위 코드는 지정된 경로의 MS Project 파일을 로드하여 새로운 `Project` 객체를 초기화합니다.

## Step 3: Retrieve Calendar Exceptions
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

여기서는 프로젝트 내 각 캘린더를 순회하고, 각 캘린더의 예외를 다시 순회하면서 예외의 시작 및 종료 날짜를 출력합니다.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **No output printed** | Project 파일에 캘린더 예외가 포함되어 있지 않음. | MS Project에서 예외(예: 휴일)가 정의되어 있는지 확인하세요. |
| **`NullPointerException`** | `dataDir` 경로가 잘못되었거나 파일을 찾을 수 없음. | 디렉터리 경로를 다시 확인하고 `project.mpp` 파일이 존재하는지 확인하세요. |
| **Time zone mismatch** | 날짜가 UTC로 표시됨. | 필요에 따라 `calExc.getFromDate().toLocalDateTime()`을 사용해 로컬 시간으로 변환하세요. |

## Frequently Asked Questions
### Can Aspose.Tasks handle different versions of MS Project files?
Yes, Aspose.Tasks supports various versions of MS Project files, including MPP, MPT, and XML formats.

### Is there a free trial available for Aspose.Tasks?
Yes, you can download a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).

### Where can I find documentation for Aspose.Tasks for Java?
You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

### How can I get support for Aspose.Tasks?
You can get support from the community forum [here](https://forum.aspose.com/c/tasks/15).

### Is there an option for temporary licenses for Aspose.Tasks?
Yes, you can obtain temporary licenses from [here](https://purchase.aspose.com/temporary-license/).

**Additional Q&A**

**Q:** *Can I modify calendar exceptions after retrieving them?*  
**A:** Absolutely. Use `CalendarException.setFromDate()` and `setToDate()` to adjust dates, then save the project with `project.save(...)`.

**Q:** *Does Aspose.Tasks preserve custom fields on calendars?*  
**A:** Yes, all custom fields and extended attributes are retained when loading and saving the project.

## Conclusion
이 **asp tasks java tutorial**에서는 Aspose.Tasks for Java를 사용하여 MS Project에서 캘린더 예외를 가져오는 방법을 배웠습니다. 간단한 단계들을 따라 하면 이 기능을 Java 애플리케이션에 원활히 통합하여 보다 풍부한 일정 기능과 정확한 프로젝트 분석을 구현할 수 있습니다.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}