---
date: 2026-02-10
description: Java용 Aspose.Tasks를 사용하여 MS Project 파일에서 통화 코드를 가져오는 방법을 배우세요 – Java
  개발자가 필요로 하는 통화 코드를 빠르게 얻는 방법.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project에서 통화 가져오는 방법
url: /ko/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks를 사용하여 MS Project에서 통화 가져오기

## 소개
환영합니다! 이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 MS Project 파일에서 **how to retrieve currency** 코드를 가져오는 방법을 알아봅니다. 다중 통화 재무 보고서를 생성하거나, 다양한 지역의 프로젝트를 통합하거나, 하위 처리에 필요한 정확한 통화 기호가 필요할 때, 이 가이드는 환경 설정부터 프로그래밍 방식으로 통화 코드를 추출하는 단계까지 모두 안내합니다. 끝까지 읽으면 MS Project 파일을 읽고 **get currency code java** 호출을 사용하여 ISO 통화 식별자를 얻는 데 익숙해질 것입니다.

## 빠른 답변
- **What does the API do?** API는 MS Project 파일을 읽고 통화 코드와 같은 속성을 노출합니다.  
- **Which language is used?** 사용되는 언어는 무엇인가요? Java, Aspose.Tasks for Java 라이브러리를 통해.  
- **Do I need a license?** 개발에는 무료 체험판을 사용할 수 있으며, 프로덕션에는 상용 라이선스가 필요합니다.  
- **Can I retrieve the code in one line?** 예—`prj.get(Prj.CURRENCY_CODE)`는 통화 코드 문자열을 반환합니다.  
- **Is it compatible with all Project versions?** Aspose.Tasks는 오래된 (MPP) 및 최신 (XML, XER) 형식을 모두 지원합니다.

## **read ms project file**란?
MS Project 파일을 읽는다는 것은 *.mpp* (또는 기타 지원되는) 프로젝트 문서를 프로그래밍 방식으로 열고, 작업, 리소스, 캘린더 및 재무 설정과 같은 데이터 구조에 접근하는 것을 의미하며, Microsoft Project를 직접 조작할 필요가 없습니다.

## Aspose.Tasks를 사용하여 **read msproject** 파일을 읽는 이유
- **Full format support** – Project 98부터 최신 Office 릴리스까지의 파일을 지원합니다.  
- **No COM or Office installation needed** – 순수 Java이며 서버 측 자동화에 적합합니다.  
- **Rich API** – `Prj.CURRENCY_CODE`와 같은 속성에 직접 접근할 수 있어 **how to retrieve currency** 정보를 즉시 얻을 수 있습니다.  
- **Performance** – 가벼운 파싱으로 다수의 프로젝트를 배치 처리하기에 이상적입니다.

## 사전 요구 사항
코드에 들어가기 전에 다음 항목을 준비하십시오:

### Java Development Kit (JDK) 설치
머신에 최신 JDK가 설치되어 있는지 확인하십시오. 최신 JDK 버전은 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드하고 설치할 수 있습니다.

### Aspose.Tasks for Java 라이브러리
Aspose.Tasks for Java 라이브러리를 다운로드하고 설정하십시오. 자세한 문서와 최신 바이너리는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## 패키지 가져오기
To get started, let's import the necessary packages in your Java project:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 단계별 가이드

### Step 1: 데이터 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의하십시오. 경로를 환경에 맞게 조정하세요.
```java
String dataDir = "Your Data Directory";
```

### Step 2: 프로젝트 파일 로드
`Project` 인스턴스를 생성하여 MS Project 파일을 로드합니다. 여기서 **read msproject** 데이터를 메모리로 읽어들입니다.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: 통화 코드 가져오기
프로젝트가 로드되었으므로, 단일 호출로 **how to retrieve currency** 정보를 가져올 수 있습니다. 이는 **get currency code java** 사용 예시입니다.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
출력은 프로젝트에 설정된 세 글자 ISO 통화 코드(`USD`, `EUR`, `GBP` 등)입니다.

### Step 4: Java에서 통화 코드 가져오기 (추가 컨텍스트)
If you need to store the value for later use, simply assign it to a variable:
*추가 코드 블록은 필요하지 않습니다* – `prj.get(Prj.CURRENCY_CODE)`가 반환하는 문자열을 그대로 유지하고, 이를 재무 서비스, 보고 엔진 또는 UI 컴포넌트에 전달하면 됩니다.

### Step 5: (선택) 통화 코드 사용
You might want to apply the retrieved code elsewhere—such as formatting cost values in a custom report or passing it to a financial API. Typical scenarios include:
- **Report generation** – 비용 열 앞에 코드를 붙입니다 (`USD 1,200`).  
- **API integration** – 통화 식별자가 필요한 결제 게이트웨이에 ISO 코드를 전송합니다.  
- **Data consolidation** – 포트폴리오 분석을 위해 통화별로 여러 프로젝트를 그룹화합니다.

## 일반적인 문제 및 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | 프로젝트 파일에 통화가 정의되어 있지 않음(기본값은 비어 있음). | Microsoft Project에서 통화를 설정하거나 읽기 전에 `prj.set(Prj.CURRENCY_CODE, "USD");`를 사용해 지정하십시오. |
| **File not found** | `dataDir` 경로가 올바르지 않음. | 경로를 확인하고 파일 이름이 정확히 일치하는지(대소문자 구분 포함) 확인하십시오. |
| **Unsupported file version** | 매우 오래되었거나 손상된 *.mpp* 파일. | 최신 Aspose.Tasks 버전을 사용하거나 먼저 Microsoft Project에서 파일을 최신 형식으로 변환하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, API는 다중 레벨 작업 계층, 리소스 풀 및 사용자 정의 필드를 문제 없이 읽고 조작할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: Absolutely. It supports MPP, XML, XER, and other formats across many Microsoft Project releases.

**Q: Aspose.Tasks가 문서와 지원을 제공하나요?**  
A: Comprehensive documentation, code examples, and dedicated support are available on the Aspose website.

**Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?**  
A: A free trial is offered so you can evaluate all features, including reading currency codes.

**Q: Aspose.Tasks의 임시 라이선스는 어디서 받을 수 있나요?**  
A: Temporary licenses can be obtained from the [website](https://purchase.aspose.com/temporary-license/) for short‑term evaluation.

**마지막 업데이트:** 2026-02-10  
**테스트 환경:** Aspose.Tasks for Java (latest version)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}