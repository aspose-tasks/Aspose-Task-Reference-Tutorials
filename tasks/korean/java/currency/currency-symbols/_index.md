---
date: 2026-02-10
description: Aspose.Tasks for Java를 사용하여 통화 기호와 같은 Java 프로젝트 속성을 추출하고 업데이트하는 방법을 배웁니다.
  프로젝트 통화를 변경하고 통화 기호를 쉽게 가져옵니다.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: java 프로젝트 속성 – Aspose.Tasks for Java를 사용하여 MPP에서 통화 기호 추출
url: /ko/java/currency/currency-symbols/
weight: 12
---

)"

**Author:** Aspose -> "**작성자:** Aspose"

Now close shortcodes.

Everything else unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 mpp에서 통화 기호 추출하기

## 소개
이 튜토리얼에서는 **java project properties**를 다루는 방법—특히 Microsoft Project (MPP) 파일에서 통화 기호를 추출하고 Aspose.Tasks 라이브러리를 사용하여 **change currency symbol java** 또는 **retrieve currency symbol java** 하는 방법을 배웁니다. 보고서 도구를 구축하거나, 프로젝트 데이터를 금융 시스템에 통합하거나, UI에 올바른 통화 기호를 표시해야 할 때, 이 작지만 필수적인 작업을 마스터하면 Java 애플리케이션이 더 견고하고 사용자 친화적으로 변합니다.

## 빠른 답변
- **“extract currency symbol mpp”가 무엇을 의미하나요?** MPP(Microsoft Project) 파일에 저장된 통화 기호를 읽는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.Tasks for Java가 간단한 API를 제공합니다.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **소요 시간은 얼마나 되나요?** 아래 코드를 사용하면 1분 이내에 기호를 얻을 수 있습니다.  
- **기호를 변경할 수도 있나요?** 네 — 동일한 `Prj.CURRENCY_SYMBOL` 속성을 사용하여 새 값을 설정할 수 있습니다.

## “extract currency symbol mpp”란?
Microsoft Project는 통화 기호(예: $, €, £)를 프로젝트 파일 헤더에 저장합니다. **extract currency symbol mpp** 작업은 해당 값을 읽어 프로그램에서 표시하거나 조작할 수 있게 합니다.

## 왜 java project properties에서 통화 기호를 업데이트해야 할까요?
프로젝트는 종종 여러 지역에 걸쳐 진행됩니다. 런타임에 **change project currency** 또는 **update currency symbol**을 할 수 있으면 보고서, 청구서, 대시보드 등을 현지 시장에 맞게 조정할 수 있어 전체 프로젝트 파일을 다시 만들 필요가 없습니다. 이러한 유연성은 java project properties를 효과적으로 관리하는 핵심 요소입니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR를 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. 코드에서 참조할 수 있는 폴더에 유효한 **project.mpp** 파일을 배치합니다.

## 패키지 가져오기
먼저, Project 파일을 다루는 데 필요한 클래스를 가져옵니다.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 단계 1: 데이터 디렉터리 정의
애플리케이션에 *.mpp* 파일이 위치한 경로를 알려줍니다.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `System.getProperty("user.dir")`를 사용하여 모든 머신에서 동작하는 절대 경로를 구성합니다.

## 단계 2: MS Project 파일 로드
`Project` 객체를 생성하여 메모리 상에 MPP 파일을 나타냅니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 단계 3: 통화 기호 가져오기(및 선택적 변경)
이제 `Prj.CURRENCY_SYMBOL` 속성을 읽어 **retrieve currency symbol java**를 수행합니다. 동일한 속성에 새 문자열을 할당하면 **change currency symbol java**(또는 **change project currency**)도 할 수 있습니다.

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
| `project.get(...)`에서 NullPointerException | 파일 경로가 잘못되었거나 파일을 찾을 수 없음 | `dataDir` 및 파일 이름을 확인하고, 디버깅을 위해 `new File(dataDir).exists()`를 사용하십시오 |
| 예상치 못한 기호(예: `?`) | 프로젝트가 비표준 로케일로 생성됨 | 원본 MPP 파일에 실제로 통화 기호가 정의되어 있는지 확인하고, 위와 같이 프로그래밍 방식으로 설정할 수 있습니다 |
| 라이선스 오류 | 유효한 라이선스 파일 없이 체험판을 사용 | `Project` 객체를 만들기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 로 라이선스를 로드하십시오 |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용하여 통화 기호 외에 다른 프로젝트 속성을 조작할 수 있나요?**  
A: 네, Aspose.Tasks를 통해 작업, 리소스, 할당, 캘린더 및 기타 많은 프로젝트 속성을 편집할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 MS Project 파일과 호환되나요?**  
A: 물론입니다. Project 98부터 최신 버전까지 MPP, MPT, XML 형식을 지원합니다.

**Q: Aspose.Tasks가 개발자를 위한 문서와 지원을 제공하나요?**  
A: 포괄적인 API 문서, 코드 예제, 전용 지원 포럼이 Aspose.Tasks 웹사이트에 제공됩니다.

**Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?**  
A: 네 – 완전한 기능을 갖춘 무료 체험판을 [Aspose 웹사이트](https://purchase.aspose.com/buy)에서 다운로드할 수 있습니다.

**Q: Aspose.Tasks의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 평가 목적을 위해 [Aspose 임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 제공받을 수 있습니다.

---

**마지막 업데이트:** 2026-02-10  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시점 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}