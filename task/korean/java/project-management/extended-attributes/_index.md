---
title: Aspose.Tasks 프로젝트에서 확장 속성 처리
linktitle: Aspose.Tasks 프로젝트에서 확장 속성 처리
second_title: Aspose.Tasks 자바 API
description: Java를 효율적으로 사용하여 Aspose.Tasks 프로젝트의 확장 속성을 처리하는 방법을 알아보세요. 효과적인 프로젝트 관리를 위한 단계별 가이드입니다.
type: docs
weight: 13
url: /ko/java/project-management/extended-attributes/
---
## 소개
프로젝트 관리에서 확장된 속성을 관리하는 것은 프로젝트 데이터를 사용자 정의하고 향상하는 데 중요합니다. Aspose.Tasks for Java는 MS 프로젝트 파일의 확장된 속성을 효율적으로 처리할 수 있는 강력한 도구를 제공합니다. 이 튜토리얼에서는 각 개념을 철저하게 이해할 수 있도록 프로세스를 단계별로 안내합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 프로그래밍에 대한 기본 지식.
2. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
3. Java 라이브러리용 Aspose.Tasks가 Java 프로젝트에 다운로드되어 설정되었습니다.
## 패키지 가져오기
먼저 시작하는 데 필요한 패키지를 가져오겠습니다.
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## 1단계: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```
 반드시 교체하세요`"Your Data Directory"` 프로젝트의 데이터 디렉터리 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 이 줄은 다음과 같은 프로젝트 파일을 로드합니다.`"project5.mpp"`.
## 3단계: 확장된 속성 정의에 액세스
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
여기서는 프로젝트에서 확장된 속성 정의 컬렉션을 검색합니다.
## 4단계: 확장된 속성 정의 생성
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 이 코드 세그먼트는 사용자 정의 필드 유형을 다음과 같이 지정하여 작업에 대한 확장된 속성 정의를 생성합니다.`Start` 속성 이름은 다음과 같습니다.`"Start 7"`.
## 5단계: 프로젝트에 정의 추가
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
새로 생성된 확장된 속성 정의를 프로젝트와 속성 정의 컬렉션 모두에 추가합니다.
## 6단계: 작업 및 확장된 속성에 액세스
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
여기서는 프로젝트 및 관련 확장 속성에서 작업을 검색합니다.
## 7단계: 확장된 속성 인스턴스 생성
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
이 단계에서는 이전에 정의된 속성 정의를 기반으로 확장된 속성의 인스턴스를 만듭니다.
## 8단계: 속성 값 설정
```java
Date date = new Date();
ea.setDateValue(date);
```
확장된 속성의 값(이 경우 날짜 값)을 설정합니다.
## 9단계: 태스크에 속성 추가
```java
eas.add(ea);
```
마지막으로 작업에 확장된 속성을 추가합니다.
## 10단계: 프로젝트 저장
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
이 줄은 확장된 속성이 추가된 수정된 프로젝트를 XML 파일에 저장합니다.
## 결론
이 튜토리얼에서는 Java를 사용하여 Aspose.Tasks 프로젝트에서 확장된 속성을 처리하는 방법을 배웠습니다. 다음 단계를 수행하면 사용자 정의 프로젝트 데이터를 효율적으로 관리하여 프로젝트 관리 기능을 향상시킬 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 Java, .NET 및 C를 포함한 여러 프로그래밍 언어를 지원합니다.++.
### Q: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
A: 예, Aspose.Tasks 웹사이트에서 무료 평가판을 다운로드할 수 있습니다.
### Q: 확장된 속성 유형을 사용자 정의할 수 있습니까?
A: 물론 Aspose.Tasks를 사용하면 프로젝트 요구 사항에 맞는 사용자 정의 확장 속성 유형을 정의할 수 있습니다.
### Q: Aspose.Tasks 문서에 어떻게 액세스할 수 있나요?
 A: Aspose.Tasks 웹사이트에서 포괄적인 문서를 찾을 수 있습니다.[선적 서류 비치](https://reference.aspose.com/tasks/java/).
### Q: Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
 A: 예, Aspose.Tasks 포럼을 통해 기술 지원에 액세스할 수 있습니다.[웹사이트](https://forum.aspose.com/c/tasks/15).