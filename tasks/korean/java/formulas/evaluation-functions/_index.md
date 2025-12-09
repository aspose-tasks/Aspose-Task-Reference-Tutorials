---
date: 2025-12-09
description: Java를 사용하여 프로젝트 객체를 생성하고 Aspose.Tasks 수식에서 평가 함수를 지원하는 방법을 배우세요. 작업에
  대한 확장 속성을 만드는 방법을 확인하세요.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 프로젝트 객체 생성 Java – Aspose.Tasks에서 평가 기능 지원
url: /ko/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 수식에서 지원 평가 함수

## 소개
Aspose.Tasks for Java를 사용하면 **create project object java** 인스턴스를 만들고 Microsoft Project 함수를 Java 코드 내부에서 직접 평가할 수 있습니다. 이러한 수식을 삽입하면 복잡한 계산을 실행하고, 맞춤형 보고서를 생성하며, 개발 환경을 떠나지 않고 프로젝트 분석을 자동화할 수 있습니다. 이 튜토리얼에서는 프로젝트 객체 설정부터 사용자 정의 데이터를 보유할 수 있는 확장 속성을 추가하는 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **“create project object java”가 무엇을 의미하나요?** 프로그램matically 조작할 수 있는 메모리 내 `Project` 인스턴스를 생성합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (공식 사이트에서 다운로드).  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다; 무료 체험판을 이용할 수 있습니다.  
- **사용자 정의 필드를 사용할 수 있나요?** 예 – 작업에 확장 속성을 정의하고 첨부할 수 있습니다.  
- **모든 Project 파일 형식과 호환되나요?** Aspose.Tasks는 MPP, MPT 및 XML 형식을 지원합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java 개발 환경** – JDK 8 이상 및 IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
2. **Aspose.Tasks for Java 라이브러리** – [Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하고 포함하십시오.

## 패키지 가져오기
프로젝트, 작업 및 확장 속성을 다룰 수 있도록 Java 클래스에 Aspose.Tasks 네임스페이스를 추가하십시오:

```java
import com.aspose.tasks.*;
```

## 단계 1: Create Project Object Java
새 `Project` 객체를 인스턴스화합니다. 이는 정의할 모든 작업, 리소스 및 사용자 정의 데이터의 컨테이너 역할을 합니다.

```java
Project project = new Project();
```

위 코드는 **creates project object java**를 생성하며, 비어 있고 사용자 정의 준비가 된 상태입니다.

## 단계 2: 확장 속성 만들기
각 작업에 대한 사용자 정의 숫자 데이터(예: 사인 값)를 저장할 확장 속성을 정의합니다.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

여기서는 `Number` 유형의 “Sine”이라는 이름으로 **create extended attribute**를 만들고 작업에 연결합니다.

## 단계 3: 프로젝트에 확장 속성 추가
모든 작업이 참조할 수 있도록 속성 정의를 프로젝트에 등록합니다.

```java
project.getExtendedAttributes().add(attr);
```

## 단계 4: 새 작업 만들기
프로젝트의 루트 작업 아래에 “Task”라는 간단한 작업을 추가합니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 단계 5: 작업에 확장 속성 연결
이전에 정의한 확장 속성을 새로 만든 작업에 연결합니다.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

이제 작업은 수식이나 계산에 사용할 수 있는 사용자 정의 “Sine” 필드를 보유합니다.

## 평가 함수를 사용하는 이유
Aspose.Tasks 수식에 MS Project 함수를 삽입하면 다음을 수행할 수 있습니다:

- 외부 도구 없이 실시간 계산을 수행합니다(예: `Sin([Start])`).  
- 모든 프로젝트 로직을 단일하고 유지 관리 가능한 코드베이스에 보관합니다.  
- 실시간 데이터 변경을 반영하는 동적 보고서를 생성합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **Formula returns `NaN`** | 사용자 정의 필드 유형이 예상되는 숫자 유형과 일치하는지 확인하십시오. |
| **Extended attribute not visible** | 속성 정의가 작업을 생성하기 **전**에 프로젝트에 추가되었는지 확인하십시오. |
| **License exception** | 임시 또는 정식 라이선스를 설치하십시오; 체험 모드에서는 일부 기능이 제한될 수 있습니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 복잡한 MS Project 수식을 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다양한 MS Project 함수를 평가하는 것을 지원하므로 Java 애플리케이션 내에서 복잡한 계산을 수행할 수 있습니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 예, Aspose.Tasks for Java는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.

**Q: 구매 전에 Aspose.Tasks for Java를 체험해볼 수 있나요?**  
A: 예, 웹사이트 [here](https://purchase.aspose.com/buy)에서 Aspose.Tasks for Java 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원을 어떻게 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼 [here](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

**Q: Aspose.Tasks for Java용 임시 라이선스가 있나요?**  
A: 예, 테스트 용도로 Aspose 웹사이트 [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 얻을 수 있습니다.

---

**마지막 업데이트:** 2025-12-09  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}