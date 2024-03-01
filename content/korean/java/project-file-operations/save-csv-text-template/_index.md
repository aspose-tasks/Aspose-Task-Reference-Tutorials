---
title: Aspose.Tasks에 CSV, 텍스트 및 템플릿으로 저장
linktitle: Aspose.Tasks에 CSV, 텍스트 및 템플릿으로 저장
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 CSV, 텍스트 및 템플릿 형식으로 저장하는 방법을 알아보세요.
type: docs
weight: 16
url: /ko/java/project-file-operations/save-csv-text-template/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 CSV, 텍스트, 템플릿과 같은 다양한 형식으로 프로젝트 파일을 저장하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치할 필요 없이 Microsoft Project 파일로 작업할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 프로젝트에 다운로드 및 구성된 Java 라이브러리용 Aspose.Tasks입니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍 언어에 대한 기본 지식.

## 패키지 가져오기
먼저 Java 파일에 필요한 패키지를 가져와야 합니다.
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## 프로젝트를 CSV로 저장
프로젝트를 CSV로 저장하는 단계를 자세히 살펴보겠습니다.
### 1단계: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2단계: CSV로 저장
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## 프로젝트를 텍스트로 저장
프로젝트를 텍스트로 저장하는 방법은 다음과 같습니다.
### 1단계: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2단계: 텍스트로 저장
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## 프로젝트를 템플릿으로 저장
프로젝트를 템플릿으로 저장하는 단계는 다음과 같습니다.
### 1단계: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2단계: 템플릿 옵션 설정
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### 3단계: 템플릿으로 저장
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 CSV, 텍스트 및 템플릿으로 저장하는 방법을 배웠습니다. 이러한 간단한 단계를 통해 다양한 형식의 프로젝트 파일을 효율적으로 관리하여 Java 개발자로서 생산성을 높일 수 있습니다.
## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 프로젝트 파일을 처리할 수 있나요?
답: 물론이죠! Aspose.Tasks for Java는 Microsoft Project 파일 형식에 대한 포괄적인 지원을 제공하여 다양한 복잡성의 프로젝트를 쉽게 처리할 수 있습니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 Aspose.Tasks for Java의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for Java에 관한 지원이나 문의 사항이 있는 경우
### Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
 A: 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/), 라이브러리의 전체 잠재력을 평가할 수 있습니다.
### Q: Aspose.Tasks for Java는 다른 운영 체제와 호환됩니까?
A: 예, Aspose.Tasks for Java는 Windows, macOS, Linux를 포함한 다양한 운영 체제와 호환됩니다.