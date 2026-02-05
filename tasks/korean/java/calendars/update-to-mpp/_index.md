---
date: 2026-02-05
description: Aspose.Tasks for Java를 사용하여 달력에 휴일을 추가하고, 달력을 프로젝트에 할당하며, MS Project
  파일을 MPP 형식으로 저장하는 방법을 배웁니다.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용해 달력에 휴일을 추가하고 MPP로 저장
url: /ko/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 캘린더에 휴일 추가 및 Aspose.Tasks로 MPP 저장

## 소개

현대 프로젝트 관리에서는 **캘린더 파일에 휴일을 추가**하고 **MS Project 캘린더**를 만든 뒤, 네이티브 MPP 형식으로 일정을 공유해야 할 때가 많습니다. 여러 소스에서 타임라인을 통합하거나 레거시 데이터를 마이그레이션할 때, 프로그래밍 방식으로 캘린더를 생성하면 수동 오류를 없애고 전달 속도를 높일 수 있습니다. 이 튜토리얼에서는 MS Project에서 캘린더를 만들고, 휴일을 커스터마이징하며, **캘린더를 프로젝트에 할당**하고, 마지막으로 **Aspose.Tasks Java API**를 사용해 프로젝트를 MPP로 **변환**하는 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** 캘린더에 휴일을 추가하고, 프로젝트에 할당한 뒤, Aspose.Tasks for Java로 MPP 파일로 저장하는 방법.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상 (JDK 8+).  
- **캘린더를 커스터마이징할 수 있나요?** 예 – 작업 시간, 예외, 휴일 등을 추가할 수 있습니다.  
- **구현 소요 시간은?** 기본 캘린더는 약 10‑15 분 정도 소요됩니다.  

## “create calendar MS Project”란?

MS Project 캘린더를 만든다는 것은 작업 일정에 영향을 주는 작업일, 작업시간, 예외 등을 프로그래밍 방식으로 정의하는 것을 의미합니다. Aspose.Tasks를 사용하면 **java create project calendar**를 수행하고, 수정하며, Microsoft Project UI를 전혀 열지 않고도 변경 사항을 저장할 수 있습니다.

## 왜 Aspose.Tasks를 사용하나요?

- **완전한 .NET/Java 호환성** – Java를 지원하는 모든 플랫폼에서 동작합니다.  
- **COM이나 Office 설치 불필요** – 서버‑사이드 자동화와 **automate schedule generation**에 최적화되었습니다.  
- **풍부한 API** – 사용자 정의 작업 주와 휴일을 포함한 모든 캘린더 속성을 지원합니다.  
- **직접 MPP 출력** – 중간 변환 없이 **save project as MPP**가 가능합니다.

## 사전 요구 사항

1. **Java Development Kit (JDK) 8+** – `java -version` 명령이 1.8 이상을 표시하는지 확인합니다.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose 웹사이트](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 편집기.  
4. **기본 Java 지식** – 클래스, 메서드, 파일 I/O에 익숙해야 합니다.

## 캘린더에 휴일 추가하기

아래에서는 환경 설정부터 최종 MPP 파일 저장까지 각 단계를 순차적으로 설명합니다. 코드 블록은 원본 튜토리얼과 동일하게 유지되며, 주변 설명만 한국어로 확장했습니다.

### 단계 1: 필요한 패키지 가져오기

먼저 Aspose.Tasks 클래스와 Java 유틸리티를 가져옵니다.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 단계 2: 데이터 디렉터리 설정

입력 템플릿과 출력 파일이 위치할 디렉터리를 정의합니다. 플레이스홀더를 실제 경로로 교체하세요.

```java
String dataDir = "Your Data Directory";
```

### 단계 3: 입력 및 출력 파일 이름 정의

기존 MPP 파일(또는 빈 프로젝트)을 로드하고, 결과를 새 파일에 기록합니다.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 단계 4: 프로젝트 로드 및 새 캘린더 추가

소스 파일에서 `Project` 인스턴스를 생성하고 **“Calendar 1”**이라는 이름의 캘린더를 추가합니다.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 단계 5: 캘린더 커스터마이징 (선택 사항)

특정 작업 시간, 휴일, 예외가 필요하면 자체 헬퍼 메서드를 호출합니다. 샘플에서는 `GetTestCalendar`를 플레이스홀더로 사용합니다.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **팁:** `cal1.getWeekDays()`를 직접 조작해 주간 작업 시간을 설정하거나, `cal1.getExceptions()`를 사용해 **add holidays to calendar**를 수행할 수 있습니다.

### 단계 6: 캘린더를 프로젝트에 할당

프로젝트가 모든 일정 계산에 새로 만든 캘린더를 사용하도록 지정합니다.

```java
project.set(Prj.CALENDAR, cal1);
```

### 단계 7: 프로젝트를 MPP로 저장

`SaveFileFormat.Mpp` 옵션을 사용해 **convert project to MPP**합니다.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 단계 8: 성공 완료 확인

간단한 콘솔 메시지를 통해 오류 없이 프로세스가 끝났음을 알립니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 사용 사례

- **자동 일정 생성** – 주간 스프린트와 같은 반복 프로젝트.  
- **레거시 CSV 또는 Excel 캘린더**를 완전한 MS Project 파일로 마이그레이션.  
- **서버‑사이드 보고** – 웹 서비스가 요청 시 MPP 파일을 반환하도록 구현.

## 문제 해결 및 흔한 함정

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir`가 존재하지 않는 폴더를 가리킴 | 디렉터리가 존재하는지 확인하거나 프로그램matically 생성합니다. |
| Calendar not applied to tasks | 작업이 기본 캘린더를 계속 참조함 | `Prj.CALENDAR`를 설정한 뒤, 이전에 오버라이드된 경우 각 작업의 `Task.CALENDAR`도 업데이트합니다. |
| Output file is 0 KB | 쓰기 권한 부족 | JVM을 적절한 파일 시스템 권한으로 실행하거나 쓰기 가능한 경로를 선택합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java는 다양한 버전의 MS Project와 호환되나요?**  
A: 예, Aspose.Tasks for Java는 Project 2007부터 최신 버전까지 광범위한 MS Project 버전을 지원하여 원활한 호환성을 보장합니다.

**Q: 프로젝트 요구 사항에 맞게 캘린더를 커스터마이징할 수 있나요?**  
A: 물론입니다. 작업일 정의, 사용자 정의 작업 주 설정, 휴일 추가, 그리고 하나의 프로젝트 파일 내에 여러 캘린더를 생성할 수 있습니다.

**Q: Aspose.Tasks for Java는 문제 해결 및 지원을 제공하나요?**  
A: 예, Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다. [여기](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

**Q: Aspose.Tasks for Java의 무료 체험판이 있나요?**  
A: 예, 완전 기능을 갖춘 무료 체험판을 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻나요?**  
A: 임시 라이선스는 Aspose 웹사이트에서 [여기](https://purchase.aspose.com/temporary-license/)를 통해 요청할 수 있습니다.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}