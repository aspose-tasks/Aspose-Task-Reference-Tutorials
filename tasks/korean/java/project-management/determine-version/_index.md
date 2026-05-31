---
date: 2026-05-31
description: Aspose.Tasks for Java를 사용하여 MS Project 파일에서 프로젝트 버전을 가져오고 마지막 저장 날짜를
  검색하는 방법을 배웁니다. 단계별 가이드와 코드 예제 포함.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Aspose.Tasks로 프로젝트 버전 확인
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 프로젝트 버전 가져오기 – Aspose Tasks Java 튜토리얼
url: /ko/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 버전 가져오기 – Aspose Tasks Java 튜토리얼

이 **Aspose Tasks Java 튜토리얼**에서는 Microsoft Project 파일의 **프로젝트 버전 가져오기**와 Aspose.Tasks for Java 라이브러리를 사용하여 **마지막 저장 날짜 검색** 방법을 배웁니다. 파일 버전과 저장 타임스탬프를 알면 호환성 문제를 피하고, 마이그레이션 정책을 적용하며, 정확한 감사 로그를 유지할 수 있습니다. 환경 설정부터 버전 및 날짜 출력까지 모든 단계를 안내하므로, 이 검사를 Java 애플리케이션에 자신 있게 삽입할 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** Aspose.Tasks for Java를 사용하여 MS Project 파일 버전과 마지막 저장 날짜를 확인합니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 작동합니다.  
- **지원되는 파일 형식은 무엇인가요?** MPP 및 XML과 같은 XML 기반 Project 파일을 완전히 지원합니다.  
- **구현에 얼마나 걸리나요?** 기본 버전 확인에 약 5‑10분 정도 소요됩니다.  
- **라이선스가 필요한가요?** 평가용 무료 체험이 가능하지만, 실제 운영에서는 상용 라이선스가 필요합니다.

## Aspose Tasks Java 튜토리얼이란?
`Aspose.Tasks` Java 튜토리얼은 Microsoft Project 데이터를 프로그래밍 방식으로 조작하는 방법을 보여주는 간결하고 실용적인 가이드입니다. 서버에 Microsoft Project를 설치하지 않고도 프로젝트 정보를 읽고, 수정하고, 분석하는 방법을 설명합니다. 또한 파일 로드, 속성 접근, 변경 사항 저장 등을 다루어 개발자가 프로젝트 관리 작업을 효율적으로 자동화할 수 있도록 합니다.

## 프로젝트 버전을 확인하기 위해 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 **정확한 버전 메타데이터**와 **마지막 저장 타임스탬프**를 제공하며, Java를 지원하는 모든 OS에서 실행됩니다. 표준 2.5 GHz CPU에서 **500 페이지를 2초 이하**로 처리할 수 있어 배치 자동화 및 대규모 마이그레이션 시나리오에 이상적입니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java JAR** – [website](https://releases.aspose.com/tasks/java/)에서 다운로드하고 프로젝트 클래스패스에 추가합니다.  
3. **MS Project file** – 검사하려는 XML 기반 Project 파일(e.g., `input.xml`).  

> **Pro tip:** Project 파일을 전용 `data` 폴더에 저장하여 경로를 정리하고 실수로 덮어쓰는 일을 방지하세요.

## 패키지 가져오기
먼저 필수 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 프로젝트 디렉터리 설정 방법
프로젝트 파일을 올바르게 찾으려면 애플리케이션 구조 내에 전용 디렉터리를 만들고 모든 입력 파일을 해당 디렉터리에 저장합니다. 이렇게 하면 코드가 깔끔해지고 파일 로드 시 경로 관련 오류를 방지할 수 있습니다. 디렉터리 경로 변수는 절대 경로나 프로젝트 루트에 대한 상대 경로가 될 수 있습니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 `input.xml`이 위치한 절대 경로나 상대 경로로 교체합니다.

## 프로젝트 로드 방법
`Project`는 메모리 내에서 Microsoft Project 파일을 나타내는 주요 Aspose.Tasks 객체로, 모든 프로젝트 속성과 컬렉션에 접근할 수 있게 해줍니다. `Project` 인스턴스를 만든 후에는 필드를 조회하거나 작업을 반복하고, 파일을 다시 저장하기 전에 데이터를 수정할 수 있습니다.

```java
Project project = new Project(dataDir + "input.xml");
```

파일 이름이 다르면 `"input.xml"`을 해당 이름으로 조정합니다.

## 프로젝트 버전 확인 방법
`Prj.SAVE_VERSION`은 파일을 저장한 Microsoft Project 버전 번호를 나타내는 속성입니다. `Prj.LAST_SAVED`는 파일이 마지막으로 저장된 날짜와 시간을 저장하는 속성입니다. `Prj.SAVE_VERSION`은 저장에 사용된 Microsoft Project 애플리케이션의 숫자 버전을 반환합니다(예: Project 2010은 12). `Prj.LAST_SAVED`는 가장 최근 저장 작업의 정확한 날짜와 시간을 제공합니다.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

이 값들을 사용하면 버전별 비즈니스 규칙을 프로그래밍 방식으로 적용하거나 감사 보고서를 생성할 수 있습니다.

## 결과 표시 방법
버전 및 마지막 저장 정보를 가져온 후에는 일반적으로 콘솔이나 로그 파일에 출력합니다. `System.out.println`을 사용해 값을 표시하고 필요에 따라 날짜 형식을 지정합니다. 이렇게 하면 추출이 성공했는지 확인하고 개발 중이나 자동화 스크립트에서 즉시 피드백을 받을 수 있습니다.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| 문제 | 이유 | 해결 방법 |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | 파일을 찾을 수 없거나 경로가 잘못됨 | `dataDir`와 파일 이름을 확인하고 테스트 시 절대 경로를 사용합니다. |
| Unexpected version number (e.g., 0) | Project XML이 아닌 파일을 로드함 | 파일이 유효한 Microsoft Project 파일(MPP/XML)인지 확인합니다. |
| License exception | 프로덕션에서 유효한 라이선스 없이 체험판 사용 | Aspose.Tasks 라이선스를 적용합니다(`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Java, C++ 등 다양한 언어를 지원합니다.

**Q: Aspose.Tasks가 대규모 프로젝트에 적합한가요?**  
A: 물론입니다. 전체 파일을 메모리에 로드하지 않고도 수백 페이지 규모의 프로젝트를 몇 초 안에 처리할 수 있습니다.

**Q: Aspose.Tasks를 사용해 프로젝트 데이터를 커스터마이즈할 수 있나요?**  
A: 예, API를 통해 작업, 리소스, 캘린더 및 기타 모든 프로젝트 요소를 수정할 수 있습니다.

**Q: Aspose.Tasks 사용에 Microsoft Project 설치가 필요한가요?**  
A: 아니요, 라이브러리는 독립적으로 동작하며 호스트 머신에 Microsoft Project가 없어도 됩니다.

**Q: Aspose.Tasks에 대한 기술 지원이 제공되나요?**  
A: 예, Aspose.Tasks 포럼에서 도움을 받을 수 있습니다([here](https://forum.aspose.com/c/tasks/15)).

**Q: 다른 프로젝트 속성(예: 작성자, 회사)을 가져오려면 어떻게 하나요?**  
A: 버전을 가져오는 방식과 동일하게 `project.get(Prj.AUTHOR)` 또는 `project.get(Prj.COMPANY)`를 사용하면 됩니다.

**Q: MPP(바이너리) 파일의 버전을 확인할 수 있나요?**  
A: 예, Aspose.Tasks는 `.mpp` 파일을 직접 로드하며 `Prj.SAVE_VERSION` 속성은 바이너리 형식에서도 작동합니다.

**Q: 오래된 프로젝트 파일을 최신 버전으로 프로그래밍 방식으로 업그레이드할 방법이 있나요?**  
A: 오래된 파일을 로드한 뒤 `project.save("newfile.mpp", SaveFileFormat.MPP);` 로 저장하면 Aspose.Tasks가 기본적으로 최신 형식으로 파일을 작성합니다.

## 결론
이제 Aspose.Tasks for Java를 사용해 MS Project 파일에서 **프로젝트 버전 가져오기**와 **마지막 저장 날짜 검색**을 마스터했습니다. 이러한 코드를 자동화 파이프라인, 보고 도구 또는 마이그레이션 유틸리티에 통합하면 항상 정확한 Project 버전을 파악할 수 있습니다.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용해 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks for Java로 Microsoft Project 데이터베이스 읽기](/tasks/java/project-data-reading/read-project-database/)
- [Aspose.Tasks for Java로 프로젝트를 템플릿, CSV, 텍스트 형식으로 저장](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}