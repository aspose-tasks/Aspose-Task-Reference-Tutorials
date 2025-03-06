---
title: Aspose.Tasks에서 MS 프로젝트 데이터를 Excel에 저장
linktitle: Aspose.Tasks에서 Excel에 데이터 저장
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 데이터를 Excel 파일에 저장하는 방법을 알아보세요. Java 개발자를 위한 손쉬운 통합.
weight: 19
url: /ko/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 데이터를 Excel에 저장

## 소개
Aspose.Tasks for Java는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 프로젝트 파일의 데이터를 Excel 파일로 저장하는 과정을 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 버전의 JDK를 다운로드하여 설치할 수 있습니다.
2.  Java 라이브러리용 Aspose.Tasks: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/) 그리고 이를 Java 프로젝트에 포함시킵니다.

## 패키지 가져오기
먼저 Aspose.Tasks를 사용하려면 Java 코드에 필요한 패키지를 가져와야 합니다.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 데이터 디렉터리 경로 정의
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"`프로젝트 파일이 있는 데이터 디렉터리의 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project5.mpp");
```
이 코드 줄은 지정된 데이터 디렉터리에서 "project5.mpp"라는 프로젝트 파일을 로드합니다.
## 3단계: 프로젝트를 XLSX로 저장
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 여기서는`save` 메소드는 로드된 프로젝트 파일을 동일한 데이터 디렉토리에 "project1.xlsx"라는 이름의 Excel 파일로 저장하는 데 사용됩니다. 우리는`SaveFileFormat.Xlsx` 매개변수를 사용하여 XLSX 형식으로 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일의 데이터를 Excel 파일로 저장하는 방법을 배웠습니다. 제공된 단계를 따르면 이 기능을 Java 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### Aspose.Tasks for Java를 사용하여 프로그래밍 방식으로 프로젝트 데이터를 조작할 수 있나요?
예, Aspose.Tasks for Java는 프로젝트 파일 읽기, 쓰기, 수정을 포함하여 프로젝트 데이터를 조작하는 광범위한 기능을 제공합니다.
### Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 예, 다음에서 Aspose.Tasks for Java의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?
Aspose.Tasks for Java에 대한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks for Java와 관련된 문제나 쿼리에 대한 지원을 어떻게 받을 수 있나요?
 Aspose.Tasks 포럼을 방문하여 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
