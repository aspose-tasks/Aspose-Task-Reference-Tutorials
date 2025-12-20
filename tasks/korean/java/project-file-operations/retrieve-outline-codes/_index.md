---
date: 2025-12-20
description: Aspose.Tasks for Java를 사용하여 프로그래밍 방식으로 MS Project 개요 코드를 검색하는 방법을 배우세요.
  프로젝트 관리 역량을 강화하세요.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 MS Project 개요 코드 가져오기
url: /ko/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS Project 개요 코드 검색하기

## 소개
이 튜토리얼에서는 **ms project 개요 코드를 검색하는 방법**을 Aspose.Tasks for Java를 사용해 알아봅니다. MS Project의 개요 코드는 작업, 리소스 및 할당을 분류하는 강력한 수단이며, 이를 프로그래밍 방식으로 접근하면 맞춤형 보고서, 자동화 또는 통합 솔루션을 구축할 수 있습니다. 여러분이 직접 프로젝트에 복사해 사용할 수 있는 완전한 단계별 예제를 함께 살펴보겠습니다.

## 빠른 답변
- **코드는 무엇을 하나요?** 프로젝트 파일을 로드하고 모든 개요 코드 정의, 해당 마스크 및 값을 출력합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (최신 버전).  
- **라이선스가 필요합니까?** 개발 단계에서는 평가판으로 충분하지만, 운영 환경에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **코드를 검색한 후 수정할 수 있나요?** 예 – 동일한 API를 사용해 개요 코드를 추가, 편집 또는 삭제할 수 있습니다.

## ms project 개요 코드는 무엇인가요?
개요 코드는 프로젝트 관리자가 기본 계층 구조를 넘어 작업을 그룹화하고 필터링할 수 있게 해주는 사용자 정의 필드입니다. 단순한 숫자값, 문자열, 혹은 조직 차원에서 정의된 엔터프라이즈 수준의 사용자 정의 코드가 될 수 있습니다. 이러한 코드를 읽어들이면 대시보드 구동, 데이터 내보내기, 명명 규칙 자동 적용 등을 구현할 수 있습니다.

## 왜 Aspose.Tasks로 ms project 개요 코드를 검색해야 할까요?
- **자동화:** 수동 내보내기 없이 보고서를 생성하거나 워크플로를 트리거합니다.  
- **통합:** ERP, PPM 또는 BI 도구와 개요 코드를 동기화합니다.  
- **맞춤화:** 코드 값에 기반한 비즈니스 규칙을 적용합니다(예: 비용 배분).  
- **크로스‑플랫폼:** Windows, Linux, macOS에서 동작하며 Microsoft Project UI와 무관합니다.

## 전제 조건
시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오.

### 1. Java Development Environment
시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다. Oracle 웹사이트에서 JDK를 다운로드하고 설치할 수 있습니다.

### 2. Aspose.Tasks Library
Aspose.Tasks 라이브러리를 Java 프로젝트에 포함하십시오. 라이브러리는 [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
먼저 Java 코드에서 Aspose.Tasks에 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

이제 제공된 예제 코드를 여러 단계로 나누어 살펴보겠습니다.

## 1단계: 프로젝트 로드
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
이 단계에서는 지정된 파일 이름을 사용해 Microsoft Project 파일을 `Project` 객체로 로드합니다.

## 2단계: 개요 코드 검색
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
프로젝트에 정의된 각 개요 코드 정의를 순회합니다.

## 3단계: 개요 코드 속성 접근
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
개요 코드 정의의 별칭, 필드 ID, 필드 이름 등 다양한 속성을 가져와 출력합니다.

## 4단계: 엔터프라이즈 사용자 정의 코드 확인
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
해당 개요 코드가 엔터프라이즈 사용자 정의 코드인지 확인하고 결과를 출력합니다.

## 5단계: 개요 코드 마스크 표시
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
개요 코드와 연결된 각 마스크를 순회하며 레벨과 마스크 값을 출력합니다.

## 6단계: 개요 코드 값 표시
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
각 개요 코드 값에 대해 설명, 값 ID, 실제 값 및 유형을 출력합니다.

## 공통 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **No output** | Project 파일 경로가 올바르지 않음 | `projectName`이 유효한 `.mpp` 파일을 가리키는지 확인하십시오. |
| **Null values** | 파일에 개요 코드가 정의되지 않음 | MS Project UI에서 실제로 개요 코드가 포함되어 있는지 확인하십시오. |
| **LicenseException** | 정식 활성화 없이 평가판 사용 | `License license = new License(); license.setLicense("Aspose.Tasks.lic");`와 같이 임시 또는 정식 라이선스를 적용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용해 Project 파일의 개요 코드를 수정할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 개요 코드를 프로그래밍 방식으로 수정할 수 있는 API를 제공합니다. 동일한 `Project` 객체를 사용해 정의를 추가, 편집 또는 삭제할 수 있습니다.

**Q: Aspose.Tasks for Java용 평가판 버전이 있나요?**  
A: 예, [Aspose.Tasks 웹사이트](https://releases.aspose.com/)에서 무료 평가판 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 기술 지원은 어떻게 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 질문을 게시하면 기술 지원을 받을 수 있습니다.

**Q: Aspose.Tasks for Java용 임시 라이선스를 구매할 수 있나요?**  
A: 예, [구매 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 구매할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 전체 문서는 어디서 찾을 수 있나요?**  
A: 자세한 사용 방법은 [문서](https://reference.aspose.com/tasks/java/)를 참고하십시오.

## 결론
이 튜토리얼을 통해 Aspose.Tasks for Java를 사용해 **ms project 개요 코드를 검색**하는 방법을 배웠습니다. 제공된 단계들을 따라 하면 Java 애플리케이션에서 개요 코드를 효과적으로 접근하고 조작할 수 있어 맞춤형 보고서, 자동화 및 엔터프라이즈 시스템과의 통합 같은 고급 프로젝트 관리 기능을 구현할 수 있습니다.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}