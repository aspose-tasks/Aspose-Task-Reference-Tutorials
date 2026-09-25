---
date: 2026-09-25
description: Aspose.Tasks for Java를 사용하여 MS Project 파일에서 통화 코드를 가져오는 방법을 배우세요 – Java
  개발자가 필요로 하는 통화 코드를 빠르게 얻는 방법.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Aspose.Tasks에서 통화 코드 관리
og_description: Aspose.Tasks를 사용하여 MS Project 파일에서 Java 통화 코드를 가져옵니다. 이 가이드는 프로젝트를
  읽고, ISO 통화 식별자를 추출하며, 이를 Java 애플리케이션에 적용하는 방법을 보여줍니다.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: MS Project에서 Java 통화 코드 가져오기
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Aspose.Tasks를 사용하여 MS Project에서 Java 통화 코드 가져오기
url: /ko/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project에서 Aspose.Tasks를 사용하여 Java로 통화 코드 가져오기

## 소개
이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 MS Project 파일에서 **how to retrieve currency code java** 를 배우게 됩니다. 다중 통화 재무 보고서를 생성하거나, 다양한 지역의 프로젝트를 통합하거나, 단순히 하위 시스템에 올바른 통화 기호를 표시해야 할 경우, 아래 단계는 환경 설정부터 ISO 통화 식별자를 반환하는 한 줄 호출까지 안내합니다. 가이드를 마치면 지원되는 모든 Project 파일 형식을 로드하고 `USD`, `EUR`, `GBP`와 같은 세 글자 통화 코드를 추출하는 데 익숙해질 것입니다.

## 빠른 답변
- **API는 무엇을 하나요?** MS Project 파일을 읽고 통화 코드와 같은 속성을 노출합니다.  
- **사용 언어는 무엇인가요?** Java, Aspose.Tasks for Java 라이브러리를 통해.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **한 줄로 코드를 가져올 수 있나요?** 예—`prj.get(Prj.CURRENCY_CODE)`는 통화 코드 문자열을 즉시 반환합니다.  
- **모든 Project 버전과 호환되나요?** Aspose.Tasks는 레거시 MPP, XML, XER 파일을 포함해 20개 이상의 입력 형식을 지원합니다.

## MS Project 파일을 읽는 것이란?
MS Project 파일을 읽는다는 것은 프로그래밍 방식으로 *.mpp* 파일(또는 XML, XER 등 지원되는 다른 형식)을 열어 내부 데이터 구조에 접근하는 것을 의미합니다. 이러한 구조에는 작업, 리소스, 캘린더, 비용 테이블 및 재무 설정이 포함됩니다. 파일을 파싱함으로써 Microsoft Project를 실행하지 않고도 정보를 추출할 수 있어 자동 보고, 마이그레이션 및 통합 워크플로우를 가능하게 합니다.

## Aspose.Tasks를 사용하여 MS Project 파일을 읽는 이유는?
Aspose.Tasks는 COM 인터옵이나 로컬 Microsoft Project 설치가 필요 없는 순수 Java 솔루션을 제공합니다. 20개 이상의 파일 형식을 지원하며, 수천 개의 작업이 있는 프로젝트도 100 MB 미만의 메모리로 처리할 수 있고 풍부한 객체 모델을 제공합니다. `Prj.CURRENCY_CODE`와 같은 상수에 직접 접근하면 통화 정보를 즉시 그리고 안정적으로 가져올 수 있습니다.

## 사전 요구 사항
코드에 들어가기 전에 다음이 준비되어 있는지 확인하십시오:

### Java 개발 키트 (JDK) 설치
최근 JDK(11 이상)가 필요합니다. 공식 Oracle 사이트에서 다운로드하십시오: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java 라이브러리
최신 Aspose.Tasks for Java 바이너리를 받아 프로젝트의 클래스패스에 추가하십시오. 전체 문서와 다운로드 링크는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## 패키지 가져오기
`Project` 클래스와 `Prj` 상수는 `com.aspose.tasks` 네임스페이스에 있습니다. Java 소스 파일 상단에 다음과 같이 가져오세요:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의하십시오. 런타임이 프로젝트 파일을 찾을 수 있도록 경로를 환경에 맞게 조정하세요.
```java
String dataDir = "Your Data Directory";
```

### 단계 2: 프로젝트 파일 로드
`Project` 클래스는 메모리 내에서 단일 MS Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 인스턴스를 생성하면 파일을 읽고 쿼리할 수 있는 메모리 내 모델을 구축합니다.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### 단계 3: 통화 코드 가져오기
`Prj.CURRENCY_CODE` 상수는 ISO 통화 식별자를 저장하는 속성을 나타냅니다. `prj.get(Prj.CURRENCY_CODE)`를 호출하면 한 번에 세 글자 코드를 반환합니다.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
출력은 프로젝트가 사용하도록 설정된 세 글자 ISO 통화 코드(예: `USD`, `EUR`, `GBP`)가 됩니다.

### 단계 4: Java에서 통화 코드를 가져오는 방법 (추가 컨텍스트)
프로젝트를 로드하고 `prj.get(Prj.CURRENCY_CODE)`를 호출하여 결과를 `String`에 저장합니다. 그런 다음 이 값을 통화 식별자가 필요한 모든 금융 서비스, 보고 엔진 또는 UI 구성 요소에 전달할 수 있습니다.

### 단계 5: (선택) 통화 코드 사용
일반적인 하위 시나리오는 다음과 같습니다:
- **보고서 생성** – 비용 열 앞에 코드를 붙입니다(`USD 1,200`).  
- **API 통합** – 통화 매개변수를 요구하는 결제 게이트웨이에 ISO 코드를 전송합니다.  
- **데이터 통합** – 포트폴리오 수준 분석을 위해 통화별로 여러 프로젝트를 그룹화합니다.

## 일반적인 문제 및 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null 출력** | 프로젝트 파일에 통화가 정의되어 있지 않음(기본값은 비어 있음). | 읽기 전에 Microsoft Project에서 통화를 설정하거나 `prj.set(Prj.CURRENCY_CODE, "USD");`를 사용해 지정하십시오. |
| **파일을 찾을 수 없음** | `dataDir` 경로가 올바르지 않음. | 경로를 확인하고 파일 이름이 정확히 일치하는지(대소문자 구분 포함) 확인하십시오. |
| **지원되지 않는 파일 버전** | 매우 오래되었거나 손상된 *.mpp* 파일. | 최신 Aspose.Tasks 버전으로 업그레이드하거나 먼저 Microsoft Project에서 파일을 최신 형식으로 변환하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, API는 다중 레벨 작업 계층, 리소스 풀, 사용자 정의 필드 및 캘린더를 제한 없이 읽습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: 전적으로 호환됩니다. Project 98부터 최신 Office 릴리스까지 MPP, XML, XER 및 기타 형식을 지원합니다.

**Q: Aspose.Tasks가 문서와 지원을 제공하나요?**  
A: 포괄적인 API 레퍼런스, 코드 예제, 전용 기술 지원이 Aspose 웹사이트에서 제공됩니다.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 모든 기능(통화 코드 추출 포함)을 평가할 수 있도록 무료 체험판을 제공합니다.

**Q: 평가용 임시 라이선스는 어디서 얻을 수 있나요?**  
A: 임시 라이선스는 [website](https://purchase.aspose.com/temporary-license/)에서 제공됩니다.

---

**마지막 업데이트:** 2026-09-25  
**테스트 환경:** Aspose.Tasks for Java (latest version)  
**작성자:** Aspose

## 관련 튜토리얼

- [Project Properties Java – Aspose.Tasks로 메타데이터 읽기](/tasks/java/project-properties/)
- [Aspose.Tasks for Java로 Microsoft Project에서 프로젝트 정보 읽는 방법](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks에서 MS Project 개요 코드 가져오기](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}