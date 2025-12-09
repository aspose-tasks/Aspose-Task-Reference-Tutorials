---
date: 2025-12-09
description: Aspose.Tasks for Java를 사용하여 MS Project 파일을 읽고 통화 코드를 효율적으로 관리하는 방법을 배우세요.
  프로젝트 관리 작업을 손쉽게 간소화하세요.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project 파일을 읽고 통화 코드를 관리하는 방법
url: /ko/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 파일을 읽고 Aspose.Tasks로 통화 코드를 관리하는 방법

## 소개
환영합니다! 이 튜토리얼에서는 **MS Project 파일을 읽는 방법** 데이터를 발견하고, 특히 Aspose.Tasks Java API를 사용하여 **통화 코드를 관리하는 방법**을 배웁니다. 보고서를 생성하거나, 다중 통화 프로젝트를 통합하거나, 올바른 재무 기호가 표시되도록 해야 할 때, 이 가이드는 환경 설정부터 프로그래밍 방식으로 통화 코드를 검색하는 단계까지 모든 과정을 안내합니다. 끝까지 진행하면 MS Project 파일을 읽고 필요한 통화 정보를 추출하는 데 익숙해질 것입니다.

## 빠른 답변
- **API는 무엇을 하나요?** MS Project 파일을 읽고 통화 코드와 같은 속성을 노출합니다.  
- **사용 언어는 무엇인가요?** Java, Aspose.Tasks for Java 라이브러리를 통해 사용합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **한 줄로 코드를 가져올 수 있나요?** 예—`prj.get(Prj.CURRENCY_CODE)`는 통화 코드 문자열을 반환합니다.  
- **모든 Project 버전과 호환되나요?** Aspose.Tasks는 오래된 (MPP) 형식과 최신 (XML, XER) 형식을 모두 지원합니다.

## **read ms project file**이란?
MS Project 파일을 읽는다는 것은 *.mpp* (또는 지원되는 다른) 프로젝트 문서를 프로그래밍 방식으로 열어 작업, 리소스, 캘린더 및 재무 설정과 같은 데이터 구조에 접근하는 것을 의미하며, Microsoft Project를 직접 사용할 필요가 없습니다.

## Aspose.Tasks로 **read msproject** 파일을 사용하는 이유
- **전체 형식 지원** – Project 98부터 최신 Office 릴리스까지 모든 파일에서 작동합니다.  
- **COM이나 Office 설치 불필요** – 순수 Java 기반으로 서버‑사이드 자동화에 최적화되었습니다.  
- **강력한 API** – `Prj.CURRENCY_CODE`와 같은 속성에 직접 접근할 수 있어 **통화 정보를 즉시 검색**할 수 있습니다.  
- **성능** – 가벼운 파싱으로 다수의 프로젝트를 배치 처리하기에 이상적입니다.

## 사전 요구 사항
코드 작성을 시작하기 전에 아래 항목을 확인하십시오:

### Java Development Kit (JDK) 설치
최근 JDK가 머신에 설치되어 있어야 합니다. 최신 JDK 버전은 [여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드하고 설치할 수 있습니다.

### Aspose.Tasks for Java 라이브러리
Aspose.Tasks for Java 라이브러리를 다운로드하고 설정하십시오. 자세한 문서와 최신 바이너리는 [여기](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의합니다. 환경에 맞게 경로를 조정하십시오.
```java
String dataDir = "Your Data Directory";
```

### 단계 2: 프로젝트 파일 로드
MS Project 파일을 로드하여 `Project` 인스턴스를 생성합니다. 여기서 **read msproject** 데이터를 메모리로 읽어들이는 시점입니다.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### 단계 3: 통화 코드 검색
프로젝트가 로드되었으므로 **how to retrieve currency** 정보를 한 번의 호출로 얻을 수 있습니다. 이는 **get currency code java** 사용 예시입니다.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
출력은 프로젝트에 설정된 세 글자 ISO 통화 코드(`USD`, `EUR`, `GBP` 등)입니다.

### 단계 4: (선택) 통화 코드 활용
검색한 코드를 다른 곳에 적용하고 싶을 수 있습니다—예를 들어 사용자 지정 보고서에서 비용 값을 포맷하거나 재무 API에 전달하는 경우입니다. 간단한 예시는 다음과 같습니다(추가 코드 블록은 필요 없음):
- 변수를 사용해 코드를 저장합니다.  
- 금액 문자열을 구성할 때 사용합니다.  
- 통화 식별자가 필요한 하위 서비스에 전달합니다.

## 일반적인 문제와 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | 프로젝트 파일에 통화가 정의되어 있지 않음(기본값은 비어 있음). | Microsoft Project에서 통화를 설정하거나 `prj.set(Prj.CURRENCY_CODE, "USD");`를 통해 읽기 전에 지정합니다. |
| **File not found** | `dataDir` 경로가 잘못됨. | 경로를 확인하고 파일 이름이 정확히 일치하는지(대소문자 포함) 확인합니다. |
| **Unsupported file version** | 매우 오래되었거나 손상된 *.mpp* 파일. | 최신 Aspose.Tasks 버전을 사용하거나 먼저 Microsoft Project에서 파일을 최신 형식으로 변환합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, API는 다중 레벨 작업 계층, 리소스 풀 및 사용자 정의 필드를 문제 없이 읽고 조작할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: 물론입니다. MPP, XML, XER 등 여러 Microsoft Project 릴리스에서 사용되는 형식을 모두 지원합니다.

**Q: Aspose.Tasks가 문서와 지원을 제공하나요?**  
A: 포괄적인 문서, 코드 예제 및 전용 지원이 Aspose 웹사이트에서 제공됩니다.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 예, 모든 기능(통화 코드 읽기 포함)을 평가할 수 있는 무료 체험판이 제공됩니다.

**Q: Aspose.Tasks 임시 라이선스는 어디서 받을 수 있나요?**  
A: 단기 평가용 임시 라이선스는 [website](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-09  
**테스트 환경:** Aspose.Tasks for Java (최신 버전)  
**작성자:** Aspose