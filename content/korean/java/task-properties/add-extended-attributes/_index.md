---
title: Aspose.Tasks의 작업에 확장 속성 추가
linktitle: Aspose.Tasks의 작업에 확장 속성 추가
second_title: Aspose.Tasks 자바 API
description: 확장된 속성으로 Microsoft Project 파일을 사용자 정의할 때 Aspose.Tasks Java의 강력한 기능을 살펴보세요. 프로젝트 관리 능력을 손쉽게 향상시키세요.
type: docs
weight: 11
url: /ko/java/task-properties/add-extended-attributes/
---
## 소개
효율적인 작업 추적 및 자원 관리를 위해서는 프로젝트 관리 기능을 향상시키는 것이 중요합니다. Aspose.Tasks for Java는 Java 개발자가 Microsoft Project 파일을 원활하게 조작할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업에 확장된 속성을 추가하여 특정 요구 사항에 따라 프로젝트 데이터를 사용자 정의하고 구성하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
- Java 프로그래밍에 대한 기본 지식.
-  Aspose.Tasks for Java 라이브러리가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/java/).
- 시스템에 설치된 Java IDE(통합 개발 환경).
## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 패키지를 가져옵니다.
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
이제 각 예를 여러 단계로 나누어 보겠습니다.
## 1. 일반 텍스트 속성 추가
1. 문서 디렉터리 경로를 설정합니다.
```java
String dataDir = "Your Document Directory";
```
2. 새 프로젝트를 만듭니다.
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Text1 유형의 확장된 속성 정의를 생성합니다.
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. 프로젝트의 확장 속성 컬렉션에 정의를 추가합니다.
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. 프로젝트에 작업을 추가합니다.
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. 속성 정의에서 확장된 속성을 생성합니다.
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. 생성된 확장 속성에 값을 할당합니다.
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. 작업에 확장 속성을 추가합니다.
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. 프로젝트를 저장합니다.
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. 조회 옵션으로 텍스트 속성 추가
위와 동일한 단계를 수행하여 Text1을 Text2로 바꾸고 조회 값을 사용자 정의합니다.
## 3. 조회 옵션으로 기간 속성 추가
위와 동일한 단계를 수행하여 Text1을 Duration2로 바꾸고 조회 값을 사용자 정의합니다.
## 결론
이 단계별 가이드를 따라 Aspose.Tasks for Java를 활용하여 Microsoft Project 파일의 작업에 확장 속성을 추가하는 방법을 배웠습니다. 이러한 사용자 정의를 통해 프로젝트 관리 접근 방식을 맞춤화하여 유연성과 효율성을 높일 수 있습니다.
## 자주 묻는 질문
### Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 Java 프로젝트에 완벽하게 통합될 수 있으며 다른 Java 라이브러리와도 잘 작동합니다.
### Q: Aspose.Tasks for Java는 대규모 프로젝트 관리 애플리케이션에 적합합니까?
A: 물론 Aspose.Tasks for Java는 대규모 애플리케이션을 포함하여 다양한 규모의 프로젝트를 처리하도록 설계되었습니다.
### Q: 상용 프로젝트에서 Aspose.Tasks for Java를 사용할 때 라이선스 고려 사항이 있나요?
 A: 예.[Aspose.Tasks 웹사이트](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks for Java에 대한 지원을 받으려면 어떻게 해야 합니까?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.
### Q: 구매하기 전에 Java용 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).