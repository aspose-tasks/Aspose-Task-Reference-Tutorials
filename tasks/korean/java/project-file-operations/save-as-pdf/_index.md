---
title: Aspose.Tasks에 PDF로 저장
linktitle: Aspose.Tasks에 PDF로 저장
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 프로젝트 파일을 PDF로 변환하는 방법을 알아보세요. 효율적인 변환을 위한 간단한 단계.
weight: 17
url: /ko/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 PDF로 저장

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하는 과정을 안내합니다. Aspose.Tasks를 사용하면 프로젝트 파일을 PDF 형식으로 효율적으로 변환하여 호환성과 공유 용이성을 보장할 수 있습니다. 다음 단계를 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java 라이브러리용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하고 설치합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
3. 프로젝트 파일: PDF로 변환할 프로젝트 파일(예: HomeMovePlan.mpp)을 준비합니다.

## 패키지 가져오기
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## 1단계: 입력 프로젝트 파일 읽기
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 반드시 교체하세요`"Your Data Directory"` 프로젝트 파일이 포함된 데이터 디렉터리의 경로를 사용하세요.
## 2단계: 프로젝트를 PDF로 저장
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
이 코드 조각은 프로젝트를 "Project5.pdf"라는 이름의 PDF 파일로 저장합니다.
## 3단계: 셀 크기에 내용 맞추기
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
여기에서는 내용 맞추기, 시간 척도 및 프레젠테이션 형식을 포함하여 PDF 저장에 대한 옵션을 설정합니다.
## 4단계: 범례 숨기기
```java
o.setLegendOnEachPage(false);
```
이 단계에서는 PDF의 각 페이지에 있는 범례를 숨깁니다.
## 5단계: 적용된 옵션으로 프로젝트 저장
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
마지막으로 이 코드는 옵션이 적용된 프로젝트를 PDF 파일로 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하는 방법을 배웠습니다. 이러한 간단한 단계를 따르면 프로젝트 파일을 효율적으로 변환하여 쉽게 공유하고 배포할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 모든 Java 버전과 호환됩니까?
A: 예, Aspose.Tasks는 JDK 6 이상부터 Java 버전을 지원합니다.
### Q: PDF 출력의 모양을 사용자 정의할 수 있습니까?
답: 물론이죠! Aspose.Tasks는 요구 사항에 따라 PDF 출력을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### Q: Aspose.Tasks는 변환을 위해 다른 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 MPP, XML, XLSX 등을 포함한 광범위한 파일 형식을 지원합니다.
### Q: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?
 A: 예, Aspose.Tasks의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 답변: 지원 및 도움이 필요한 경우 다음 사이트를 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
