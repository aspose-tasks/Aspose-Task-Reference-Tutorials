---
title: Java용 Aspose.Tasks를 사용한 MS 프로젝트 수식
linktitle: Aspose.Tasks에서 수식 작업
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks 라이브러리를 사용하여 Java에서 MS 프로젝트 파일을 조작하는 방법을 알아보세요. 속성을 쉽게 생성, 수정, 계산할 수 있습니다.
weight: 11
url: /ko/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java용 Aspose.Tasks를 사용한 MS 프로젝트 수식

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 수식 작업을 자세히 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 광범위한 기능을 사용하면 Java 애플리케이션에서 프로젝트 파일을 쉽게 생성, 읽기, 수정 및 변환할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### 자바 개발 환경
시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 JDK를 다운로드하여 설치할 수 있습니다.
### Aspose.Tasks 라이브러리
Java 프로젝트에 Aspose.Tasks 라이브러리를 추가해야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose.Tasks for Java 다운로드 페이지](https://releases.aspose.com/tasks/java/) 프로젝트의 종속성에 포함시킵니다.

## 패키지 가져오기
예제를 살펴보기 전에 필요한 패키지를 Java 코드로 가져옵니다.
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 사용자 정의 필드를 사용하여 테스트 프로젝트 만들기
```java
Project project = CreateTestProjectWithCustomField();
```
 먼저 다음을 사용하여 사용자 정의 필드가 있는 테스트 프로젝트를 만듭니다.`CreateTestProjectWithCustomField()` 방법. 이 메서드는 새로 생성된 프로젝트를 나타내는 Project 개체를 반환합니다.
## 2단계: 확장된 속성 정의 정의
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
프로젝트에서 확장된 속성 정의를 검색하고 해당 별칭과 수식을 설정합니다. 이 예에서는 완료 날짜부터 마감일까지의 일수를 계산하는 속성을 정의합니다.
## 3단계: 작업 마감일 설정
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Calendar 개체를 만들고 마감일을 설정합니다. 그런 다음 프로젝트에서 작업을 검색하고 Calendar 개체를 사용하여 마감일을 설정합니다.
## 4단계: 프로젝트 저장
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
마지막으로 프로젝트를 지정된 이름과 형식의 파일로 저장합니다. 이 경우 MPP 파일로 저장하겠습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 수식으로 작업하는 방법을 배웠습니다. 다음 단계를 따르면 사용자 정의 필드를 추가하고 수식을 기반으로 속성을 계산하여 프로젝트 파일을 프로그래밍 방식으로 효과적으로 조작할 수 있습니다.

## FAQ
### Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 Java, .NET 등을 포함한 다양한 프로그래밍 언어를 지원합니다.
### Q: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?
 A: Aspose.Tasks에 대한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/java/).
### Q: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
 A: 지원을 받으려면 다음 사이트를 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks를 사용하려면 임시 라이선스가 필요합니까?
A: 추가 기능이 필요한 경우 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
