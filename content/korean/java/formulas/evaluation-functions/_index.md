---
title: Aspose.Tasks 수식에서 평가 기능 지원
linktitle: Aspose.Tasks 수식에서 평가 기능 지원
second_title: Aspose.Tasks 자바 API
description: Java를 사용하여 Aspose.Tasks 수식에서 MS Project 함수 평가를 지원하는 방법을 알아보세요. Aspose.Tasks로 생산성을 높이세요.
type: docs
weight: 10
url: /ko/java/formulas/evaluation-functions/
---

## 소개
Aspose.Tasks for Java는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 주요 기능 중 하나는 Aspose.Tasks 공식 내에서 MS 프로젝트 기능 평가를 지원하는 기능입니다. 이 기능을 통해 사용자는 Java 애플리케이션 내에서 직접 복잡한 계산 및 분석을 수행할 수 있습니다.
## 전제조건
MS 프로젝트 기능을 Aspose.Tasks 수식에 통합하기 전에 다음 사항이 있는지 확인하세요.
1. Java 개발 환경: IntelliJ IDEA 또는 Eclipse와 같은 Java 개발용 호환 IDE와 함께 시스템에 Java가 설치되어 있는지 확인하십시오.
2.  Java 라이브러리용 Aspose.Tasks: Java 프로젝트에 Aspose.Tasks for Java 라이브러리를 다운로드하고 포함합니다. 다음에서 다운로드할 수 있습니다.[Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
시작하려면 Aspose.Tasks 기능을 활용하기 위해 Java 클래스에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
```

## 1단계: 새 프로젝트 개체 만들기
 먼저 새 항목을 만듭니다.`Project`작업할 객체:
```java
Project project = new Project();
```
그러면 새로운 빈 프로젝트가 초기화됩니다.
## 2단계: 작업에 대한 확장된 속성 정의
다음으로 작업에 대한 확장된 속성을 정의합니다. 이 속성은 작업과 관련된 사용자 정의 데이터를 보유합니다.
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 여기서는 유형의 확장 속성을 생성합니다.`Number` 작업의 경우 이름이 "Sine"입니다.
## 3단계: 프로젝트에 확장 특성 추가
프로젝트의 확장된 속성 목록에 확장된 속성 정의를 추가합니다.
```java
project.getExtendedAttributes().add(attr);
```
그러면 프로젝트에 사용자 정의 속성이 추가됩니다.
## 4단계: 새 작업 만들기
이제 프로젝트 내에 새 작업을 만들어 보겠습니다.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
그러면 프로젝트에 "Task"라는 새 작업이 추가됩니다.
## 5단계: 확장된 특성을 작업과 연결
이전에 생성한 확장 속성을 작업과 연결합니다.
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
이는 "사인" 확장 속성을 작업과 연결합니다.

## 결론
결론적으로 MS Project 함수를 Java의 Aspose.Tasks 수식에 통합하는 것은 간단한 프로세스입니다. 제공된 단계를 따르면 Aspose.Tasks for Java의 강력한 기능을 효과적으로 활용하여 프로그래밍 방식으로 Microsoft Project 파일을 조작하고 분석할 수 있습니다.
## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 MS 프로젝트 수식을 처리할 수 있습니까?
A: 예, Aspose.Tasks for Java는 광범위한 MS 프로젝트 기능 평가를 지원하므로 Java 애플리케이션 내에서 복잡한 계산이 가능합니다.
### Q: Aspose.Tasks for Java는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 예, Aspose.Tasks for Java는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: 구매하기 전에 Java용 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 예, 웹사이트에서 Aspose.Tasks for Java의 무료 평가판을 다운로드할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### Q: Java용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks for Java에 사용할 수 있는 임시 라이선스가 있나요?
 A: 예, Aspose 웹사이트에서 테스트 목적으로 임시 라이선스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).