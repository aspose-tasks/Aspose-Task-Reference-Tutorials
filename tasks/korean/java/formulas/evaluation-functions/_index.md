---
date: 2026-02-13
description: Java에서 프로젝트 객체를 생성하고 확장 속성을 추가한 뒤 Aspose.Tasks의 평가 기능을 사용하여 프로젝트 보고서를
  생성하는 방법을 배웁니다.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 프로젝트 보고서 생성 – Java 프로젝트 객체 생성
url: /ko/java/formulas/evaluation-functions/
weight: 10
---

 "Author". Keep them as text.

Also ensure we keep markdown formatting.

Let's produce final content.

Be careful with bullet points: translate.

Also "## Quick Answers" etc.

Let's translate.

I'll produce Korean translation.

Note: Keep code block placeholders as is.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 수식에서 지원 평가 함수

## 소개
Aspose.Tasks for Java를 사용하면 Java에서 **프로젝트 객체**를 생성하고 Microsoft Project 함수를 직접 코드 안에서 평가하여 **프로젝트 보고서**를 **생성**할 수 있습니다. 이러한 수식을 삽입하면 복잡한 계산을 수행하고, 맞춤형 보고서를 생성하며, 개발 환경을 떠나지 않고 프로젝트 분석을 자동화할 수 있습니다. 이번 튜토리얼에서는 프로젝트 객체를 만들고, 확장 속성을 추가한 뒤, 평가 함수를 사용해 **사용자 정의 필드 작업** 데이터를 **추가**하는 과정을 단계별로 살펴보겠습니다.

## 빠른 답변
- **“create project object java”가 의미하는 것은?** 메모리 상에 `Project` 인스턴스를 생성하여 프로그래밍 방식으로 조작할 수 있게 합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java (공식 사이트에서 다운로드).  
- **라이선스가 필요한가요?** 프로덕션 사용을 위해서는 임시 또는 정식 Aspose.Tasks 라이선스가 필요합니다; 무료 체험판을 사용할 수 있습니다.  
- **사용자 정의 필드를 사용할 수 있나요?** 예 – 작업에 **확장 속성**을 추가하여 사용자 정의 필드로 활용할 수 있습니다.  
- **모든 Project 파일 형식을 지원하나요?** Aspose.Tasks는 MPP, MPT, XML 형식을 지원합니다.

## 사전 준비
시작하기 전에 다음을 준비하세요:

1. **Java 개발 환경** – JDK 8 이상 및 IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
2. **Aspose.Tasks for Java 라이브러리** – [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하고 프로젝트에 포함합니다.

## 패키지 가져오기
프로젝트, 작업 및 확장 속성을 다루기 위해 Java 클래스에 Aspose.Tasks 네임스페이스를 추가합니다:

```java
import com.aspose.tasks.*;
```

## 프로젝트 보고서 생성 – Create Project Object Java
새 `Project` 객체를 인스턴스화합니다. 이 객체는 정의할 모든 작업, 리소스 및 사용자 정의 데이터를 담는 컨테이너 역할을 합니다.

```java
Project project = new Project();
```

위 코드는 **create project object java**를 수행하며, 비어 있는 상태에서 커스터마이징이 가능한 프로젝트 객체를 생성합니다.

## 확장 속성 추가 방법
각 작업에 저장할 사용자 정의 숫자 데이터(예: 사인값)를 보관할 확장 속성을 정의합니다.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

여기서는 `Number` 유형의 “Sine”이라는 이름을 가진 **확장 속성**을 추가하고 이를 작업에 연결합니다.

## 프로젝트에 확장 속성 등록
속성 정의를 프로젝트에 등록하여 모든 작업이 해당 속성을 참조할 수 있게 합니다.

```java
project.getExtendedAttributes().add(attr);
```

## 새 작업 만들기
프로젝트의 루트 작업 아래에 “Task”라는 간단한 작업을 추가합니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 작업에 확장 속성 연결
앞서 정의한 확장 속성을 새로 만든 작업에 연결합니다.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

이제 작업은 수식이나 계산에 사용할 수 있는 사용자 정의 “Sine” 필드를 보유하게 됩니다. 이것이 **add custom field task** 데이터를 프로그래밍 방식으로 추가하는 방법이기도 합니다.

## 평가 함수를 사용하는 이유
Aspose.Tasks 수식에 MS Project 함수를 삽입하면 다음과 같은 이점을 얻을 수 있습니다:

- 외부 도구 없이 **실시간 계산**(`Sin([Start])` 등) 수행.  
- 모든 프로젝트 로직을 하나의 유지보수 가능한 코드베이스에 집중.  
- 실시간 데이터 변화를 반영하는 동적 보고서를 생성하여 **프로젝트 보고서**를 자동으로 **생성**.

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|------|--------|
| **수식이 `NaN`을 반환** | 사용자 정의 필드 유형이 기대하는 숫자 유형과 일치하는지 확인합니다. |
| **확장 속성이 보이지 않음** | 작업을 생성하기 **전에** 속성 정의가 프로젝트에 추가되었는지 확인합니다. |
| **라이선스 예외 발생** | 임시 또는 정식 **Aspose.Tasks 라이선스**를 설치합니다; 체험 모드에서는 일부 기능이 제한될 수 있습니다. |
| **임시 라이선스 누락** | Aspose 웹사이트에서 **임시 Aspose 라이선스**를 받아 설치합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 복잡한 MS Project 수식을 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다양한 MS Project 함수를 평가할 수 있어 Java 애플리케이션 내에서 복잡한 계산을 수행할 수 있습니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 예, Aspose.Tasks for Java는 MPP, MPT, XML 등 여러 버전의 Microsoft Project 파일을 지원합니다.

**Q: 구매 전에 Aspose.Tasks for Java를 체험해볼 수 있나요?**  
A: 예, 웹사이트에서 무료 체험 버전을 [여기](https://purchase.aspose.com/buy) 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다 [여기](https://forum.aspose.com/c/tasks/15).

**Q: Aspose.Tasks for Java용 임시 라이선스가 제공되나요?**  
A: 예, 테스트 용도로 사용할 수 있는 임시 라이선스를 Aspose 웹사이트에서 [여기](https://purchase.aspose.com/temporary-license/) 받아 사용할 수 있습니다.

## 결론
이 절차를 따라 **프로젝트 객체를 생성**, **확장 속성을 추가**, 그리고 평가 함수를 활용해 **프로젝트 보고서를 자동으로 생성**하는 방법을 배웠습니다. 이제 이 기반 위에 더 풍부한 프로젝트 분석, 맞춤형 대시보드, 자동 일정 관리 도구 등을 구축할 수 있으며, 모두 Aspose.Tasks for Java가 지원합니다.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}