---
date: 2026-01-31
description: Aspose.Tasks for Java를 사용하여 프로젝트 캘린더를 만들고, 휴일 캘린더를 추가하며, 프로젝트 XML을 내보내는
  방법을 배웁니다.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java로 프로젝트 캘린더 만들기
url: /ko/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java로 프로젝트 캘린더 만들기

## 소개
현대 프로젝트 관리 워크플로우에서, 프로그래밍 방식으로 **프로젝트 캘린더의 수동 편집을 절약할 수 있습니다. Aspose.Tasks for Java는 개발자에게 데스크톱 클라이언트를 열지 조작할 수 있는 API를 제공합니다. 이 튜토리얼에서는 **캘린더 추가 방법**, **MS Project 캘린더 생성 방법**, 그리고 **프로젝트 XML 내보내기**를 몇 줄의 Java **“프로젝트 캘린더 만들기”가 무엇을 의미하나요?**  
  코드를 통해 Microsoft Project 파일 내부에 새로운 작업 시간 정의(캘린더)를 생성하는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?**  
  Aspose.Tasks for더를 관리하기 위해 `Calendar` 클래스와 `Project` 컨테이너를 제공합니다.  
- ** 테스트용으로는 임시 평가 라이선스로 충분하지만, 실제 운영에서는 정식 라이을 XML로 내보낼 수 있나요?**  
  예—`SaveFileFormat.Xml`제 조건은 무엇인가요?**  
  Java JDK 8 이상과 클래스패스에 포함된 Aspose.Tasks for Java JAR가 필요합니다.  

## “프로젝트 캘린더 만들기”란?
프로젝트 캘린더를 생성한다는 것은 프로젝트의 작업일, 휴가 작업, 리소스 또는 전체 프로젝트에 연결되면 모든 일정 계산이 정의된 작업 시간을 기준으로 수행됩니다.

## 왜 Aspose.Tasks for Java를 사용해 프로젝트 캘린더를 만들까요?
- **Full control** – UI 없이도 다수의 프로젝트에 걸쳐 대량 캘린더 생성을 자동화합니다.  
- **Cross‑version compatibility** – Project 2007, 2010, 2013, 2016 및 이후 파일과 호환됩니다.  
- **No Microsoft Project installation** – 서버나 CI 파이프라인 어디서든 실행할 수 있습니다.  
- **Export flexibility** – XML, MPP 또는 기타 지원 형식으로 저장할 수 있습니다.  

## 전제 조건
- **Java Development Kit (JDK) 8 이상**이 설치되고 구성되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리 – [공식 웹사이트](https://releases.aspose.com/tasks/java/)에서 다운로드하고 JAR를 프로젝트 클래스패스에 추가합니다.  
- 선호하는 IDE 또는 빌드 도구(Maven/Gradle)를 사용합니다.  

## 단계별 가이드

### 단계 1: 필요한 Aspose.Tasks 패키지 가져오기
먼저, Aspose.Tasks 클래스를 가져와 프로젝트와 캘린더를 다룰 수 있도록 합니다.

```java
import com.aspose.tasks.*;
```

### 단계 2: 데이터 디렉터리 경로 설정
생성된 프로젝트 파일이 저장될 위치를 정의합니다. 플레이스홀더를 실제 머신의 절대 경로나 상대 경로로 교체하세요.

```java
String dataDir = "Your Data Directory";
```

### 단계 3: 새로운 Project 인스턴스 생성
`Project – 이는 채울 수 있는 빈 Microsoft Project 파일을 나타냅니다.

```java
Project prj = new Project();
```

### 단계 4: 추가할 캘린더 정의 항목을 생성합니다 세 개의 캘린더를 추가하지만, 필요에 따라 원하는 만큼 추가하고 이후에 작업 시간을 설정할 수 있습니다.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **팁:** 캘린더를 추가한 후 `cal1.getWeekDays().add(...)`로 작업일을 맞춤 설정하고 `cal1.getBaseCalendar().setWorkingTime(...)`으로 일일 작업 시간을 지정할기)
새로 추가된 캘린더를 포함한 프로젝트를 XML 파일로 저장합니다. 이 형식은 확인하기 쉽고 다양한 도구와 호환됩니다.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```


작업이 성공적으로 완료되었음을 사용자에게 알립니다.

```java
System.out.println("Process completed Successfully");
```

이 여섯 단계만 따라 하면 **프로젝트 캘린더를 성공적으로 만들고**, Microsoft Project 파일에 추가했으며, **프로젝트를 XML로 내보냈**습니다.

## 일반적인 문제 및 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **`prj.getCalendars()`에서 `NullPointerException`** | Project 객체가 올바르게 초기화되지 않았습니다. | 캘린더에 접근하기 전에 `new Project()`가 호출되었는지 확인하세요. |
| **저장 시 파일을 찾을 수 없음** | `dataDir`이 존재하지 않는 폴더를 가리키고 있습니다. | 경로 info”로 일정에 맞는 의미 있는 이름(예: “US Holiday Calendar”)으로 교체하세요. |
| **저장된 XML을 MS Project에서 열 수 없음** | 오래된 Aspose.Tasks 버전을 사용하고 있습니다. | 최신 Aspose.Tasks for Java 릴리스로 업데이트하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 여러 예외가 있는 복잡한 캘린더를 처리할 수 있나요?**  
A: 예 – 캘린더를 추가한 후 `WeekDay` 및 `Exception` 클래스를 사용해 예외, 작업 시간 및 비작업일을 특정 작업에 할당할 수 있나요?**  
A: 물론입니다. `prj.getRootTask().getChildren().add("Task Name")`으로 작업을 가져온 뒤 `task.set(Tsk.CALENDAR, cal3);`을 설정하면 됩니다.

**Q: 라이브러리가 MPP와 같은 다른 형식으로 저장을 지원하나요?**  
A: 예. 필요에 따라 `SaveFileFormat.Xml`을 `SaveFileFormat.Mpp` 또는 `SaveFileFormat.P6`으로 교체하면 됩니다.

**Q: 개발 빌드에 라이선스가 필요합니까?**  
A: 테스트에는 임시 평가 라이선스로 충분하지만, 실제 배포에는 정식 라이선스가 필요합니다.

**Q: 문제가 발생하면 어디에서 도움을 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼이 좋은 자료입니다: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

## 결론
Aspose.Tasks for Java를 사용하면 프로그래밍 방식으로 **프로젝트 캘린더를 만들고**, 일정 규칙을 맞춤 설정하며, **프로젝트 XML을 내보낼** 수 있습니다. 이 자동화는 수동 작업을 줄이고 인간 오류를 없애며 대규모 프로젝트 포트폴리오를 일괄 처리할 수 업데이트:** 2026-01-31  
**테스트 Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}