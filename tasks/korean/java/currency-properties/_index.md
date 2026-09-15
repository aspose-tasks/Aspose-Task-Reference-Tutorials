---
date: 2026-09-14
description: Java와 Aspose.Tasks를 사용하여 통화 형식을 변경하고 통화 속성을 읽는 방법을 배웁니다. 통화 코드를 추출하고
  통화 기호를 가져오며 MS Project 파일에서 프로젝트 통화를 업데이트합니다.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: 통화 형식 변경 방법
og_description: Java와 Aspose.Tasks를 사용하여 통화 형식을 변경하고 통화 속성을 읽는 방법을 배웁니다. 통화 코드를 추출하고
  프로젝트 통화를 업데이트하는 단계별 가이드.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Java와 Aspose.Tasks를 사용하여 통화 형식을 변경하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Java와 Aspose.Tasks를 사용하여 통화 형식을 변경하는 방법
url: /ko/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks와 Java에서 통화 속성 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks를 사용하는 Java 프로젝트에서 **통화 형식 변경** 및 통화 속성을 읽는 방법을 배웁니다. 정확한 재무 데이터는 다국적 팀에 필수적이며, 이러한 API를 마스터하면 ISO‑4217 코드를 추출하고, 통화 기호를 가져오며, 수동 스프레드시트 편집 없이 프로젝트의 통화 설정을 업데이트할 수 있습니다.

## 빠른 답변
- **“read currency”(통화 읽기)란 무엇인가요?** 프로젝트 파일에 저장된 통화 코드, 기호 및 숫자 형식 설정을 추출하는 것을 의미합니다.  
- **왜 통화 설정을 조정해야 하나요?** 비용 보고서를 지역 관례에 맞추고 변환 실수를 방지하기 위해서입니다.  
- **라이선스가 필요합니까?** 예 – 프로덕션에서는 유효한 Aspose.Tasks for Java 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Project 버전은 무엇인가요?** *.mpp* (Project 2007‑2024)와 *.xml* 형식 모두 완전히 지원되며, 20년 이상의 파일 버전을 포괄합니다.  
- **추가 설정이 필요합니까?** Aspose.Tasks for Java JAR를 클래스패스에 추가하고 관련 클래스를 임포트하기만 하면 됩니다.

## Aspose.Tasks 프로젝트에서 Java로 통화 속성 읽기
프로젝트 관리의 역동적인 영역에서 통화 세부 정보를 추출하는 것은 정확한 비용 분석에 필수적입니다. 우리의 전용 가이드 **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)**는 프로젝트 파일을 여는 것부터 통화 코드, 기호 및 형식을 가져오는 단계까지 모든 과정을 안내합니다. 튜토리얼을 따라하면 다음을 수행할 수 있습니다:

* 프로젝트 전체에서 사용되는 통화 코드(예: USD, EUR)를 가져오기.  
* 통화 기호와 숫자 형식 설정에 접근하기.  
* 이 정보를 사용해 현지화된 비용 보고서를 생성하거나 재무 대시보드에 제공하기.

통화를 읽는 방법을 이해하면 프로젝트 예산을 감사하고, 지역 간 비용을 비교하며, 회계 기준을 준수할 수 있습니다.

## Aspose.Tasks를 사용한 Java에서 통화 코드 추출 방법
`Project.getCurrencyCode()` 메서드는 프로젝트의 통화 단위에 대한 세 글자 ISO‑4217 식별자를 반환합니다.

**직접 답변:** `project.getCurrencyCode()`를 호출하면 **USD** 또는 **EUR**와 같은 통화 코드를 얻을 수 있으며, 이 값을 저장, 로그 기록하거나 외부 금융 서비스에 전달하여 변환에 사용할 수 있습니다. 이 한 줄 호출은 모든 지원되는 Project 버전에서 작동하는 신뢰할 수 있는 표준 기반 식별자를 제공합니다.

이 메서드는 표준화된 코드를 기대하는 ERP 시스템과 프로젝트 데이터를 신속하게 동기화하는 방법을 제공합니다.

## Aspose.Tasks를 사용한 Java에서 통화 형식 조정 방법
통화 값의 시각적 표현을 변경하려면 세 가지 간단한 속성을 사용합니다.

`project.setCurrencySymbol(String)` sets the currency symbol displayed for monetary values.  
`project.setCurrencyDecimalSeparator(char)` defines the character used to separate the integer part from the fractional part.  
`project.setCurrencyThousandsSeparator(char)` defines the character used to separate groups of thousands.

**직접 답변:** `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")`, `project.setCurrencyThousandsSeparator(".")`를 사용하여 각각 기호, 소수 구분자, 천 단위 구분자를 정의하면 한 번에 통화 형식을 완전히 변경할 수 있습니다. 이러한 설정을 조정하면 모든 이해관계자가 익숙한 스타일로 숫자를 보게 되어 오해를 줄일 수 있습니다.

* `project.setCurrencySymbol("€")` – 시각적 기호를 설정합니다.  
* `project.setCurrencyDecimalSeparator(",")` – 소수 구분자를 정의합니다.  
* `project.setCurrencyThousandsSeparator(".")` – 천 단위 구분자를 정의합니다.  

## Aspose.Tasks 프로젝트에서 통화 속성 설정 방법
프로젝트가 새로운 시장으로 이동하거나 클라이언트가 다른 통화 형식을 요청할 때, 프로그래밍 방식으로 통화를 업데이트해야 합니다.

`project.setCurrencyCode(String)`은 프로젝트의 ISO‑4217 통화 코드를 정의합니다.

**직접 답변:** `project.setCurrencyCode("GBP")`와 `project.setCurrencySymbol("£")` 및 적절한 구분자를 함께 호출한 뒤 프로젝트를 저장하면, 라이브러리는 기존 비용 데이터를 보존하면서 모든 표시 설정을 업데이트합니다. 이 방법을 통해 일정의 재무 표현을 완전히 제어할 수 있습니다.

우리의 단계별 가이드 **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)**는 다음과 같은 방법을 설명합니다:

* 전체 프로젝트에 대한 새로운 통화 코드와 기호를 정의합니다.  
* 숫자 형식(소수 자리, 천 단위 구분자)을 현지 관례에 맞게 조정합니다.  
* 기존 데이터를 잃지 않고 업데이트된 프로젝트 파일을 저장합니다.

통화 설정 방법을 마스터하면 USD, GBP, JPY 또는 지원되는 모든 통화 사이를 즉시 전환할 수 있습니다.

## Aspose.Tasks에서 통화 처리 마스터가 왜 중요한가요?
적절한 통화 처리는 비용이 많이 드는 오해를 없애고 글로벌 협업을 효율화합니다.

**직접 답변:** 통화 처리를 마스터하면 각 팀의 고유 형식으로 비용을 표시하고, 정확한 보고를 보장하며, 지역 회계 기준을 준수하고, 자동화된 재무 워크플로를 가능하게 하여 프로젝트당 수시간의 수동 재포맷 작업을 절감할 수 있습니다.

* **글로벌 협업:** 다양한 국가의 팀이 자체 통화 형식으로 비용을 볼 수 있습니다.  
* **정확한 보고:** 예산에 영향을 줄 수 있는 반올림 또는 변환 실수를 방지합니다.  
* **준수:** 지역 회계 기준 및 클라이언트 사양에 맞춥니다.  
* **자동화:** 프로젝트 생성 시 프로그래밍 방식으로 통화 설정을 적용하여 수동 편집을 줄입니다.

## 실제 사용 사례
* **다국적 프로젝트:** 유럽과 북미에 현장을 보유한 건설 회사가 EUR와 USD 두 통화로 예산을 제시해야 합니다.  
* **재무 감사:** 감사자는 모든 비용 항목에 대한 통화 컨텍스트를 명확히 볼 필요가 있습니다.  
* **동적 가격 모델:** SaaS 제공업체가 고객의 현지 통화에 따라 구독 비용을 조정합니다.

## 일반적인 함정 및 팁
* **함정:** 코드를 변경한 후 통화 기호 업데이트를 잊는 경우.  
  **팁:** 코드와 기호를 항상 함께 설정하여 표시 불일치를 방지하세요.  
* **함정:** 코드를 실행하는 머신의 기본 로케일에 의존하는 경우.  
  **팁:** Aspose.Tasks 코드에서 원하는 통화 형식을 명시적으로 지정하여 환경 간 일관성을 보장하세요.  

## 통화 속성 튜토리얼
### [Aspose.Tasks 프로젝트에서 통화 속성 읽기](./read-properties/)
Aspose.Tasks for Java를 사용하여 MS Project 파일에서 통화 정보를 추출하는 방법을 배웁니다. 단계별 가이드가 제공됩니다.

### [Aspose.Tasks 프로젝트에서 통화 속성 설정](./set-properties/)
Java를 사용하여 Aspose.Tasks 프로젝트에서 통화 속성을 설정하는 방법을 배웁니다. Microsoft Project 파일을 손쉽게 조작할 수 있습니다.

## 자주 묻는 질문

**Q: 프로젝트를 이미 저장한 후에도 통화를 변경할 수 있나요?**  
A: 예. `Project.setCurrencyCode()` 및 관련 메서드를 사용한 뒤 프로젝트를 다시 저장하면 됩니다.

**Q: 통화를 변경하면 기존 비용 값에 영향을 줍니까?**  
A: 숫자 값은 그대로 유지되고, 표시 형식(기호, 소수 구분자)만 업데이트됩니다. 통화 간 변환이 필요하면 비용을 다시 계산해야 합니다.

**Q: 정의할 수 있는 통화 수에 제한이 있나요?**  
A: Aspose.Tasks는 모든 ISO‑4217 통화 코드를 지원하므로 사실상 제한이 없습니다.

**Q: 지원되지 않는 통화 코드가 있는 프로젝트를 열면 어떻게 되나요?**  
A: 라이브러리는 기본 통화(USD)로 대체하고 경고를 기록합니다; 원하는 통화를 수동으로 설정하면 이를 덮어쓸 수 있습니다.

**Q: Project XML 파일에서 통화 속성을 읽고 쓸 수 있나요?**  
A: 물론 가능합니다. 동일한 API가 *.mpp*와 *.xml* 형식 모두에서 작동합니다.

---

**마지막 업데이트:** 2026-09-14  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [java 프로젝트 속성 – Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호 추출](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks를 사용하여 MS Project에서 통화 가져오는 방법](/tasks/java/currency/currency-codes/)
- [프로젝트 속성 Java – Aspose.Tasks로 메타데이터 읽기](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}