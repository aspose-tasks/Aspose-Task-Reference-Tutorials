---
date: 2026-01-18
description: Aspose.Tasks for Java를 사용하여 MS Project에서 표준 요율 및 기타 리소스 속성을 설정하는 방법과
  리소스를 추가하고 효율적으로 관리하는 방법을 배웁니다.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 리소스의 표준 요율 설정 방법
url: /ko/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 리소스 표준 요율 설정

## 소개
Microsoft Project 파일과 상호 작용해야 하는 Java 애플리케이션을 개발하고 있다면, **리소스의 표준 요율 설정**은 가장 흔한 작업 중 하나입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **표준 요율** 및 기타 리소스 속성을 설정하는 방법을 배웁니다. 가이드를 마치면 프로젝트 객체를 생성하고, MS Project 파일에 리소스를 추가하며, MS Project 리소스를 자신 있게 관리할 수 있게 됩니다.

## 빠른 답변
- **프로젝트 파일을 다루는 주요 클래스는 무엇인가요?** `Project`
- **새 리소스를 추가하는 메서드는?** `project.getResources().add()`
- **표준 요율을 어떻게 설정하나요?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **프로덕션에 라이선스가 필요합니까?** 예, 유효한 Aspose.Tasks 라이선스가 필요합니다.
- **지원되는 Java 버전은?** Java 8+ (최신 JDK 권장).

## ‘표준 요율 설정’이란?
*표준 요율 설정* 작업은 리소스에 기본 시간당 비용을 할당합니다. 프로젝트 관리자는 이 값을 사용해 인건비를 계산하고, 비용 보고서를 생성하며, 예산을 예측합니다.

## 왜 Aspose.Tasks로 요율을 설정하나요?
- **Microsoft Project 설치 불필요** – Java에서 직접 파일을 조작합니다.
- **완전한 정밀도** – 초과 근무 및 비용 요율을 포함한 모든 리소스 필드가 보존됩니다.
- **크로스 플랫폼** – Windows, Linux, macOS에서 작동합니다.
- **자동화 친화적** – 배치 처리나 CI 파이프라인 통합에 이상적입니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하십시오.

### Java 개발 환경 설정
1. JDK 설치: 시스템에 Java Development Kit (JDK)가 설치되어 있는지 확인하십시오. [Oracle 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드할 수 있습니다.
2. IDE 설정: IntelliJ IDEA, Eclipse, NetBeans 등 통합 개발 환경(IDE)을 선택하고 머신에 설정하십시오.

### Aspose.Tasks for Java 설치
1. Aspose.Tasks for Java 다운로드: [다운로드 페이지](https://releases.aspose.com/tasks/java/)로 이동하여 최신 버전의 Aspose.Tasks for Java를 획득하십시오.
2. 프로젝트에 통합: Aspose.Tasks for Java 라이브러리를 의존성으로 추가하여 Java 프로젝트에 통합하십시오.

## 패키지 가져오기
시작하려면 Aspose.Tasks for Java에서 필요한 패키지를 프로젝트에 가져와야 합니다. 이 단계에서는 필요한 기능에 접근할 수 있게 됩니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## 단계 1: Project 객체 생성
**Project 객체**를 생성하는 것은 모든 MS Project 조작의 첫 번째 단계입니다. 이는 메모리 내에서 전체 프로젝트 파일을 나타냅니다.

```java
Project project = new Project();
```

## 단계 2: 리소스 추가 (add resource ms project)
이제 Resources 컬렉션을 사용하여 **MS Project에 리소스를 추가**합니다. 리소스 이름은 일정에 맞게 자유롭게 지정할 수 있습니다.

```java
Resource rsc = project.getResources().add("Rsc");
```

## 단계 3: 리소스 속성 설정 (how to set rates)
여기서 **표준 요율**을 설정하고 초과 근무 요율을 설정하는 방법을 보여줍니다. 이러한 요율은 정밀도를 유지하기 위해 `BigDecimal` 값으로 저장됩니다.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## 일반적인 문제와 해결책
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `NullPointerException` when calling `set` | 리소스가 올바르게 추가되지 않았습니다. | `project.getResources().add()`가 null이 아닌 `Resource`를 반환하도록 확인하세요. |
| Rates appear as 0 in the saved file | `int`를 사용하고 `BigDecimal`을 사용하지 않음. | 금액 값에는 항상 `BigDecimal.valueOf()`를 사용하세요. |
| License not found | `Project` 생성 전에 라이선스 파일을 로드하지 않음. | 프로그램 시작 시 라이선스를 로드하세요 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 결론
이 단계들을 따라 **Project 객체를 생성**, **MS Project에 리소스를 추가**, 그리고 **표준 요율 및 기타 리소스 속성을 설정**하는 방법을 배웠습니다. 이를 통해 비용 계산을 자동화하고, 맞춤형 보고서를 생성하며, Java에서 MS Project 리소스를 완전히 관리할 수 있습니다.

## FAQ
### Aspose.Tasks for Java가 복잡한 MS Project 파일을 처리할 수 있나요?
예, Aspose.Tasks for Java는 복잡한 작업 계층 구조를 포함한 다양한 MS Project 파일 형식을 처리할 수 있습니다.
### Aspose.Tasks for Java에 대한 무료 체험판이 있나요?
예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험판을 이용할 수 있습니다.
### Aspose.Tasks for Java 지원은 어디서 찾을 수 있나요?
[Aspose.Tasks 지원 포럼](https://forum.aspose.com/c/tasks/15)에서 도움을 받거나 토론에 참여할 수 있습니다.
### Aspose.Tasks for Java 임시 라이선스를 어떻게 얻을 수 있나요?
평가 목적으로 [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 획득할 수 있습니다.
### Aspose.Tasks for Java 정식 라이선스 버전을 어디서 구매할 수 있나요?
[Aspose.Tasks 구매 페이지](https://purchase.aspose.com/buy)에서 정식 라이선스를 구매할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-18  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신)  
**작성자:** Aspose