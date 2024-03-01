---
title: Aspose.Tasks 프로젝트에서 간트 차트 보기 구성
linktitle: Aspose.Tasks 프로젝트에서 간트 차트 보기 구성
second_title: Aspose.Tasks 자바 API
description: Java를 사용하여 Aspose.Tasks에서 Gantt MS 프로젝트 차트 보기를 구성하는 방법을 알아보세요. 프로젝트를 사용자 정의하고 단계별로 Gantt 차트에서 시각화하세요.
type: docs
weight: 10
url: /ko/java/project-configuration/configure-gantt-chart/
---
## 소개
이 튜토리얼에서는 Java를 사용하여 Aspose.Tasks 프로젝트에서 Gantt MS 프로젝트 차트 보기를 구성하는 방법을 배웁니다. Aspose.Tasks는 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있는 강력한 Java API입니다. 다음 단계를 수행하면 프로젝트 요구 사항에 따라 Gantt 차트 보기를 사용자 정의할 수 있습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks 라이브러리: Aspose.Tasks 라이브러리를 다운로드하고 설치합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): 원하는 IDE를 선택하세요. 이 튜토리얼에서는 IntelliJ IDEA를 사용하지만 자신에게 편한 IDE를 사용해도 됩니다.
## 패키지 가져오기
먼저 Java 프로젝트에서 Aspose.Tasks를 사용하는 데 필요한 패키지를 가져와야 합니다. Java 파일에 다음 가져오기 문을 추가합니다.
```java
import com.aspose.tasks.*;
```
이제 Gantt MS 프로젝트 차트 보기를 구성하는 과정을 단계별 지침으로 나누어 보겠습니다.
## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 데이터 디렉터리 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
프로젝트 파일을 로드합니다(`project.mpp` 이 예에서는)`Project` Aspose.Tasks의 클래스입니다.
## 3단계: 새 활동 추가
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 다음을 사용하여 프로젝트에 새 작업을 만듭니다.`Task` 클래스를 만들어 루트 작업의 하위 항목에 추가합니다.
## 4단계: 사용자 정의 속성 정의
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 다음을 사용하여 새 사용자 정의 속성을 정의합니다.`ExtendedAttributeDefinition`클래스를 프로젝트의 확장 속성에 추가합니다.
## 5단계: 작업에 사용자 정의 속성 추가
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 다음을 사용하여 생성된 작업에 사용자 정의 속성을 추가합니다.`createExtendedAttribute` 방법.
## 6단계: 표 사용자 정의
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
지정된 너비, 제목 및 정렬이 있는 텍스트 속성 필드를 추가하여 테이블을 사용자 정의합니다.
## 7단계: 프로젝트 저장
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
구성된 Gantt MS 프로젝트 차트 보기로 프로젝트를 저장합니다. 결과 파일은 Microsoft Project 2010에서 열 수 있습니다.
## 결론
축하해요! Java를 사용하여 Aspose.Tasks 프로젝트에서 Gantt MS 프로젝트 차트 보기를 성공적으로 구성했습니다. 이제 프로젝트 특성을 사용자 정의하고 프로젝트 요구 사항에 따라 Gantt 차트에서 시각화할 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 .NET, Java 및 C를 포함한 여러 프로그래밍 언어에서 사용할 수 있습니다.++.
### Q: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
A: 다음 사이트에서 지원을 찾고 질문할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks 라이선스를 어떻게 구매할 수 있나요?
 A: 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### Q: 테스트 목적으로 임시 라이센스가 필요합니까?
 A: 예, 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).