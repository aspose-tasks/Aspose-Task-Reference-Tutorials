---
date: 2026-09-09
description: Aspose.Tasks Java 프로젝트에서 currency symbol을 변경하고, currency codes를 설정하며,
  기호를 조정하고, Microsoft Project 파일에 대한 custom formats를 적용하는 방법을 배웁니다.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Aspose.Tasks 프로젝트에서 Currency Properties 설정
og_description: Java를 사용하여 Aspose.Tasks에서 currency symbol을 변경하는 방법. 단계별 지침, 전제 조건
  및 프로젝트 비용 포맷을 맞춤화하는 팁을 확인하세요.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Aspose.Tasks에서 currency symbol을 변경하는 방법 – Java guide
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Aspose.Tasks 프로젝트에서 currency symbol을 변경하는 방법 – Java guide
url: /ko/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 통화 기호 변경 방법 – Java 가이드

## 소개
이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 Microsoft Project 파일의 **통화 기호 변경 방법**을 배웁니다. 해외 고객을 위한 보고서를 준비하거나, 여러 지역의 예산을 통합하거나, 단순히 회사의 회계 기준에 맞추고자 할 때, 통화 기호를 조정하면 모든 비용 관련 필드에 올바른 통화 기호가 표시됩니다. 이 가이드는 개발 환경 설정부터 새 프로젝트 파일 또는 기존 파일에 변경 사항을 저장하는 단계까지 모든 과정을 안내합니다.

## 빠른 답변
- **필요한 라이브러리는 무엇입니까?** Aspose.Tasks for Java.  
- **통화 기호를 변경할 수 있나요?** Yes – set `Prj.CURRENCY_SYMBOL` and choose `CurrencySymbolPositionType`.  
- **지원되는 파일 형식은 무엇입니까?** XML, MPP, and many others via `SaveFileFormat`.  
- **개발에 라이선스가 필요합니까?** A free trial works for testing; a license is required for production.  
- **구현에 얼마나 걸립니까?** About 5‑10 minutes for a basic setup.

## Java를 사용하여 Aspose.Tasks에서 통화 기호를 변경하는 방법
대상 프로젝트를 로드(또는 새로 생성)하고 원하는 통화 속성을 설정한 뒤 파일을 저장합니다. 전체 작업은 세 번의 API 호출로 구성됩니다: `Project` 객체를 생성하거나 로드하고, 통화 코드, 기호 및 위치를 지정한 다음 `project.save`를 호출합니다. 이 방법은 Microsoft Project를 설치하지 않아도 새 프로젝트와 기존 파일 모두에 적용할 수 있습니다.

## 통화 변경에 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 **30개 이상의 통화 관련 속성에 대한 전체 API 지원**을 제공하여 코드, 기호, 소수점 자리수 및 위치를 한 곳에서 정의할 수 있게 합니다. 이 라이브러리는 일반 서버 하드웨어에서 수백 페이지에 달하는 Project 파일을 1초 미만으로 처리하며, Windows, Linux, macOS에서 추가 종속성 없이 작동합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK) 8 이상** – API는 최소 JDK 8이 필요합니다.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일은 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받으세요.  
3. **IDE** – Eclipse, IntelliJ IDEA 또는 Java를 지원하는 편집기.  
4. **쓰기 가능한 폴더** – 생성된 프로젝트 파일이 저장될 위치.

## 패키지 가져오기
다음 클래스들은 프로젝트 속성, 파일 처리 및 통화 설정에 접근할 수 있게 합니다.

`Project` – 메모리 내에서 Microsoft Project 파일을 나타냅니다.  
`Prj` – 통화 필드를 포함한 모든 프로젝트 수준 속성에 대한 상수를 포함합니다.  
`CurrencySymbolPositionType` – 통화 기호의 가능한 위치(금액 앞 또는 뒤)를 열거합니다.

프로젝트를 조작하는 코드 앞에 이러한 import가 필요합니다.

## 단계별 가이드

### 1단계: 데이터 디렉터리 정의
소스 파일이 위치하고 출력이 기록될 폴더를 선택하십시오. 디렉터리가 존재하고 Java 프로세스에 쓰기 권한이 있는지 확인하세요.

### 2단계: 새 프로젝트 인스턴스 생성
`Project` 클래스는 메모리 내에서 단일 Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 인스턴스를 생성하면 구성을 위한 빈 프로젝트가 만들어집니다.

### 3단계: 통화 속성 설정
여기서 통화 코드, 소수점 자리수, 기호 자체 및 기호 위치를 설정합니다.

- **통화 코드** – `AUD` 또는 `USD`와 같은 3자리 ISO 4217 코드.  
- **소수점 자리수** – 대부분의 통화는 일반적으로 2자리.  
- **통화 기호** – 금액과 함께 표시되는 문자 또는 문자열, 예: `$` 또는 `€`.  
- **기호 위치** – `CurrencySymbolPositionType.Before`는 숫자 앞에 기호를 배치하고, `After`는 뒤에 배치합니다.

이 설정은 프로젝트의 모든 비용 관련 필드(리소스 요금, 작업 예산 등)에 영향을 줍니다.

> **Pro tip:** 기존 파일의 통화를 변경해야 하는 경우, 위 설정을 적용하기 전에 `new Project("file.mpp")`로 파일을 로드하십시오.

### 4단계: 업데이트된 프로젝트 저장
원하는 형식으로 프로젝트를 디스크에 다시 씁니다. XML 형식은 사람이 읽기 쉬우며, `SaveFileFormat.MPP`는 Microsoft Project와의 완전한 호환성을 유지합니다.

### 5단계: 성공 확인
작업이 오류 없이 완료되었음을 알 수 있도록 짧은 메시지나 로그 항목을 출력합니다. 이는 자동 파이프라인에서 특히 유용합니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **`project.save`에서 `NullPointerException`** | `dataDir`이(가) 유효한 경로가 아니거나 쓰기 권한이 없습니다. | 디렉터리가 존재하고 Java 프로세스에 쓰기 권한이 있는지 확인하십시오. |
| **통화 기호가 표시되지 않음** | 기호 위치가 로케일에 맞게 잘못 설정되었습니다. | 기호가 금액 앞에 와야 한다면 `CurrencySymbolPositionType.Before`를 사용하십시오. |
| **프로젝트 파일이 MS Project에서 열리지 않음** | 호환되지 않는 설정으로 오래된 형식에 저장했습니다. | 최근 MS Project 버전과 완전한 호환성을 위해 `SaveFileFormat.MPP`로 저장하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용하여 단일 프로젝트에서 여러 통화를 설정할 수 있나요?**  
A: 예, 프로젝트 수준 통화를 정의한 후 개별 리소스 또는 작업의 비용 필드를 수정하여 서로 다른 통화 설정을 할당할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. 이 라이브러리는 Project 2000부터 최신 버전까지의 MPP 파일은 물론 XML 및 기타 교환 형식을 지원합니다.

**Q: Aspose.Tasks가 사용자 정의 통화 형식을 지원하나요?**  
A: 예, 사용자 정의 기호, 소수점 자리수 및 위치를 정의하여 모든 지역 요구 사항을 충족할 수 있으며, 이러한 설정은 저장된 파일에 유지됩니다.

**Q: Aspose.Tasks를 다른 Java 프레임워크와 통합할 수 있나요?**  
A: 물론입니다. API가 순수 Java이므로 Spring, Hibernate, Maven, Gradle 및 기타 생태계와 원활하게 작동합니다.

**Q: 추가 도움이나 예제는 어디서 찾을 수 있나요?**  
A: 커뮤니티 지원을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하거나, 자세한 API 참조를 위해 공식 문서를 참고하십시오.

## 결론
이제 Java를 사용하여 Aspose.Tasks 프로젝트에서 **통화 기호를 변경하는 방법**과 통화 코드를 설정하고, 소수점 자리수를 조정하며, 사용자 정의 기호를 적용하는 방법을 알게 되었습니다. 이러한 기능을 통해 지역별 비용 보고서를 생성하고, 프로젝트 예산을 지역 회계 기준에 맞추며, 전 세계 팀 간에 Microsoft Project 파일을 일관되게 유지할 수 있습니다.

---

**마지막 업데이트:** 2026-09-09  
**테스트 대상:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## 관련 튜토리얼

- [java 프로젝트 속성 – Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호 추출](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks 프로젝트로 Java에서 통화 속성 읽기](/tasks/java/currency-properties/read-properties/)
- [Aspose.Tasks를 사용한 Java 통화 코드 관리](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}