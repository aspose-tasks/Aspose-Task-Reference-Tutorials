---
date: 2026-01-28
description: Aspose.Tasks for Java를 사용하여 확장 작업 속성을 읽는 방법과 사용자 정의 필드 유형을 효율적으로 전환하는
  방법을 배워보세요.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 확장 작업 속성 읽기
url: /ko/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 확장 작업 속성 읽기

## 소개
이 포괄적인 튜토리얼에서는 Aspose.Tasks 라이브러리를 사용해 Microsoft Project 파일에서 **확장 작업 속성**을 읽는 방법을 알아봅니다. 보고서 도구를 구축하든, 데이터를 동기화하든, 혹은 사용자 정의 필드에 대한 심층적인 통찰이 필요하든, 이 기능을 마스터하면 프로젝트에 저장된 모든 정보를 추출할 수 있습니다. 필요한 설정 과정을 단계별로 안내하고, 속성을 처리할 때 사용자 정의 필드 유형을 전환하는 방법을 보여주며, 일반적인 함정을 피하기 위한 실용적인 팁도 제공합니다.

## 빠른 답변
- **“확장 작업 속성을 읽는다”는 무슨 의미인가요?** 기본 작업 속성을 넘어서는 사용자 정의 필드 값을 추출하는 것을 의미합니다.  
- **어떤 클래스를 통해 이러한 속성에 접근하나요?** Aspose.Tasks의 `ExtendedAttribute` 클래스입니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **런타임에 속성 유형을 변경할 수 있나요?** 예 – `CustomFieldType`을 기준으로 **사용자 정의 필드 유형 전환**을 위해 `switch` 문을 사용합니다.  
- **Java 8 이상과 호환되나요?** 물론입니다. API는 JDK 8+을 지원합니다.

## 확장 작업 속성이란?
확장 작업 속성은 Microsoft Project에서 표준 작업 속성을 보완하는 사용자 정의 필드(텍스트, 날짜, 숫자, 플래그 등)입니다. Aspose.Tasks는 각 `Task` 객체에 연결된 `ExtendedAttribute` 컬렉션을 통해 이러한 속성을 프로그래밍 방식으로 읽고 수정할 수 있게 합니다.

## 왜 확장 작업 속성을 읽어야 할까요?
- **전체 가시성:** 이해관계자가 일정에 추가한 맞춤 데이터를 파악할 수 있습니다.  
- **자동화:** 대시보드에 데이터를 채우고, 맞춤 보고서를 생성하거나, 수동 내보내기 없이 다른 시스템으로 데이터를 마이그레이션할 수 있습니다.  
- **유연성:** 텍스트, 날짜, 기간, 비용, 플래그 등 모든 사용자 정의 필드 유형을 각각에 맞게 처리할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:
- Java 프로그래밍에 대한 기본 지식.  
- 머신에 설치된 Java Development Kit (JDK).  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE.

## 패키지 가져오기
Aspose.Tasks 프로젝트에 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## 단계 1: 작업 및 확장 속성 접근
프로젝트 파일을 로드하고 각 작업을 순회하면서 확장 속성에 접근합니다:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## 단계 2: 필드 ID 및 값 GUID 가져오기
사용 중인 사용자 정의 필드를 이해하는 데 도움이 되는 내부 식별자를 출력합니다:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## 단계 3: 확장 작업 속성을 읽을 때 사용자 정의 필드 유형 전환 방법
`CustomFieldType`에 대한 `switch` 문을 사용해 각 데이터 유형을 올바르게 처리합니다:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

프로젝트의 각 작업에 대해 이 단계를 반복하면 모든 확장 작업 속성을 탐색하고 조작할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **Null 값 반환** | 소스 .mpp 파일에서 해당 사용자 정의 필드가 실제로 채워져 있는지 확인하세요. |
| **잘못된 유형 표시** | `switch` 문에서 올바른 `CustomFieldType`을 사용했는지 확인하세요; 유형이 일치하지 않으면 기본값이 표시됩니다. |
| **대형 프로젝트에서 성능 저하** | 작업을 배치로 처리하거나 `project.getRootTask().getChildren().stream()`과 적절한 프레디케이트를 사용해 필요한 작업만 필터링하세요. |

## 자주 묻는 질문
### 프로그래밍 방식으로 확장 작업 속성을 수정할 수 있나요?
예, Aspose.Tasks for Java를 사용해 확장 작업 속성을 수정할 수 있습니다. 자세한 내용은 공식 문서를 참고하세요.

### 체험 버전을 사용할 수 있나요?
예, 무료 체험판은 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

### Aspose.Tasks for Java에 대한 지원은 어디서 찾을 수 있나요?
지원이 필요하면 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

### 임시 라이선스를 어떻게 얻을 수 있나요?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.Tasks for Java 전체 버전을 어디서 구매할 수 있나요?
전체 버전은 [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

---

**마지막 업데이트:** 2026-01-28  
**테스트 환경:** Aspose.Tasks Java API (최신 안정 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}