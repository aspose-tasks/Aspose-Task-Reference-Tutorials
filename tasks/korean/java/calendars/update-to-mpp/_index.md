---
date: 2025-12-03
description: Aspose.Tasks for Java를 사용하여 캘린더 MS Project를 만드는 방법, 프로젝트를 MPP로 변환하는 방법,
  그리고 프로젝트 MPP를 손쉽게 저장하는 방법을 배워보세요.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 캘린더 MS Project를 생성하고 MPP로 저장
url: /ko/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 캘린더 MS Project 만들기 및 MPP로 저장

## 소개

현대 프로젝트 관리에서는 종종 **캘린더 MS Project** 파일을 생성하고 이를 기본 MPP 형식으로 공유해야 합니다. 여러 소스에서 일정을 통합하거나 레거시 데이터를 마이그레이션하든, 프로그래밍 방식으로 캘린더를 생성하면 시간 절약과 수동 오류 방지에 도움이 됩니다. 이 튜토리얼에서는 MS Project에서 캘린더를 만들고, 사용자 정의하며, 마지막으로 Aspose.Tasks Java API를 사용하여 **프로젝트를 MPP로 변환**하는 전체 과정을 안내합니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** MS Project에서 캘린더를 만들고 Aspose.Tasks for Java를 사용하여 MPP 파일로 저장합니다.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상 (JDK 8+).  
- **캘린더를 사용자 정의할 수 있나요?** 예 – 작업 시간, 예외, 휴일을 추가할 수 있습니다.  
- **구현 시간은 얼마나 걸리나요?** 기본 캘린더의 경우 약 10‑15분 정도 소요됩니다.

## “create calendar MS Project”란 무엇인가요?

캘린더 MS Project를 만든다는 것은 Microsoft Project 파일 내에서 작업 일정에 영향을 주는 작업일, 작업시간 및 예외를 프로그래밍 방식으로 정의하는 것을 의미합니다. Aspose.Tasks를 사용하면 Microsoft Project UI를 열지 않고도 이러한 캘린더를 구축, 수정 및 저장할 수 있습니다.

## 이 작업에 Aspose.Tasks를 사용하는 이유는?

- **전체 .NET/Java 호환성** – Java를 지원하는 모든 플랫폼에서 작동합니다.  
- **COM이나 Office 설치 불필요** – 서버 측 자동화에 이상적입니다.  
- **풍부한 API** – 사용자 정의 작업 주 및 휴일을 포함한 모든 캘린더 속성을 지원합니다.  
- **직접 MPP 출력** – 중간 변환 없이 **프로젝트를 MPP로 저장**할 수 있습니다.

## 전제 조건

1. **Java Development Kit (JDK) 8+** – `java -version` 명령이 1.8 이상을 표시하는지 확인하세요.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose 웹사이트](https://releases.aspose.com/tasks/java/)에서 다운로드하세요.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 편집기.  
4. **기본 Java 지식** – 클래스, 메서드 및 파일 I/O에 익숙해야 합니다.

## 단계별 가이드

### Step 1: 필요한 패키지 가져오기

먼저, Aspose.Tasks 클래스와 Java 유틸리티를 범위에 가져옵니다.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: 데이터 디렉터리 설정

입력 템플릿과 출력 파일이 위치할 경로를 정의합니다. 플레이스홀더를 실제 머신의 경로로 교체하세요.

```java
String dataDir = "Your Data Directory";
```

### Step 3: 입력 및 출력 파일 이름 정의

기존 MPP 파일(또는 빈 프로젝트)을 로드하고 결과를 새 파일에 기록합니다.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: 프로젝트 로드 및 새 캘린더 추가

소스 파일에서 `Project` 인스턴스를 생성하고 **“Calendar 1”**이라는 이름의 캘린더를 추가합니다.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: 캘린더 사용자 정의 (선택 사항)

특정 작업 시간, 휴일 또는 예외가 필요하면 자체 헬퍼 메서드를 호출하세요. 샘플에서는 `GetTestCalendar`를 플레이스홀더로 사용합니다.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **팁:** `cal1.getWeekDays()`를 직접 조작하여 주의 각 요일에 대한 작업 시간을 설정할 수 있습니다.

### Step 6: 캘린더를 프로젝트에 할당

프로젝트가 모든 일정 계산에 새로 만든 캘린더를 사용하도록 지정합니다.

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: 프로젝트를 MPP로 저장

이제 `SaveFileFormat.Mpp` 옵션으로 저장하여 **프로젝트를 MPP로 변환**합니다.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: 성공 완료 확인

간단한 콘솔 메시지를 통해 오류 없이 프로세스가 완료되었음을 확인할 수 있습니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 사용 사례

- **반복 프로젝트(예: 주간 스프린트)를 위한 자동 일정 생성**.  
- **레거시 CSV 또는 Excel 캘린더를 완전한 MS Project 파일로 마이그레이션**.  
- **서버 측 보고** – 웹 서비스가 요청 시 MPP 파일을 반환합니다.

## 문제 해결 및 일반적인 함정

| Issue | Cause | Fix |
|-------|-------|-----|
| `project.save` 시 `NullPointerException` | `dataDir`가 존재하지 않는 폴더를 가리킴 | 디렉터리가 존재하는지 확인하거나 프로그래밍으로 생성하세요. |
| 캘린더가 작업에 적용되지 않음 | 작업이 여전히 기본 캘린더를 참조함 | `Prj.CALENDAR`를 설정한 후, 이전에 재정의된 경우 각 작업의 `Task.CALENDAR`도 업데이트하세요. |
| 출력 파일이 0 KB | 쓰기 권한이 없음 | JVM을 적절한 파일 시스템 권한으로 실행하거나 쓰기 가능한 경로를 선택하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 다양한 버전의 MS Project와 호환되나요?**  
A: 예, Aspose.Tasks for Java는 Project 2007부터 최신 릴리스까지 다양한 MS Project 버전을 지원하여 원활한 호환성을 보장합니다.

**Q: 특정 프로젝트 요구사항에 맞게 캘린더를 사용자 정의할 수 있나요?**  
A: 물론입니다. 작업일을 정의하고, 사용자 정의 작업 주를 설정하며, 휴일을 추가하고, 하나의 프로젝트 파일 내에 여러 캘린더를 만들 수도 있습니다.

**Q: Aspose.Tasks for Java는 문제 해결 및 지원을 제공하나요?**  
A: 예, Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다 [here](https://forum.aspose.com/c/tasks/15).

**Q: Aspose.Tasks for Java의 무료 체험판이 있나요?**  
A: 예, 완전한 기능을 제공하는 무료 체험판을 이용할 수 있습니다 [here](https://releases.aspose.com/).

**Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: Aspose 웹사이트에서 임시 라이선스를 요청할 수 있습니다 [here](https://purchase.aspose.com/temporary-license/).

**마지막 업데이트:** 2025-12-03  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}