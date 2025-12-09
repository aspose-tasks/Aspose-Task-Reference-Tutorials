---
date: 2025-12-04
description: Aspose.Tasks for Java를 사용하여 MS Project 파일에서 통화 속성을 읽는 방법을 배워보세요. 단계별
  가이드를 따라 프로그래밍 방식으로 통화 코드, 기호, 소수 자릿수 및 위치를 추출합니다.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks 프로젝트를 사용한 Java에서 통화 속성 읽기
url: /ko/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 프로젝트에서 Java로 통화 속성 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java API를 사용하여 Microsoft Project 파일에서 **read currency properties java**를 읽는 방법을 알아봅니다. Aspose.Tasks를 사용하면 Microsoft Project를 설치하지 않아도 .mpp 파일을 다룰 수 있어 자동 보고, 데이터 마이그레이션 또는 Java 기반 엔터프라이즈 애플리케이션과의 통합에 이상적입니다. 이 가이드를 끝까지 따라하면 프로젝트 파일에서 통화 코드, 기호, 소수점 자리수 및 기호 위치를 직접 추출할 수 있게 됩니다.

## 빠른 답변
- **“read currency properties java”는 무엇을 의미하나요?** Java 코드를 사용하여 MS Project 파일에서 통화와 관련된 메타데이터(코드, 기호, 자리수, 위치)를 가져오는 것을 의미합니다.  
- **시도하려면 라이선스가 필요합니까?** Aspose.Tasks의 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다.  
- **필요한 JDK 버전은?** Java 8 이상.  
- **통화 설정을 읽은 후 수정할 수 있나요?** 예, Aspose.Tasks는 통화 속성에 대한 읽기 및 쓰기 작업을 모두 지원합니다.  
- **모든 .mpp 버전과 호환되나요?** API는 Microsoft Project 2003‑2021에서 생성된 파일을 지원합니다.

## read currency properties java란?
Java에서 통화 속성을 읽는다는 것은 Microsoft Project 파일에 정의된 프로젝트 수준 설정을 접근하여 금액이 어떻게 표시되는지를 확인하는 것을 말합니다. 여기에는 ISO 통화 코드(예: **USD**), 기호(**$**), 소수점 자리수, 그리고 기호가 금액 앞에 표시되는지 뒤에 표시되는지 여부가 포함됩니다.

## 왜 Aspose.Tasks로 read currency properties java를 사용하나요?
- **Microsoft Project 설치 불필요** – Java를 지원하는 모든 플랫폼에서 API를 사용할 수 있습니다.  
- **빠른 인‑프로세스 추출** – 대량의 프로젝트 파일을 배치 처리하기에 적합합니다.  
- **전체 제어** – 추출한 값을 사용자 정의 보고와 결합하거나 ERP 시스템에 통합할 수 있습니다.  
- **버전 간 지원** – Project 2003부터 최신 2021 릴리스까지의 .mpp 파일을 모두 처리합니다.

## 전제 조건
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – Java 8 이상이 설치되어 `PATH`에 설정되어 있어야 합니다.  
2. **Aspose.Tasks for Java JAR** – 최신 라이브러리를 [here](https://releases.aspose.com/tasks/java/)에서 다운로드하고 프로젝트 클래스패스에 추가합니다.  

## 패키지 가져오기
프로젝트 조작에 필요한 Aspose.Tasks 네임스페이스를 가져옵니다:

```java
import com.aspose.tasks.*;
```

## 단계 1: 프로젝트 디렉터리 설정
`.mpp` 파일이 들어 있는 폴더를 정의합니다. 경로를 변수에 저장하면 코드를 재사용하기 쉽습니다:

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"`를 `project.mpp` 파일이 위치한 절대 경로나 상대 경로로 교체하세요.*

## 단계 2: 프로젝트 리더 인스턴스 생성
Microsoft Project 파일을 `Project` 객체로 로드합니다. 이 객체를 통해 통화 설정을 포함한 모든 프로젝트 속성에 접근할 수 있습니다:

```java
Project project = new Project(dataDir + "project.mpp");
```

*파일 이름이 다르면 `"project.mpp"`를 해당 이름으로 변경하세요.*

## 단계 3: 통화 속성 표시
이제 `Prj` 열거형을 사용해 각 통화 속성을 가져와 콘솔에 출력합니다. API는 객체를 반환하므로 문자열로 변환해 표시하면 됩니다:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**출력 예시:**  
- **Currency Code** – `USD`, `EUR`, `JPY`와 같은 ISO‑4217 코드.  
- **Currency Digits** – 대부분의 통화는 `2`, 일본 엔은 `0`.  
- **Currency Symbol** – 보고서에 표시되는 문자(`$`, `€`, `¥`).  
- **Currency Symbol Position** – 금액 앞에 표시하면 `0`, 뒤에 표시하면 `1`.  

## 단계 4: 프로세스 완료
추출이 성공적으로 끝났음을 알리는 간단한 메시지를 출력합니다. 배치 작업의 일부로 실행될 때 유용합니다:

```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` 경로가 잘못되었거나 파일 이름이 틀렸습니다. | 디렉터리 문자열을 확인하고 지정된 위치에 `.mpp` 파일이 존재하는지 확인하세요. |
| **NullPointerException on `project.get(...)`** | 프로젝트 파일에 통화 정보가 없거나(드물게) 속성 키가 잘못되었습니다. | 읽기 전에 `project.contains(Prj.CURRENCY_CODE)`를 사용해 존재 여부를 확인하세요. |
| **LicenseException** | 프로덕션 환경에서 유효한 Aspose.Tasks 라이선스 없이 실행했습니다. | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 코드를 `Project` 객체를 만들기 전에 추가하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks가 Microsoft Project 모든 버전과 호환되나요?**  
A: Aspose.Tasks는 Microsoft Project 2003‑2021에서 생성된 .mpp 파일을 지원하므로 구버전부터 최신 포맷까지 모두 처리할 수 있습니다.

**Q: Aspose.Tasks를 사용해 통화 속성을 수정할 수 있나요?**  
A: 예, 통화 설정을 읽고 쓸 수 있습니다. `project.set(Prj.CURRENCY_CODE, "EUR");`와 같이 설정한 뒤 프로젝트를 저장하면 됩니다.

**Q: Aspose.Tasks를 상업적으로 사용할 수 있나요?**  
A: 물론입니다. 상업용 라이브러리이며, 라이선스는 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: Aspose.Tasks에 무료 체험판이 있나요?**  
A: 예, 완전 기능을 제공하는 체험판을 [here](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: Aspose.Tasks에 대한 지원이나 도움을 어디서 받을 수 있나요?**  
A: 공식 Aspose.Tasks 포럼이 가장 좋은 지원 채널이며, [here](https://forum.aspose.com/c/tasks/15)에서 방문할 수 있습니다.

## 결론
이제 Aspose.Tasks for Java를 사용해 MS Project 파일에서 **read currency properties java**를 읽는 방법을 익혔습니다. 이 기능을 활용하면 통화 메타데이터를 사용자 정의 보고서, 재무 분석 또는 통합 파이프라인에 쉽게 포함시킬 수 있으며, Microsoft Project에 의존하지 않고도 작업을 수행할 수 있습니다. 속성을 수정하거나 다른 프로젝트 속성과 결합해 보다 풍부한 솔루션을 만들어 보세요.

---

**마지막 업데이트:** 2025-12-04  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}