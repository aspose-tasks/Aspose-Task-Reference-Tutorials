---
title: Aspose.Tasks에서 MS 프로젝트 수식 작성 및 읽기
linktitle: Aspose.Tasks에서 수식 쓰기 및 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS Project 수식을 효율적으로 작성하고 읽는 방법을 알아보세요. 프로젝트 관리 기술을 향상시키세요.
weight: 12
url: /ko/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 수식 작성 및 읽기

## 소개
프로젝트 관리 영역에서는 데이터를 효과적으로 처리하는 것이 가장 중요합니다. Aspose.Tasks for Java는 Microsoft Project 파일에서 데이터 조작 및 추출을 용이하게 하는 강력한 솔루션입니다. 그것이 제공하는 강력한 기능 중 하나는 MS 프로젝트 수식을 작성하고 읽는 기능입니다. 이 튜토리얼에서는 이 기능을 활용하여 프로젝트 관리 작업을 향상시키는 프로세스를 안내합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): Java 개발을 위해 선호하는 IDE를 선택하세요.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 1단계: 데이터 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
```
이 단계에서는 MS 프로젝트 파일이 있는 디렉터리를 정의합니다.
## 2단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
여기에서 MS 프로젝트 파일을`Project` 조작 대상.
## 3단계: 사용자 정의 수식 정의
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
이 단계에는 작업 비용을 두 배로 늘리는 수식을 사용하여 사용자 정의 필드를 만드는 작업이 포함됩니다.
## 4단계: 작업 추가 및 비용 설정
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
여기에는 새로운 작업이 추가되고 비용은 100으로 설정됩니다.
## 5단계: 프로젝트 파일 저장
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
마지막으로 수정된 프로젝트 파일을 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS Project 수식을 작성하고 읽는 방법을 살펴보았습니다. 다음 단계를 수행하면 특정 요구 사항에 맞게 프로젝트 데이터를 효율적으로 조작할 수 있습니다.
## FAQ
### Aspose.Tasks는 모든 버전의 MS Project와 호환됩니까?
Aspose.Tasks는 다양한 버전의 MS Project와의 호환성을 제공하여 사용자의 유연성을 보장합니다.
### Aspose.Tasks를 기존 Java 프로젝트에 통합할 수 있나요?
전적으로! Aspose.Tasks는 간단한 API 사용을 통해 Java 프로젝트와의 원활한 통합을 제공합니다.
### 만들 수 있는 수식 유형에 제한이 있나요?
Aspose.Tasks를 사용하면 프로젝트 요구 사항에 맞는 사용자 정의 수식을 제작할 수 있는 광범위한 유연성을 얻을 수 있습니다.
### Aspose.Tasks는 다중 플랫폼 배포를 지원합니까?
예, Aspose.Tasks는 여러 플랫폼에 걸친 배포를 지원하여 다양성을 향상시킵니다.
### Aspose.Tasks에 대한 기술 지원은 어떻게 받을 수 있나요?
 기술 지원 및 커뮤니티 지원을 받으려면 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
