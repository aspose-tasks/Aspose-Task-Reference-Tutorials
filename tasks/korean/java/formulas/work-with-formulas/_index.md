---
date: 2026-10-05
description: Aspose.Tasks for Java를 사용하여 테스트 프로젝트를 생성하고 날짜 사이의 일수를 계산하는 방법을 배우고, custom
  field를 추가하고, MPP 파일을 효율적으로 조작하는 방법을 알아보세요.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Aspose.Tasks에서 수식 사용하기
og_description: Aspose.Tasks for Java를 사용하여 테스트 프로젝트를 생성하고 날짜 사이의 일수를 계산합니다. 이 가이드는
  custom field를 추가하고, task deadlines를 설정하며, 프로젝트를 MPP 파일로 저장하는 방법을 보여줍니다.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: 테스트 프로젝트를 생성하고 날짜 사이의 일수를 계산하기
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: 테스트 프로젝트를 생성하고 날짜 사이의 일수를 계산하기
url: /ko/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 테스트 프로젝트 생성 및 날짜 사이 일수 계산

이 튜토리얼에서는 **테스트 프로젝트를 생성**하고 **날짜 사이 일수를 계산**하기 위해 사용자 정의 필드를 추가하고, 확장 속성을 정의하며, Aspose.Tasks Java 라이브러리를 통해 Microsoft Project 수식을 적용합니다. 일정 생성, 마감일 계산 또는 보고서 자동화가 필요하든, Aspose.Tasks는 데스크톱 설치 없이도 프로젝트 데이터를 프로그래밍 방식으로 조작할 수 있게 하며, 50개 이상의 입력 및 출력 형식을 지원하고 메모리 효율 모드에서 수백 페이지 파일을 처리합니다.

## 빠른 답변
- **튜토리얼은 무엇을 다루나요?** 테스트 프로젝트를 생성하고, 확장 속성을 정의하며, 작업 마감일을 설정하고, 날짜 사이 일수를 계산하는 수식을 사용하는 방법을 보여줍니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요한가요?** 개발에는 무료 체험판을 사용할 수 있으며, 프로덕션 사용에는 상용 라이선스가 필요합니다.  
- **어떤 IDE를 사용할 수 있나요?** JDK 8+을 지원하는 모든 Java IDE(IntelliJ IDEA, Eclipse, VS Code) 사용 가능.  
- **구현에 얼마나 걸리나요?** 코드를 복사하고 실행하는 데 대략 10‑15분 정도 소요됩니다.

## Aspose.Tasks에서 “날짜 사이 일수 계산”이란?
Aspose.Tasks에서 수식은 작업 필드를 참조하고 계산을 수행할 수 있는 문자열입니다. `[Deadline] - [Finish]`는 두 날짜 필드 사이의 일수 차이를 숫자로 반환하기 위해 Aspose.Tasks가 사용하는 수식 구문입니다. 결과는 전체 일수를 나타내는 숫자 값으로 저장되며, 이를 사용자 정의 필드에 표시하거나 추가 계산에 사용할 수 있습니다.

## 날짜 사이 일수 계산에 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 모든 Project, Task, Resource 속성에 대해 **전체 API 커버리지**를 제공하며, Windows, Linux, macOS에서 실행되고 **Microsoft Project 또는 Office 설치가 필요하지 않습니다**. 이 엔진은 일반 서버 하드웨어에서 **500개 이상의 작업**을 1초 미만에 처리할 수 있어 CI 파이프라인, Docker 컨테이너, 대량 배치 처리에 이상적입니다.

## 작업에 마감일 설정 방법
java.util.Calendar는 특정 순간을 나타내는 Java 클래스입니다. `java.util.Calendar` 값을 작업의 `Tsk.DEADLINE` 필드에 할당하여 마감일을 설정합니다. Calendar 인스턴스를 만든 후 연도, 월, 일을 원하는 마감일로 설정하고 `task.set(Tsk.DEADLINE, calendar);`를 호출합니다. 마감일은 프로젝트 파일에 저장되며 `[Deadline] - [Finish]`와 같은 수식에서 사용할 수 있습니다.

## 확장 속성 정의 방법
확장 속성은 수식 결과를 저장하는 사용자 정의 필드입니다. 한 번 생성하고 친숙한 별칭을 부여한 뒤 `[Deadline] - [Finish]` 표현식을 연결하면 모든 작업이 자동으로 간격을 계산합니다. `ExtendedAttribute`를 인스턴스화하고 Alias를 설정하고 수식을 할당한 뒤 프로젝트 컬렉션에 추가하여 생성합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- **Java Development Kit (JDK) 8+** – Oracle 웹사이트 또는 OpenJDK에서 다운로드합니다.  
- **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받아 프로젝트의 클래스패스 또는 Maven/Gradle 의존성에 추가합니다.

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 단계별 가이드

### 단계 1: 사용자 정의 필드가 있는 테스트 프로젝트 생성
우선 **테스트 프로젝트를 생성**하고 이후 수식 결과를 저장할 사용자 정의 필드를 추가합니다.

```java
Project project = CreateTestProjectWithCustomField();
```

> *팁:* `CreateTestProjectWithCustomField()`는 최소 일정을 만들고 수식 할당을 위해 확장 속성을 등록하는 도우미 메서드입니다.

### 단계 2: 확장 속성 정의 (사용자 정의 필드 추가)
다음으로 **확장 속성을 정의**합니다 – 즉 사용자 정의 필드이며, 친숙한 별칭을 부여합니다. 여기서 **사용자 정의 필드** 로직을 추가합니다.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias**는 Project에서 필드를 읽기 쉽게 만듭니다.  
- **Formula**는 작업의 *Finish* 날짜와 *Deadline* 사이 일수를 계산합니다 – *날짜 사이 일수 계산*의 핵심입니다.

### 단계 3: 작업에 마감일 설정 (마감일 작업 추가 및 작업 마감일 설정)
이제 특정 작업에 *Deadline* 속성을 설정하여 **마감일 작업** 데이터를 추가합니다.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 인스턴스는 정확한 마감 순간을 정의합니다.  
- `set(Tsk.DEADLINE, …)`는 선택한 작업의 **마감일을 설정**합니다.

### 단계 4: 프로젝트 저장 (Microsoft Project 파일 조작)
마지막으로 변경 사항을 MPP 파일에 저장하여 **Microsoft Project를 조작**합니다.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp`를 Microsoft Project에서 열어 사용자 정의 필드, 수식 결과 및 마감일이 일정에 반영된 것을 확인할 수 있습니다.

## 일반적인 문제와 해결책

| 문제 | 해결책 |
|-------|----------|
| **수식이 평가되지 않음** | 속성의 `Formula` 문자열이 올바른 필드 이름(예: `[Deadline]`, `[Finish]`)을 사용하고 있는지 확인하십시오. |
| **작업을 찾을 수 없음** | 작업 ID(`예제에서 1`)가 존재하는지 확인하고, `project.getRootTask().getChildren().size()`를 사용해 디버그하십시오. |
| **라이선스 예외** | API 메서드를 호출하기 전에 유효한 Aspose.Tasks 라이선스를 적용하십시오 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Java 및 기타 플랫폼용 API를 제공하므로 원하는 언어로 Microsoft Project 파일을 조작할 수 있습니다.

**Q: Aspose.Tasks의 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드하십시오.

**Q: Aspose.Tasks에 대한 자세한 문서는 어디서 찾을 수 있나요?**  
A: 공식 문서는 [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)에 있습니다.

**Q: Aspose.Tasks 지원을 어떻게 받을 수 있나요?**  
A: 커뮤니티에 질문하고 경험을 공유하려면 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

**Q: 평가를 위해 임시 라이선스가 필요합니까?**  
A: 단기 테스트를 위한 임시 라이선스가 제공되며, [임시 라이선스 요청 페이지](https://purchase.aspose.com/temporary-license/)에서 신청할 수 있습니다.

**마지막 업데이트:** 2026-10-05  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [MPP 파일 만들기 – Aspose.Tasks로 빈 프로젝트를 MPP 형식으로 생성 및 저장](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks와 Java로 확장 속성 만들기](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}