---
date: 2026-02-13
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 조작하면서 날짜 간의 일수를 계산하고,
  테스트 프로젝트를 생성하며, 사용자 정의 필드를 추가하는 방법을 배웁니다.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java로 날짜 사이의 일수 계산
url: /ko/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 날짜 사이의 일수 계산

## 소개
이 튜토리얼에서는 테스트 프로젝트를 생성하고, 사용자 정의 필드를 추가한 뒤, Aspose.Tasks for Java 라이브러리를 통해 Microsoft Project 수식을 사용하여 **날짜 사이의 일수 계산**을 수행합니다. 일정 생성, 마감일 계산, 보고서 자동화가 필요하든, Aspose.Tasks를 사용하면 데스크톱 설치 없이도 프로그래밍 방식으로 Project 데이터를 조작할 수 있습니다. 가이드를 마치면 확장 속성을 정의하고, 작업에 마감일을 설정하며, 프로젝트를 MPP 파일로 저장하는 실행 가능한 예제를 얻게 됩니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** 테스트 프로젝트 생성, 사용자 정의 필드 추가, 확장 속성 정의, 그리고 날짜 사이의 일수를 계산하는 수식을 사용한 작업 마감일 설정.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **어떤 IDE를 사용할 수 있나요?** JDK 8+를 지원하는 모든 Java IDE(IntelliJ IDEA, Eclipse, VS Code 등).  
- **구현에 얼마나 걸리나요?** 코드를 복사하고 실행하는 데 약 10‑15 분 정도 소요됩니다.

## Aspose.Tasks에서 “날짜 사이의 일수 계산”이란?
날짜 사이의 일수 계산은 하나의 날짜 필드(예: **Finish**)에서 다른 날짜 필드(예: **Deadline**)를 빼서 일수 차이를 숫자로 반환하는 Project 수식을 사용하는 것을 의미합니다. 일정 지연을 추적하거나, 여유 시간을 측정하거나, 맞춤형 보고서를 생성할 때 유용합니다.

## 날짜 사이의 일수 계산에 Aspose.Tasks를 사용하는 이유
- **전체 API 지원** – 모든 Project, Task, Resource 속성에 접근 가능.  
- **Office 설치 불필요** – 서버, CI 파이프라인, Docker 컨테이너에서 동작.  
- **크로스‑플랫폼** – 동일한 Java 코드로 Windows, Linux, macOS에서 실행.  
- **강력한 수식 엔진** – 프로젝트 파일 내부에서 `[Deadline] - [Finish]`와 같은 계산을 직접 정의 가능.

## 작업에 마감일 설정하는 방법
마감일을 설정하는 것은 간격을 계산하기 전 첫 번째 단계입니다. 마감일은 작업의 `Tsk.DEADLINE` 필드에 저장되며, `java.util.Calendar` 인스턴스를 사용해 지정할 수 있습니다.

## 확장 속성 정의 방법
확장 속성은 수식 결과를 저장할 사용자 정의 필드입니다. 한 번 정의하고, 가독성을 위해 별칭을 부여한 뒤, 날짜 차이를 수행하는 수식을 연결합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있어야 합니다:

- **Java Development Kit (JDK) 8+** – Oracle 웹사이트 또는 OpenJDK에서 다운로드.  
- **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받아 프로젝트 클래스패스 또는 Maven/Gradle 의존성에 추가.

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 단계별 가이드

### 단계 1: 사용자 정의 필드가 있는 테스트 프로젝트 생성
**테스트 프로젝트**를 만들고, 이후 수식 결과를 저장할 사용자 정의 필드를 추가합니다.

```java
Project project = CreateTestProjectWithCustomField();
```

> *팁:* `CreateTestProjectWithCustomField()`는 최소 일정을 만들고 수식 할당을 위한 확장 속성을 등록하는 도우미 메서드입니다.

### 단계 2: 확장 속성 정의 (사용자 정의 필드 추가)
다음으로 **확장 속성**을 정의합니다 – 즉, 사용자 정의 필드이며 친숙한 별칭을 부여합니다. 여기서 **사용자 정의 필드** 로직을 추가합니다.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias**는 Project에서 필드를 읽기 쉽게 만듭니다.  
- **Formula**는 작업의 *Finish* 날짜와 *Deadline* 사이의 일수를 계산합니다 – *날짜 사이의 일수 계산*의 핵심입니다.

### 단계 3: 작업에 마감일 설정 (마감일 작업 추가 및 작업 마감일 지정)
이제 특정 작업에 *Deadline* 속성을 설정하여 **마감일 작업** 데이터를 추가합니다.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 인스턴스는 정확한 마감 시점을 정의합니다.  
- `set(Tsk.DEADLINE, …)` **선택한 작업에 마감일을 설정**합니다.

### 단계 4: 프로젝트 저장 (Microsoft Project 파일 조작)
마지막으로 변경 사항을 MPP 파일에 저장하여 **Microsoft Project**를 조작합니다.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp`를 Microsoft Project에서 열면 사용자 정의 필드, 수식 결과 및 마감일이 일정에 반영된 것을 확인할 수 있습니다.

## 일반적인 문제 및 해결책

| 문제 | 해결책 |
|------|--------|
| **Formula not evaluating** | 속성의 `Formula` 문자열에 올바른 필드 이름(예: `[Deadline]`, `[Finish]`)이 사용되었는지 확인합니다. |
| **Task not found** | 예제에서 사용한 작업 ID(`1`)가 존재하는지 확인하고, `project.getRootTask().getChildren().size()` 로 디버그합니다. |
| **License exception** | API 메서드를 호출하기 전에 유효한 Aspose.Tasks 라이선스를 적용합니다 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 네, Aspose.Tasks는 .NET, Java 및 기타 플랫폼용 API를 제공하므로 원하는 언어로 **Microsoft Project** 파일을 조작할 수 있습니다.

**Q: Aspose.Tasks의 무료 체험판을 이용할 수 있나요?**  
A: 물론입니다. [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드하십시오.

**Q: Aspose.Tasks에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 공식 문서는 [Aspose.Tasks Java API 레퍼런스](https://reference.aspose.com/tasks/java/)에 있습니다.

**Q: Aspose.Tasks 지원을 어떻게 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 질문을 올리고 커뮤니티와 경험을 공유하세요.

**Q: 평가를 위해 임시 라이선스가 필요합니까?**  
A: 단기 테스트를 위한 임시 라이선스를 제공하며, [여기](https://purchase.aspose.com/temporary-license/)에서 요청할 수 있습니다.

**마지막 업데이트:** 2026-02-13  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}