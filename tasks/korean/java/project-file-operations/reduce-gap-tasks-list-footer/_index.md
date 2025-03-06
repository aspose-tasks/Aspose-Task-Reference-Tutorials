---
title: Aspose.Tasks에서 작업 목록과 바닥글 사이의 간격 줄이기
linktitle: Aspose.Tasks에서 작업 목록과 바닥글 사이의 간격 줄이기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 작업 목록과 바닥글 사이의 간격을 줄이는 방법을 알아보세요. 프로젝트 문서 레이아웃을 손쉽게 최적화하세요.
weight: 10
url: /ko/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 목록과 바닥글 사이의 간격 줄이기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 작업 목록과 바닥글 사이의 간격을 줄이는 방법을 살펴보겠습니다. 다음 단계를 따르면 프로젝트 문서의 레이아웃을 쉽게 최적화할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks for Java 라이브러리: 프로젝트에 Aspose.Tasks for Java 라이브러리를 다운로드하고 포함합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
코딩 부분을 살펴보기 전에 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 1단계: 데이터 디렉터리 경로 제공
```java
String dataDir = "Your Data Directory";
```
 꼭 교체하세요`"Your Data Directory"` Microsoft Project 파일(`HomeMovePlan.mpp` 이 예에서는)이 있습니다.
## 2단계: MPP 파일 읽기
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 이 코드 줄은 다음과 같은 Microsoft Project 파일을 읽습니다.`HomeMovePlan.mpp`.
## 3단계: ImageSaveOptions 설정
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 이미지 저장 옵션 구성, 설정`ReduceFooterGap` 에게`true` 작업 목록과 바닥글 사이의 간격을 줄입니다.
## 4단계: 이미지로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
구성된 옵션을 사용하여 프로젝트를 이미지로 저장합니다.
## 5단계: PdfSaveOptions 설정
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 PDF 저장 옵션을 정의하고 설정을 확인하세요.`ReduceFooterGap` 에게`true`.
## 6단계: PDF로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
구성된 옵션을 사용하여 프로젝트를 PDF로 저장합니다.
## 7단계: HtmlSaveOptions 설정
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // 사실로 설정
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 HTML 저장 옵션 지정, 설정`ReduceFooterGap` 에게`true`.
## 8단계: HTML로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
구성된 옵션을 사용하여 프로젝트를 HTML 파일로 저장합니다.

## 결론
결론적으로, Microsoft Project 파일에서 작업 목록과 바닥글 사이의 간격을 줄이는 것은 Aspose.Tasks for Java를 사용하는 간단한 프로세스입니다. 이 튜토리얼에 설명된 단계를 따르면 프로젝트 문서의 레이아웃을 효율적으로 최적화할 수 있습니다.

## FAQ

### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?

A: Aspose.Tasks는 Microsoft Project 2003-2019 형식을 지원하여 다양한 버전 간의 호환성을 보장합니다.

### Q: 내 프로젝트 문서의 바닥글 모양을 사용자 정의할 수 있나요?

A: 예, Aspose.Tasks는 간격 줄이기 및 콘텐츠 배치 조정을 포함하여 바닥글 모양을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.

### Q: Aspose.Tasks는 PNG, PDF, HTML 이외의 형식으로 프로젝트 저장을 지원합니까?

A: 예, Aspose.Tasks는 XLSX, XML, MPP 등 다양한 형식을 지원합니다.

### Q: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?

 A: 예, Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Q: Aspose.Tasks를 사용하는 동안 문제가 발생하면 어디서 지원을 받을 수 있나요?

 A: Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
