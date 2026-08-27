---
date: 2026-03-27
description: Aspose.Tasks for Java를 사용하여 MS Project 개요 코드를 프로그래밍 방식으로 검색하는 방법을 배우세요.
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

# Aspose.Tasks에서 MS Project 개요 코드 가져오기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **ms project outline codes**를 가져오는 방법을 알아봅니다. MS Project의 개요 코드는 작업, 리소스 및 할당을 분류하는 강력한 방법을 제공하며, 이를 프로그래밍 방식으로 액세스하면 맞춤형 보고서, 자동화 또는 통합 솔루션을 구축할 수 있습니다. 자체 프로젝트에 복사하여 사용할 수 있는 완전한 단계별 예제를 안내합니다.

## 빠른 답변
- **코드가 무엇을 하나요?** 프로젝트 파일을 로드하고 모든 개요 코드 정의와 해당 마스크 및 값을 출력합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java(최신 버전).  
- **라이선스가 필요합니까?** 개발에는 체험판을 사용할 수 있으며, 운영 환경에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **코드를 가져온 후 수정할 수 있나요?** 예 – 동일한 API를 사용해 개요 코드를 추가, 편집 또는 삭제할 수 있습니다.

## ms project 개요 코드는 무엇인가요?
개요 코드는 기본 계층 구조를 넘어 작업을 그룹화하고 필터링할 수 있게 해주는 사용자 정의 필드입니다. 단순한 숫자값, 문자열 또는 조직 수준에서 정의된 전사적 사용자 정의 코드가 될 수 있습니다. 이러한 코드를 읽으면 대시보드를 구동하고, 데이터를 내보내며, 명명 규칙을 자동으로 적용할 수 있습니다.

## 왜 Aspose.Tasks로 ms project 개요 코드를 가져와야 할까요?
- **자동화:** 수동 내보내기 없이 보고서를 생성하거나 워크플로를 트리거합니다.  
- **통합:** 개요 코드를 ERP, PPM 또는 BI 도구와 동기화합니다.  
- **맞춤화:** 코드 값에 기반한 비즈니스 규칙을 적용합니다(예: 비용 할당).  
- **크로스‑플랫폼:** Windows, Linux, macOS에서 동작하며 Microsoft Project UI와 무관합니다.

## 개요 코드를 위해 MPP 파일을 읽는 방법은?
MPP(Microsoft Project) 파일을 읽는 것은 개요 코드를 추출하기 위한 첫 단계입니다. Aspose.Tasks는 파일 형식을 추상화하므로 바이너리 구조를 직접 파싱할 필요가 없습니다. `Project` 클래스가 복잡한 작업을 처리하므로 실제 필요한 데이터에 집중할 수 있습니다.

## MS Project의 사용자 정의 필드
개요 코드는 MS Project의 **사용자 정의 필드** 유형입니다. 표준 필드는 날짜, 기간 및 리소스를 다루는 반면, 사용자 정의 필드를 통해 조직 고유 정보를 저장할 수 있습니다. Aspose.Tasks를 통해 이를 액세스하면 프로그래밍 방식으로 동일한 유연성을 얻을 수 있습니다.

## 전제 조건
시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하십시오:

### 1. Java 개발 환경
시스템에 Java Development Kit(JDK)이 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 JDK를 다운로드하고 설치할 수 있습니다.

### 2. Aspose.Tasks 라이브러리
Aspose.Tasks 라이브러리를 다운로드하여 Java 프로젝트에 포함하십시오. 라이브러리는 [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
먼저 Java 코드에서 Aspose.Tasks의 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

이제 제공된 예제 코드를 여러 단계로 나눠 살펴보겠습니다:

## 1단계: 프로젝트 로드
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
이 단계에서는 제공된 파일 이름을 사용하여 Microsoft Project 파일을 `Project` 객체에 로드합니다.

## 2단계: 개요 코드 가져오기
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
프로젝트의 각 개요 코드 정의를 반복합니다.

## 3단계: 개요 코드 속성 접근
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Alias, Field ID, Field Name 등 개요 코드 정의의 다양한 속성을 가져와 출력합니다.

## 4단계: 전사 사용자 정의 코드 확인
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
개요 코드가 전사 사용자 정의 코드인지 확인하고 결과를 출력합니다.

## 5단계: 개요 코드 마스크 표시
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
개요 코드와 연결된 각 마스크를 반복하며 레벨과 마스크 값을 출력합니다.

## 6단계: 개요 코드 값 표시
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
각 개요 코드 값을 반복하며 설명, value ID, 값 및 유형을 출력합니다.

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **출력 없음** | 프로젝트 파일 경로가 올바르지 않음 | `projectName`이 유효한 `.mpp` 파일을 가리키는지 확인하십시오. |
| **Null 값** | 파일에 개요 코드가 정의되지 않음 | 프로젝트 파일에 실제로 개요 코드가 포함되어 있는지 확인하십시오(MS Project UI에서 확인). |
| **LicenseException** | 적절한 활성화 없이 체험판 사용 | `License license = new License(); license.setLicense("Aspose.Tasks.lic");`를 사용해 임시 또는 정식 라이선스를 적용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용하여 프로젝트 파일의 개요 코드를 수정할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 프로그래밍 방식으로 개요 코드를 수정할 수 있는 API를 제공합니다. 동일한 `Project` 객체를 사용해 정의를 추가, 편집 또는 삭제할 수 있습니다.

**Q: Aspose.Tasks for Java의 체험 버전을 사용할 수 있나요?**  
A: 예, [Aspose.Tasks 웹사이트](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 기술 지원은 어떻게 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하여 문의 사항을 게시하면 기술 지원을 받을 수 있습니다.

**Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?**  
A: 예, [구매 페이지](https://purchase.aspose.com/temporary-license/)에서 Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 전체 문서는 어디에서 찾을 수 있나요?**  
A: Aspose.Tasks for Java 사용에 대한 자세한 정보는 [문서](https://reference.aspose.com/tasks/java/)를 참고하십시오.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **ms project outline codes**를 가져오는 방법을 배웠습니다. 제공된 단계를 따르면 Java 애플리케이션에서 개요 코드를 효과적으로 액세스하고 조작할 수 있어 맞춤형 보고서, 자동화 및 기타 전사 시스템과의 통합과 같은 고급 프로젝트 관리 기능을 구현할 수 있습니다.

---

**마지막 업데이트:** 2026-03-27  
**테스트 대상:** Aspose.Tasks for Java (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}