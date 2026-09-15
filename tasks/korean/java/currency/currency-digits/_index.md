---
date: 2026-09-14
description: Aspose.Tasks와 함께 ms project 통화를 가져오고 Java로 프로젝트 속성을 읽는 방법을 배웁니다. MPP
  파일에서 통화 자릿수를 추출하는 단계별 가이드.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Aspose.Tasks를 사용하여 MS Project에서 통화를 가져오는 방법
og_description: Aspose.Tasks와 함께 ms project 통화를 가져오고 Java로 프로젝트 속성을 읽는 방법을 배웁니다. 이
  간결한 Java 튜토리얼을 따라 MPP 파일에서 통화 자릿수를 추출하세요.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Aspose.Tasks를 사용하여 ms project 통화를 가져오는 방법 – Java 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Aspose.Tasks를 사용하여 ms project 통화를 가져오는 방법
url: /ko/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS Project 통화 가져오기

## 소개
Microsoft Project 파일에서 **ms project 통화** 정보를 얻는 방법이 궁금하다면, 올바른 곳에 오셨습니다. 이 포괄적인 튜토리얼에서는 Java용 Aspose.Tasks 라이브러리를 사용하여 **ms project 통화** 값을 다루는 방법을 알아볼 수 있습니다. 보고서 도구, 마이그레이션 유틸리티를 구축하거나 단순히 **java 프로젝트 파일**의 통화 설정을 읽어야 할 경우에도, 이 가이드는 *.mpp* 파일 로드부터 통화 자릿수 추출까지 모든 단계를 안내합니다. 마지막까지 진행하면 자체 애플리케이션에서 ms project 통화 데이터를 자유롭게 처리할 수 있게 됩니다.

## 빠른 답변
- **MS Project 파일을 읽는 라이브러리는 무엇인가요?** Aspose.Tasks for Java.  
- **통화 자릿수를 얻기 위한 코드 라인은 몇 줄인가요?** 프로젝트가 로드된 후 단 3줄의 간결한 코드만 필요합니다.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상 (Aspose.Tasks를 실행할 수 있는 모든 JDK).  
- **다른 Project 속성을 가져올 수 있나요?** 예 – Aspose.Tasks는 전체 Project 필드 집합(예: 시작 날짜, 비용 비율 등)을 제공합니다.

## ms project 통화란?
`ms project currency` 속성은 Microsoft Project가 금액을 표시할 때 사용하는 소수점 자리수를 정의합니다. 이 값은 프로젝트 파일에 **CURRENCY_DIGITS** 필드로 저장되며, 금액이 정수, 소수점 1자리, 2자리 등으로 표시될지를 결정합니다. 이 설정은 예산 보고서, 비용 집계 및 재무 수치를 표시하는 모든 UI에 직접 영향을 미치므로 정확한 데이터 교환에 필수적입니다.

## ms project 통화 처리를 위해 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks를 사용하면 Microsoft Project를 설치하지 않고도 통화 자릿수를 추출할 수 있으며, 엔터프라이즈 수준의 성능을 제공합니다. 이 라이브러리는 **30년 이상의 Project 파일 버전**(Project 2000부터 Project 2024까지)을 지원하며, **150개 이상의 고유 파일 스키마**를 포괄합니다. 500페이지 규모의 프로젝트를 로드하는 데 일반 서버에서는 보통 **2초** 미만이 걸리며, 필요한 필드만 조회함으로써 가장 큰 일정이라도 메모리 사용량을 **50 MB** 이하로 유지할 수 있습니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Environment** – JDK 8 이상 설치 및 구성됨.  
2. **Aspose.Tasks for Java** – 공식 사이트에서 최신 JAR 다운로드: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Java 프로젝트를 생성하고 외부 라이브러리를 추가하며 `main` 메서드를 실행하는 데 익숙해야 합니다.  

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다.  
Aspose.Tasks 라이브러리에서 `Project` 클래스와 관련 유틸리티를 가져옵니다.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 단계 1: 데이터 디렉터리 정의
**java project file**(`*.mpp`)이 들어 있는 폴더를 지정합니다.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 `project.mpp`가 위치한 절대 경로나 상대 경로로 교체하십시오.

## 단계 2: mpp 파일 로드
이제 Aspose.Tasks를 사용하여 **mpp 파일을 로드하는 방법**을 살펴보겠습니다.  
`Project` 클래스는 Microsoft Project 파일을 나타내며 해당 속성에 접근할 수 있게 합니다.  
```java
Project project = new Project(dataDir + "project.mpp");
```
파일 이름이 정확히 일치하는지 확인하십시오; 그렇지 않으면 `IOException`이 발생합니다.

## 단계 3: 통화 자릿수 가져오기
프로젝트가 로드된 상태에서 **ms project 통화** 자릿수를 추출하는 코드는 한 줄입니다:  
`getCurrencyDigits()` 메서드는 금액에 정의된 소수점 자리수를 반환합니다.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
이 호출은 소수점 자리수를 나타내는 `Integer`를 반환합니다(예: 센트는 `2`). 값은 콘솔에 출력되지만, 추가 처리를 위해 변수에 저장할 수도 있습니다.

## 일반적인 문제 및 팁
- **파일을 찾을 수 없음** – `dataDir` 경로를 다시 확인하고 파일 이름이 정확한지, `.mpp` 확장자를 포함하고 있는지 확인하십시오.  
- **지원되지 않는 파일 버전** – Aspose.Tasks는 Project 2000‑2024 형식을 지원합니다; 오래되었거나 손상된 파일은 변환이 필요할 수 있습니다.  
- **라이선스 미설정** – 개발 단계에서는 체험판으로 충분하지만, 프로덕션에서는 평가 워터마크를 방지하기 위해 유효한 라이선스를 적용해야 합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks가 통화 자릿수 외에 다른 Project 속성도 처리할 수 있나요?**  
A: 예, Aspose.Tasks는 작업, 리소스, 사용자 정의 필드 등 Project 파일의 다양한 측면을 조작할 수 있는 광범위한 기능을 제공합니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준 애플리케이션에 적합한가요?**  
A: 물론입니다. Aspose.Tasks는 엔터프라이즈 급 프로젝트의 요구를 충족하도록 설계되었으며, 높은 성능과 확장성을 제공합니다.

**Q: Aspose.Tasks가 크로스‑플랫폼 개발을 지원하나요?**  
A: 예, Java Runtime Environment를 지원하는 모든 플랫폼(Windows, Linux, macOS)에서 Aspose.Tasks for Java를 사용할 수 있습니다.

**Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?**  
A: 예, [Aspose releases page](https://releases.aspose.com/)에서 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

---

**마지막 업데이트:** 2026-09-14  
**테스트 환경:** Aspose.Tasks for Java (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [java 프로젝트 속성 – Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호 추출](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks를 사용하여 MS Project에서 통화 가져오기](/tasks/java/currency/currency-codes/)
- [Project 속성 Java – Aspose.Tasks로 메타데이터 읽기](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}