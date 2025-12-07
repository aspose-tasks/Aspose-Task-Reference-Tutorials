---
date: 2025-12-07
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 조작하면서 **테스트 프로젝트 생성**
  및 **사용자 정의 필드 추가** 방법을 배웁니다.
language: ko
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java로 테스트 프로젝트 생성 및 수식 사용
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java로 테스트 프로젝트 생성 및 수식 사용

## 소개
이 튜토리얼에서는 **테스트 프로젝트** 파일을 만들고, 사용자 정의 필드를 추가한 뒤, Aspose.Tasks for Java 라이브러리를 사용해 MS Project 수식을 적용하는 방법을 배웁니다. Aspose.Tasks를 사용하면 **Microsoft Project** 데이터를 프로그래밍 방식으로 손쉽게 **조작**할 수 있습니다—일정 생성, 날짜 계산, 보고서 자동화 등 어떤 작업이든 가능합니다. 가이드를 마치면 확장 속성을 정의하고, 작업에 마감일을 설정하며, 프로젝트를 MPP 파일로 저장하는 실행 가능한 예제를 얻게 됩니다.

## 빠른 답변
- **이 튜토리얼에서 다루는 내용은?** 테스트 프로젝트 생성, 사용자 정의 필드 추가, 확장 속성 정의, 수식을 이용한 작업 마감일 설정.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요한가요?** 개발 단계에서는 무료 체험판으로 가능하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **어떤 IDE를 사용할 수 있나요?** JDK 8 이상을 지원하는 모든 Java IDE (IntelliJ IDEA, Eclipse, VS Code 등).  
- **구현 시간은 얼마나 걸리나요?** 코드를 복사하고 실행하는 데 약 10‑15 분 정도 소요됩니다.

## Aspose.Tasks에서 “테스트 프로젝트”란?
**테스트 프로젝트**는 기능을 시연하거나 검증하기 위해 프로그래밍 방식으로 생성된 가벼운 Microsoft Project 파일입니다. 최소한의 작업, 리소스, 사용자 정의 필드만 포함되어 있어 실제 프로젝트 데이터에 영향을 주지 않고 자유롭게 조작할 수 있습니다.

## Microsoft Project 조작에 Aspose.Tasks를 사용하는 이유
- **전체 API 지원** – 모든 Project, Task, Resource 속성에 접근 가능.  
- **Office 설치 불필요** – 서버, CI 파이프라인, Docker 컨테이너에서도 동작.  
- **크로스‑플랫폼** – 동일한 Java 코드로 Windows, Linux, macOS에서 실행.  
- **강력한 수식 엔진** – 프로젝트 파일 내부에서 날짜, 기간, 사용자 정의 필드를 직접 계산.

## 사전 요구 사항
시작하기 전에 다음 항목을 준비하세요:

- **Java Development Kit (JDK) 8+** – Oracle 웹사이트 또는 OpenJDK에서 다운로드.  
- **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받아 프로젝트 클래스패스 또는 Maven/Gradle 의존성에 추가.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 단계별 가이드

### 단계 1: 사용자 정의 필드가 포함된 테스트 프로젝트 생성
**테스트 프로젝트**를 만들고, 이후 수식 결과를 저장할 사용자 정의 필드를 추가합니다.

```java
Project project = CreateTestProjectWithCustomField();
```

> *팁:* `CreateTestProjectWithCustomField()`는 최소 일정과 확장 속성을 생성해 수식 할당을 준비하는 헬퍼 메서드입니다.

### 단계 2: 확장 속성 정의 (사용자 정의 필드 추가)
다음으로 **확장 속성**—즉 사용자 정의 필드—을 정의하고 친숙한 별칭을 지정합니다. 여기서 **사용자 정의 필드** 로직을 추가합니다.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias**는 Project에서 필드를 읽기 쉽게 만들어 줍니다.  
- **Formula**는 작업의 *Finish* 날짜와 *Deadline* 사이의 일수를 계산합니다.

### 단계 3: 작업에 마감일 설정 (마감일 작업 추가 및 설정)
특정 작업에 *Deadline* 속성을 설정해 **마감일 작업** 데이터를 추가합니다.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 인스턴스가 정확한 마감일 시점을 정의합니다.  
- `set(Tsk.DEADLINE, …)` **선택한 작업의 마감일**을 설정합니다.

### 단계 4: 프로젝트 저장 (Microsoft Project 파일 조작)
마지막으로 **Microsoft Project**를 조작해 변경 내용을 MPP 파일에 저장합니다.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp`를 Microsoft Project에서 열면 사용자 정의 필드, 수식 결과, 마감일이 일정에 반영된 것을 확인할 수 있습니다.

## 일반적인 문제 및 해결 방법
| 문제 | 해결 방법 |
|-------|----------|
| **수식이 평가되지 않음** | 속성의 `Formula` 문자열에 올바른 필드 이름(`[Deadline]`, `[Finish]` 등)이 사용됐는지 확인하세요. |
| **작업을 찾을 수 없음** | 예제에서 사용한 작업 ID(`1`)가 존재하는지 확인하고, `project.getRootTask().getChildren().size()` 로 디버그해 보세요. |
| **라이선스 예외 발생** | API 메서드 호출 전에 유효한 Aspose.Tasks 라이선스를 적용하세요(`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 네, Aspose.Tasks는 .NET, Java 등 여러 플랫폼용 API를 제공하므로 원하는 언어로 **Microsoft Project** 파일을 **조작**할 수 있습니다.

**Q: Aspose.Tasks의 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드하세요.

**Q: Aspose.Tasks에 대한 자세한 문서는 어디서 찾을 수 있나요?**  
A: 공식 문서는 [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)에 있습니다.

**Q: Aspose.Tasks 지원을 받으려면 어떻게 해야 하나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 질문을 올리면 커뮤니티와 함께 문제를 해결할 수 있습니다.

**Q: 평가용 임시 라이선스가 필요한가요?**  
A: 단기 테스트를 위한 임시 라이선스를 제공하고 있습니다. [여기](https://purchase.aspose.com/temporary-license/)에서 요청하세요.

---

**마지막 업데이트:** 2025-12-07  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}