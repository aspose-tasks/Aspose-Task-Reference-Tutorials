---
title: Aspose.Tasks의 확장된 작업 속성
linktitle: Aspose.Tasks의 확장된 작업 속성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java에서 확장된 작업 속성을 살펴보세요. 단계별 가이드, FAQ 및 지원. 지금 프로젝트 관리를 최적화하세요!
weight: 16
url: /ko/java/task-properties/extended-task-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 확장된 작업 속성

## 소개
Aspose.Tasks for Java에서 확장된 작업 속성을 활용하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다. Aspose.Tasks는 Microsoft Project 문서를 원활하게 사용할 수 있게 해주는 강력한 Java 라이브러리입니다. 이 튜토리얼에서는 확장된 작업 속성을 자세히 살펴보고 이를 활용하여 프로젝트 관리 기능을 향상시키는 방법을 보여줍니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 컴퓨터에 JDK(Java Development Kit)를 설치했습니다.
- IntelliJ 또는 Eclipse와 같은 통합 개발 환경(IDE).
## 패키지 가져오기
Aspose.Tasks 프로젝트를 시작하는 데 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
이제 프로세스를 안내하기 위해 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 태스크 및 확장 속성 액세스
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## 2단계: 필드 ID 및 값 GUID 검색
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## 3단계: 다양한 속성 유형 처리
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
확장된 작업 속성을 탐색하고 조작하려면 프로젝트의 각 작업에 대해 이러한 단계를 반복하세요.
## 결론
결론적으로 Aspose.Tasks for Java의 확장된 작업 속성을 이해하고 활용하면 프로젝트 관리 기능이 크게 향상될 수 있습니다. 이 가이드는 이 여정을 시작하는 데 견고한 기반을 제공합니다.
## 자주 묻는 질문
### 확장된 작업 속성을 프로그래밍 방식으로 수정할 수 있나요?
예, Aspose.Tasks for Java를 사용하여 확장 작업 속성을 수정할 수 있습니다. 자세한 지침은 설명서를 참조하세요.
### 평가판을 사용할 수 있나요?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 지원을 받으려면 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### 임시 라이센스는 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Tasks 정식 버전은 어디에서 구입할 수 있나요?
 정식 버전을 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
