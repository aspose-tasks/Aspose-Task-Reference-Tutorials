---
date: 2025-12-05
description: Aspose.Tasks for Java를 사용하여 MS Project 통화 자릿수를 효율적으로 처리하는 방법을 배웁니다. Java
  프로젝트 파일 처리와 MPP 파일 로드 방법을 단계별로 안내합니다.
language: ko
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project 통화 자릿수 처리
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 ms project 통화 자리수 처리

## 소개
이 포괄적인 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 **ms project 통화** 값을 다루는 방법을 알아봅니다. 보고서 도구를 만들든, 마이그레이션 유틸리티를 개발하든, 혹은 **java 프로젝트 파일**에서 통화 설정을 읽어야 하든, 이 가이드는 *.mpp* 파일을 로드하고 통화 자리수를 추출하는 모든 단계를 안내합니다. 마지막까지 읽으면 여러분의 애플리케이션에서 ms project 통화 데이터를 자신 있게 처리할 수 있게 됩니다.

## 빠른 답변
- **MS Project 파일을 읽는 라이브러리는?** Aspose.Tasks for Java.  
- **통화 자리수를 얻는 코드 라인은 몇 줄인가요?** 프로젝트를 로드한 뒤 단 3줄이면 충분합니다.  
- **개발용 라이선스가 필요한가요?** 테스트용 무료 체험판으로 가능하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상 (Aspose.Tasks가 실행되는 모든 JDK).  
- **다른 Project 속성도 가져올 수 있나요?** 네 – Aspose.Tasks는 시작일, 비용 비율 등 전체 Project 필드를 제공합니다.

## ms project 통화란?
`ms project 통화`는 Microsoft Project가 금액을 표시할 때 사용하는 소수점 자리수(정밀도)를 의미합니다. 이는 Project 파일에 **CURRENCY_DIGITS** 속성으로 저장되며, 금액이 정수, 소수점 1자리, 2자리 등으로 표시될지를 결정합니다.

## Aspose.Tasks로 ms project 통화를 처리하는 이유
- **Microsoft Project 설치 불필요** – Java를 지원하는 모든 플랫폼에서 *.mpp* 파일을 직접 작업합니다.  
- **강력한 타입 안전성** – API가 강타입 값을 반환하므로 파싱 오류가 감소합니다.  
- **성능 최적화** – 대형 프로젝트를 빠르게 로드하고 필요한 필드만 추출합니다.  
- **크로스 플랫폼** – Windows, Linux, macOS 어디서든 수정 없이 실행됩니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있어야 합니다:

1. **Java 개발 환경** – JDK 8 이상 설치 및 설정 완료.  
2. **Aspose.Tasks for Java** – 공식 사이트에서 최신 JAR 다운로드: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **기본 Java 지식** – Java 프로젝트 생성, 외부 라이브러리 추가, `main` 메서드 실행에 익숙해야 합니다.  

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 1단계: 데이터 디렉터리 정의
**java 프로젝트 파일**(`*.mpp`)이 들어 있는 폴더를 지정합니다.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 `project.mpp` 파일이 위치한 절대 경로나 상대 경로로 교체하세요.

## 2단계: MPP 파일 로드  
이제 Aspose.Tasks를 사용해 **mpp** 파일을 로드하는 방법을 확인합니다.  
```java
Project project = new Project(dataDir + "project.mpp");
```
파일 이름이 정확히 일치하지 않으면 `IOException`이 발생합니다.

## 3단계: 통화 자리수 가져오기  
프로젝트가 로드된 상태에서 **ms project 통화** 자리수를 추출하는 코드는 한 줄입니다:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
이 호출은 소수점 자리수를 나타내는 `Integer`를 반환합니다(예: 센트는 `2`). 값은 콘솔에 출력되지만, 필요에 따라 변수에 저장해 추가 처리도 가능합니다.

## 일반적인 문제 및 팁
- **파일을 찾을 수 없음** – `dataDir` 경로와 파일 이름(확장자 포함)을 다시 확인하세요.  
- **지원되지 않는 파일 버전** – Aspose.Tasks는 Project 2000‑2024 형식을 지원합니다. 오래되었거나 손상된 파일은 변환이 필요할 수 있습니다.  
- **라이선스 미설정** – 개발 단계에서는 체험판으로 가능하지만, 상용 환경에서는 평가 워터마크를 없애기 위해 유효한 라이선스를 적용해야 합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks가 통화 자리수 외에 다른 Project 속성도 처리할 수 있나요?**  
A: 네, Aspose.Tasks는 작업, 리소스, 사용자 정의 필드 등 다양한 Project 요소를 조작할 수 있는 광범위한 기능을 제공합니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준 애플리케이션에 적합한가요?**  
A: 물론입니다. Aspose.Tasks는 고성능과 확장성을 갖춘 엔터프라이즈 급 프로젝트 요구 사항을 충족하도록 설계되었습니다.

**Q: Aspose.Tasks가 크로스‑플랫폼 개발을 지원하나요?**  
A: 예, Java Runtime Environment가 설치된 Windows, Linux, macOS 어디서든 Aspose.Tasks for Java를 사용할 수 있습니다.

**Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?**  
A: 네, [여기](https://releases.aspose.com/)에서 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

---

**마지막 업데이트:** 2025-12-05  
**테스트 환경:** Aspose.Tasks for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}