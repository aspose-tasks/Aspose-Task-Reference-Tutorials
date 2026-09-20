---
date: 2026-09-20
description: Aspose.Tasks for Java를 사용하여 mpp 통화 기호를 추출하고 프로젝트 속성을 업데이트하는 방법을 배웁니다.
  몇 줄의 코드만으로 기호를 변경하고 가져올 수 있습니다.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Aspose.Tasks for Java를 사용하여 mpp 통화 기호 추출
og_description: Aspose.Tasks for Java를 사용하여 mpp 통화 기호를 추출하고 프로젝트 속성을 업데이트하는 방법을 배웁니다.
  빠르고 신뢰할 수 있으며 프로덕션에 바로 사용할 수 있습니다.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Aspose.Tasks Java를 사용하여 mpp 통화 기호를 추출하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Aspose.Tasks Java를 사용하여 mpp 통화 기호를 추출하는 방법
url: /ko/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 mpp에서 통화 기호 추출

## 소개
이 튜토리얼에서는 **java project properties**를 사용하는 방법—특히 Microsoft Project (MPP) 파일에서 **extract currency symbol mpp**를 추출하고 Aspose.Tasks 라이브러리를 사용하여 **change currency symbol java** 또는 **retrieve currency symbol java**를 수행하는 방법을 배웁니다. 재무 보고 도구를 구축하거나, Project 데이터를 ERP 시스템에 통합하거나, UI에 올바른 통화 기호를 표시해야 할 때, 이 작지만 필수적인 작업을 마스터하면 Java 애플리케이션이 보다 견고하고 사용자 친화적으로 됩니다.

## 빠른 답변
- **What does “extract currency symbol mpp” mean?** 이는 MPP(Microsoft Project) 파일에 저장된 통화 기호를 읽는 것을 의미합니다.  
- **Which library handles this?** Aspose.Tasks for Java은 이 작업을 위한 간단한 API를 제공합니다.  
- **Do I need a license?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **How long does it take?** 아래 코드를 사용하면 1분 이내에 기호를 얻을 수 있습니다.  
- **Can I also change the symbol?** 예 – 동일한 `Prj.CURRENCY_SYMBOL` 속성을 사용하여 새 값을 설정할 수 있습니다.

## “extract currency symbol mpp”란 무엇인가요?
MPP 파일에서 통화 기호를 추출한다는 것은 Microsoft Project가 파일 헤더에 저장하는 단일 문자 문자열을 읽어 프로젝트의 통화 단위를 나타내는 것을 의미합니다. 이 작업을 통해 값을 하드코딩하지 않고도 자체 애플리케이션에서 올바른 기호(예: $, €, £)를 표시할 수 있습니다.

## java 프로젝트 속성에서 통화 기호를 업데이트하는 이유는 무엇인가요?
통화 기호를 업데이트하면 보고서, 청구서 및 대시보드를 실시간으로 현지화할 수 있습니다. 여러 지역에서 프로젝트를 운영하는 기업은 한 번의 단계로 기호를 전환할 수 있어 전체 프로젝트 파일을 복제할 필요가 없습니다. Aspose.Tasks는 메모리 내에서 속성을 수정하고 파일을 다시 저장할 수 있으며, 최대 2,000개의 작업을 포함하는 프로젝트도 눈에 띄는 성능 저하 없이 지원합니다.

## 전제 조건
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. 코드에서 참조할 수 있는 폴더에 유효한 **project.mpp** 파일을 배치합니다.

## 패키지 가져오기
먼저, Project 파일 작업에 필요한 클래스를 가져옵니다.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 1단계: 데이터 디렉터리 정의
애플리케이션에 *.mpp* 파일이 위치한 경로를 알려줍니다.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `System.getProperty("user.dir")`를 사용하여 모든 머신에서 작동하는 절대 경로를 구축하십시오.

## 2단계: MS Project 파일 로드
`Project`는 Aspose.Tasks의 최상위 객체로, 메모리 내에서 단일 Microsoft Project 파일을 나타냅니다. 이 객체를 생성하면 Microsoft Project를 설치하지 않아도 파일 구조가 로드됩니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 3단계: 통화 기호 가져오기(및 선택적으로 변경)
`Prj.CURRENCY_SYMBOL`은 통화 기호를 저장하는 속성 키입니다. 이를 읽으면 현재 기호가 반환되고, 새 문자열을 할당하면 프로젝트의 통화 정의가 업데이트됩니다.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` 호출은 기호(예: `$`)를 콘솔에 출력하여 추출이 성공했음을 확인합니다.

## 일반적인 문제 및 해결 방법
| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | 잘못된 파일 경로 또는 파일을 찾을 수 없음 | `dataDir` 및 파일 이름을 확인하고, 디버그를 위해 `new File(dataDir).exists()`를 사용하십시오. |
| Unexpected symbol (e.g., `?`) | 프로젝트가 비표준 로케일로 생성됨 | 소스 MPP 파일이 실제로 통화 기호를 정의하고 있는지 확인하십시오; 위와 같이 프로그래밍 방식으로 설정할 수 있습니다. |
| License error | 유효한 라이선스 파일 없이 체험판을 사용함 | `Project` 객체를 생성하기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 라이선스를 로드하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용하여 통화 기호 외에 다른 프로젝트 속성을 조작할 수 있나요?**  
A: 예, Aspose.Tasks를 사용하면 작업, 리소스, 할당, 캘린더 및 기타 많은 프로젝트 속성을 편집할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: 물론입니다. Project 98부터 최신 버전까지 MPP, MPT, XML 형식을 지원합니다.

**Q: Aspose.Tasks가 개발자를 위한 문서와 지원을 제공하나요?**  
A: 포괄적인 API 문서, 코드 예제, 전용 지원 포럼이 Aspose.Tasks 웹사이트에서 제공됩니다.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 예 – 완전한 기능을 갖춘 무료 체험판을 [Aspose website](https://purchase.aspose.com/buy)에서 다운로드할 수 있습니다.

**Q: Aspose.Tasks의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 평가용으로 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 제공받을 수 있습니다.

---

**마지막 업데이트:** 2026-09-20  
**테스트 환경:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**작성자:** Aspose

## 관련 튜토리얼

- [Project Properties Java – Aspose.Tasks로 메타데이터 읽기](/tasks/java/project-properties/)
- [Aspose.Tasks로 MS Project에서 통화 가져오는 방법](/tasks/java/currency/currency-codes/)
- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}