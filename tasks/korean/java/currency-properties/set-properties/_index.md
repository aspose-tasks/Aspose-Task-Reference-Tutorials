---
date: 2026-02-07
description: Aspose.Tasks 프로젝트에서 통화 코드를 Java로 설정하고, 통화 기호를 변경하며, Microsoft Project
  파일에 맞춤 통화 형식을 적용하는 방법을 배워보세요.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 통화 코드 Java – Aspose.Tasks 프로젝트에서 설정하는 방법
url: /ko/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 통화 코드 설정 방법 – Java 가이드

## 소개
이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 Microsoft Project 파일의 **통화 코드(java)를 설정하는 방법**을 배웁니다. 국제 팀을 위해 *통화를 변경*하거나, *통화 기호*를 조정하거나, **맞춤 통화 형식**을 적용해야 할 경우, 아래 단계가 명확한 설명과 바로 실행 가능한 코드와 함께 과정을 안내합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Tasks for Java.  
- **통화 기호를 변경할 수 있나요?** 예 – `CurrencySymbolPositionType` 및 `Prj.CURRENCY_SYMBOL`을 사용합니다.  
- **지원되는 파일 형식은?** XML, MPP 및 `SaveFileFormat`을 통해 지원되는 기타 여러 형식.  
- **개발에 라이선스가 필요합니까?** 테스트용 무료 체험판으로 가능하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **구현 소요 시간은?** 기본 설정 기준으로 약 5‑10분 정도.

## Aspose.Tasks에서 통화 코드 Java 설정하기
프로젝트의 통화는 비용 값이 표시되는 방식을 정의합니다—코드(예: `AUD`), 소수점 자리수, 기호(`$`), 그리고 기호 위치. 이러한 속성을 설정하면 모든 비용 관련 필드(리소스 요금, 작업 예산 등)가 대상 청중에 맞는 올바른 통화 형식을 반영합니다.

## 통화 변경에 Aspose.Tasks를 사용하는 이유
- **Microsoft Project 설치 불필요** – 서버 어디서든 파일을 조작할 수 있습니다.  
- **전체 API 지원** – 모든 통화 관련 필드가 `Prj` 상수를 통해 노출됩니다.  
- **크로스 플랫폼** – Windows, Linux, macOS에서 Java 호환 IDE와 함께 작동합니다.  
- **고성능** – 대용량 프로젝트 파일을 빠르고 안정적으로 처리합니다.  
- **맞춤 통화 형식 지원** – 기호, 소수점 자리수, 위치 등을 지역 표준에 맞게 정의할 수 있습니다.

## 사전 준비 사항
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [Aspose.Tasks 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 받으세요.  
3. **IDE** – Eclipse, IntelliJ IDEA 또는 선호하는 편집기.  
4. **쓰기 가능한 폴더** – 생성된 프로젝트 파일을 저장할 위치.

## 패키지 가져오기
프로젝트 속성 및 파일 처리를 위한 클래스를 먼저 가져옵니다.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 정의
소스 파일이 위치한 폴더와 출력이 기록될 폴더를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 2: 새 Project 인스턴스 생성
새 `Project` 객체를 인스턴스화합니다. 이 객체는 메모리 내 Microsoft Project 파일을 나타냅니다.

```java
Project project = new Project();
```

### 단계 3: 통화 속성 설정
여기서 **통화 코드를 설정하는 방법**인 코드, 소수점 자리수, 기호, 기호 위치 등을 지정합니다.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **전문가 팁:** 기존 파일의 **프로젝트 통화**를 변경하려면 `new Project("file.mpp")` 로 파일을 로드한 뒤 위 설정을 적용하면 됩니다.

### 단계 4: 업데이트된 프로젝트 저장
프로젝트를 원하는 형식으로 디스크에 기록합니다. 이 예제에서는 XML 형식을 사용하지만 `SaveFileFormat.MPP` 를 선택할 수도 있습니다.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 단계 5: 성공 확인
오류 없이 작업이 완료되었음을 알리는 메시지를 출력합니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **`project.save` 시 `NullPointerException`** | `dataDir` 경로가 유효하지 않거나 쓰기 권한이 없습니다. | 디렉터리가 존재하고 Java 프로세스에 쓰기 권한이 있는지 확인하세요. |
| **통화 기호가 표시되지 않음** | 기호 위치가 로케일에 맞게 설정되지 않았습니다. | 금액 앞에 기호가 와야 한다면 `CurrencySymbolPositionType.Before` 를 사용하세요. |
| **프로젝트 파일이 MS Project에서 열리지 않음** | 호환되지 않는 설정으로 오래된 형식에 저장되었습니다. | 최신 MS Project 버전과 완전 호환을 위해 `SaveFileFormat.MPP` 로 저장하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 하나의 프로젝트에 여러 통화를 설정할 수 있나요?**  
A: 예, 리소스 또는 작업별로 통화 속성을 설정하여 하나의 프로젝트 파일 내에서 여러 통화를 관리할 수 있습니다.

**Q: Aspose.Tasks가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. 라이브러리는 Project 2000부터 최신 버전까지의 MPP 파일은 물론 XML 및 기타 형식을 지원합니다.

**Q: Aspose.Tasks가 맞춤 통화 형식을 지원하나요?**  
A: 예, 지역별 요구에 맞게 기호, 소수점 자리수 및 위치를 정의할 수 있습니다.

**Q: Aspose.Tasks를 다른 Java 라이브러리나 프레임워크와 통합할 수 있나요?**  
A: 가능합니다. 순수 Java API이므로 Spring, Hibernate, Maven, Gradle 등과 원활히 연동됩니다.

**Q: Aspose.Tasks에 대한 추가 지원이나 도움을 어디서 받을 수 있나요?**  
A: 커뮤니티 지원은 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 확인하거나, 공식 문서에서 자세한 API 레퍼런스를 참고하세요.

## 결론
이제 **통화 코드(java)를 설정하는 방법**, **통화 값을 변경하는 방법**, 그리고 **통화 기호를 변경하는 방법**을 Aspose.Tasks for Java를 사용해 알게 되었습니다. 이러한 기능을 통해 전 세계 팀을 위한 비용 데이터를 맞춤화하고, 지역별 보고서를 생성하며, 프로젝트 파일을 국경을 넘어 일관되게 유지할 수 있습니다.

---

**마지막 업데이트:** 2026-02-07  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}