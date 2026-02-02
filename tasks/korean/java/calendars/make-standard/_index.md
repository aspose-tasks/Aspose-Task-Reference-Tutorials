---
date: 2026-02-02
description: Aspose.Tasks를 사용하여 Java에서 기본 프로젝트 캘린더를 설정하고 MS Project 캘린더를 만드는 방법을 배웁니다.
  이 단계별 가이드는 표준 캘린더를 추가하고 Aspose.Tasks를 효과적으로 사용하는 방법을 보여줍니다.
linktitle: Set Default Project Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 기본 프로젝트 캘린더 설정 – 가이드
url: /ko/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 기본 프로젝트 캘린더 설정 – 가이드

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project 파일에 **기본 프로젝트 캘린더** 객체를 설정하는 방법을 배웁니다. **표준 MS Project 캘린더**를 만들고, 이를 기본(표준) 캘린더로 지정한 뒤 프로젝트 파일을 저장하는 과정을 단계별로 안내합니다. 가이드를 마치면 Java 기반 프로젝트 관리 솔루션에 캘린더 생성을 통합하고 **MS Project 캘린더** 객체를 프로그래밍 방식으로 생성할 수 있습니다.

## 빠른 답변
- **“표준 캘린더”란 무엇인가요?** 사용자 지정 캘린더를 지정하지 않은 작업이 사용하는 기본 작업 시간 정의입니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (“Aspose 사용 방법” 부분).  
- **라이선스가 필요한가요?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **생성되는 파일 형식은?** XML 기반 Microsoft Project 파일(`.xml`).  
- **구현 소요 시간은?** 기본 캘린더 하나를 만드는 데 약 5‑10분 정도 소요됩니다.

## Microsoft Project에서 표준 캘린더란?
**표준 캘린더**는 프로젝트의 기본 작업 일과 시간을 정의합니다. 표준 캘린더를 추가하면, 특정 캘린더가 할당되지 않은 모든 작업이 해당 일정에 따라 실행됩니다.

## Aspose.Tasks로 캘린더를 만드는 이유
Aspose.Tasks는 순수 Java API를 제공하여 Microsoft Project가 설치되지 않은 환경에서도 프로젝트 파일을 조작할 수 있게 해줍니다. 이는 서버‑사이드 자동화, CI 파이더** 객체를.Tasks로
기본 프로젝트 캘린더를 설정하는 것은 새로 승격시키는 것만큼 간단합니다. 아래 단계에서 전체 과정을 안내합니다.

## 사전 요구 사항
시작하기 배[download page](https://releases.aspose.com하고 J 필요한 import는 하나뿐입니다:

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
생성된 프로젝트 파일을 저장할 위치를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 머신의 절대 경로(예: `C:/Projects/Output/`)로 교체하세요.

### 단계 2: Project 인스턴스 생성
캘린더를 보관할 새, 빈 Project 객체를 인스턴스화합니다.

```java
Project project = new Project();
```

### 단계 3: 캘린더 정의 및 표준 캘린더로 지정
**“My Cal”**이라는 새 캘린더를 추가하고 이를 기본 프로젝트 캘린더로 승격시킵니다.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **팁:** `makeStandardCalendar` 메서드는 제공된 캘린더를 프로젝트의 기본 캘린더로 자동 지정합니다. 즉, **기본 프로젝트 캘린더** 기능을 구현할 때 정확히 필요한 동작입니다.

### 단계 4: 프로젝트 저장
새 캘린더가 포함된 프로젝트를 XML 파일로 영구 저장합니다.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

다른 Project 버전을 원한다면 파일 이름이나 형식(`SaveFileFormat.Pp`)을 변경하면 됩니다.

### 단계 5: 완료 메시지 표시
프로세스가 오류 없이 끝났음을 시각적으로 확인할 수 있습니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|------|------|--------|
| **파일을 찾을 수 없음** | `dataDir`가 존재하지 않는 폴더를 가리킴 | 폴더를 생성하거나 절대 경로를 사용 |
| **라이선스 예외** | 프로덕션 환경에서 유효한 Aspose.Tasks 라이선스 없이 실행 | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 로 라이선스 적용 |
| **캘린더가 비어 있음** | 작업 시간 정의를 추가하지 않음 | 필요에 따라 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 등으로 사용자 정의 작업 시간을 추가 |

## 자주 묻는 질문

**Q: Aspose.Tasks가 모든 버전의 Microsoft Project와 호환되나요?**  
A: 네, Aspose.Tasks는 2000 버전부터 최신 릴리스까지 다양한 Microsoft Project 버전을 지원합니다.

**Q: 캘린더 설정을 더 세부적으로 커스터마이즈할 수 있나요?**  
A: 물론입니다! `WeekDay`와 `WorkingTime` 클래스를 사용해 작업 일, 예외, 특정 작업 시간을 자유롭게 정의할 수 있습니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준 애플리케이션에 적합한가요?**  
A: 예. 이 라이브러리는 고성능·확장성을 염두에 두고 설계되었으며, 대용량 Project 파일을 위한 포괄적인 지원을 제공합니다.

**Q: 개발자를 위한 기술 지원이 제공되나요?**  
A: 네, Aspose는 전용 포럼, 티켓 기반 지원, 그리고 풍부한 문서를 제공하여 문제 해결을 빠르게 도와줍니다.

**Q: 구매 전 Aspose.Tasks를 체험해볼 수 있나요?**  
A: 예. [website](https://purchase.aspose.com/buy)에서 무료 체험 버전을 다운로드받아 모든 기능을 평가해볼 수 있습니다.

## 결론
이제 Aspose.Tasks for Java에서 **기본 프로젝트 캘린더** 객체를 설정하고, 이를 표준 캘린더로 지정한 뒤 프로젝트 파일을 저장하는 방법을 알게 되었습니다. 이 기능을 활용하면 프로젝트 일정 자동화, 일관된 작업 시간 적용, 그리고 Microsoft Project 데이터를 직접 Java 애플리케이션에 통합할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-02