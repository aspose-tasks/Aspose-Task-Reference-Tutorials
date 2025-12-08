---
date: 2025-12-05
description: Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호를 추출하고 Java에서 통화 기호를 변경하는 방법을
  배웁니다. 프로젝트 관리에 필요한 통화 기호를 Java에서 빠르게 가져옵니다.
language: ko
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호 추출
url: /java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 mpp 파일에서 통화 기호 추출하기

## 소개
이 튜토리얼에서는 Microsoft Project 파일에서 **통화 기호 mpp**를 추출하고, Aspose.Tasks 라이브러리를 사용하여 **Java에서 통화 기호 변경** 또는 **Java에서 통화 기호 가져오기** 방법을 알아봅니다. 보고서 도구를 만들거나, Project 데이터를 재무 시스템에 통합하거나, UI에 올바른 통화 기호를 표시해야 할 때, 이 작지만 필수적인 작업을 마스터하면 Java 애플리케이션을 보다 견고하고 사용자 친화적으로 만들 수 있습니다.

## 빠른 답변
- **“extract currency symbol mpp”는 무엇을 의미하나요?** MPP(Microsoft Project) 파일에 저장된 통화 기호를 읽는 것을 의미합니다.  
- **어떤 라이브러리를 사용하나요?** Aspose.Tasks for Java가 간단한 API를 제공합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **소요 시간은 얼마나 되나요?** 아래 코드를 사용하면 1분 이내에 기호를 얻을 수 있습니다.  
- **기호를 변경할 수도 있나요?** 네 – 동일한 `Prj.CURRENCY_SYMBOL` 속성을 사용해 새 값을 설정할 수 있습니다.

## “extract currency symbol mpp”란?
Microsoft Project는 프로젝트 파일 헤더에 통화 기호(예: $, €, £)를 저장합니다. **통화 기호 mpp 추출** 작업은 해당 값을 읽어 프로그램에서 표시하거나 조작할 수 있도록 합니다.

## 왜 Java에서 통화 기호를 변경해야 할까요?
프로젝트는 종종 여러 지역에 걸쳐 진행됩니다. 런타임에 **Java에서 통화 기호를 변경**하면 전체 프로젝트 파일을 다시 만들지 않고도 보고서, 인보이스, 대시보드 등을 현지 시장에 맞게 조정할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받으세요.  
3. 코드에서 참조할 수 있는 유효한 **project.mpp** 파일을 폴더에 배치합니다.

## 패키지 가져오기
프로젝트 파일을 다루기 위해 필요한 클래스를 먼저 가져옵니다.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 1단계: 데이터 디렉터리 정의
*.mpp* 파일이 위치한 경로를 애플리케이션에 알려줍니다.

```java
String dataDir = "Your Data Directory";
```

> **팁:** `System.getProperty("user.dir")`를 사용하면 어떤 머신에서도 동작하는 절대 경로를 만들 수 있습니다.

## 2단계: MS Project 파일 로드
메모리 상에 MPP 파일을 나타내는 `Project` 객체를 생성합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 3단계: 통화 기호 가져오기(및 선택적 변경)
이제 `Prj.CURRENCY_SYMBOL` 속성을 읽어 **Java에서 통화 기호를 가져오기**합니다. 동일한 속성에 새 문자열을 할당하면 **Java에서 통화 기호를 변경**할 수도 있습니다.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` 호출은 콘솔에 기호(예: `$`)를 출력하여 추출이 성공했음을 확인합니다.

## 일반적인 문제 및 해결 방법
| 증상 | 가능한 원인 | 해결 방법 |
|------|------------|----------|
| `NullPointerException` on `project.get(...)` | 파일 경로가 잘못되었거나 파일을 찾을 수 없음 | `dataDir`와 파일 이름을 확인하고, `new File(dataDir).exists()`로 디버그 |
| 예상치 못한 기호(예: `?`) | 비표준 로케일로 프로젝트가 생성됨 | 원본 MPP 파일에 실제 통화 기호가 정의되어 있는지 확인하고, 위 예시처럼 프로그래밍적으로 설정 |
| 라이선스 오류 | 유효한 라이선스 파일 없이 체험판 사용 | `Project` 객체를 만들기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 라이선스 로드 |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 통화 기호 외에 다른 프로젝트 속성도 조작할 수 있나요?**  
A: 네, Aspose.Tasks를 이용하면 작업, 리소스, 할당, 캘린더 및 다양한 프로젝트 속성을 편집할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: 물론입니다. MPP, MPT, XML 형식을 포함해 Project 98부터 최신 버전까지 지원합니다.

**Q: Aspose.Tasks는 개발자를 위한 문서와 지원을 제공하나요?**  
A: 풍부한 API 문서, 코드 예제, 전용 지원 포럼이 Aspose.Tasks 웹사이트에 마련되어 있습니다.

**Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?**  
A: 네 – [Aspose 웹사이트](https://purchase.aspose.com/buy)에서 완전 기능의 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 임시 라이선스는 어떻게 얻나요?**  
A: 평가용으로는 [Aspose 임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 발급받을 수 있습니다.

---

**최종 업데이트:** 2025-12-05  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}