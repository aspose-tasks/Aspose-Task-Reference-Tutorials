---
date: 2025-12-17
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 내보내고, 바닥글 간격을 줄이며, 프로젝트를 이미지로
  저장하는 방법을 배워보세요. MS Project 레이아웃을 손쉽게 최적화하세요.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 프로젝트를 PDF로 내보내고 작업 목록과 바닥글 사이의 간격 줄이기
url: /ko/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 PDF로 내보내고 Aspose.Tasks에서 작업 목록과 바닥글 사이의 간격 줄이기

## 소개  
이 튜토리얼에서는 **프로젝트를 PDF로 내보내는 방법**을 배우면서 Microsoft Project 파일에서 작업 목록과 바닥글 사이의 원치 않는 공간을 줄이는 방법도 알아봅니다. 가이드가 끝날 때쯤이면 Aspose.Tasks for Java를 사용하여 깔끔한 PDF, PNG 이미지 및 HTML 페이지를 컴팩트한 레이아웃으로 생성할 수 있게 됩니다. 단계별로 진행해 보겠습니다.

## 빠른 답변  
- **“export project to PDF”가 무엇을 의미하나요?** MPP 파일을 작업, 일정 및 서식을 보존한 채 PDF 문서로 변환합니다.  
- **왜 바닥글 간격을 줄여야 하나요?** 간격을 줄이면 특히 인쇄물이나 웹에서 보는 문서가 더 촘촘하고 전문적인 보고서가 됩니다.  
- **프로젝트를 이미지로 저장할 수 있나요?** 예 – Aspose.Tasks는 PNG, JPEG 및 기타 이미지 형식을 지원합니다.  
- **특별한 라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 상용 사용을 위해서는 상업용 라이선스가 필요합니다.  
- **필요한 Java 버전은 무엇인가요?** 현재 Aspose.Tasks 라이브러리는 Java 8 이상에서 작동합니다.

## “export project to PDF”란 무엇인가요?  
프로젝트를 PDF로 내보내면 내부 MPP 구조가 휴대용 문서로 변환되어 Microsoft Project 없이도 모든 장치에서 열 수 있습니다. 이는 상태 보고서, 이해관계자 업데이트 또는 프로젝트 계획을 보관하는 데 이상적입니다.

## 왜 바닥글 간격을 줄여야 할까요?  
기본 바닥글 간격은 불필요한 여백을 추가하여 페이지 나눔 문제와 균형 잡히지 않은 외관을 초래할 수 있습니다. 간격을 줄이면 콘텐츠가 페이지를 효율적으로 활용하게 되어 최종 PDF 또는 이미지가 더 읽기 쉬워집니다.

## 작업 목록과 바닥글 사이의 간격을 줄이는 방법은?  
Aspose.Tasks는 이미지, PDF 및 HTML 저장 작업에 대해 `setReduceFooterGap(true)` 옵션을 제공합니다. 이 플래그를 활성화하면 엔진이 마지막 작업 행과 페이지 바닥글 사이의 공간을 압축하도록 지시합니다.

## Aspose.Tasks로 프로젝트를 이미지로 저장하기  
일정의 시각적 스냅샷이 필요하다면 동일한 간격 감소 설정을 적용하여 **프로젝트를 이미지(PNG)로 저장**할 수 있습니다.

## Java 프로젝트 PDF 내보내기  
다음 섹션에서는 MPP 파일을 로드하고 세 가지 다른 형식으로 저장하는 전체 **java 프로젝트 내보내기** 워크플로우를 단계별로 안내합니다.

## 전제 조건
시작하기 전에 다음 전제 조건을 확인하십시오:
1. Java Development Kit (JDK) – 버전 8 이상.  
2. Aspose.Tasks for Java Library – [here](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.

## 패키지 가져오기  
코딩 부분에 들어가기 전에 필요한 패키지를 가져오겠습니다:
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

## 단계 1: 데이터 디렉터리 경로 제공
```java
String dataDir = "Your Data Directory";
```
예제에서 `HomeMovePlan.mpp` 파일이 위치한 실제 데이터 디렉터리 경로로 `"Your Data Directory"`를 교체하십시오.

## 단계 2: MPP 파일 읽기
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
이 코드는 `HomeMovePlan.mpp`라는 Microsoft Project 파일을 읽습니다.

## 단계 3: ImageSaveOptions 설정 (프로젝트를 이미지로 저장)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
`ReduceFooterGap`을 `true`로 설정하여 작업 목록과 바닥글 사이의 간격을 줄이는 이미지 저장 옵션을 구성합니다.

## 단계 4: 이미지로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
구성된 옵션으로 프로젝트를 이미지로 저장합니다.

## 단계 5: PdfSaveOptions 설정 (프로젝트를 PDF로 내보내기)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
`ReduceFooterGap`을 `true`로 설정하여 PDF 저장 옵션을 정의합니다.

## 단계 6: PDF로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
구성된 옵션으로 프로젝트를 PDF로 저장합니다.

## 단계 7: HtmlSaveOptions 설정
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
`ReduceFooterGap`을 `true`로 설정하여 HTML 저장 옵션을 지정합니다.

## 단계 8: HTML로 저장
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
구성된 옵션으로 프로젝트를 HTML 파일로 저장합니다.

## 결론  
결론적으로, Microsoft Project 파일에서 작업 목록과 바닥글 사이의 간격을 줄이는 것은 Aspose.Tasks for Java를 사용하면 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따르면 **프로젝트를 PDF로 내보내기**, 이미지로 저장하거나 HTML을 생성하면서 레이아웃을 촘촘하고 전문적으로 유지할 수 있습니다.

## FAQ

### Q: Aspose.Tasks가 모든 버전의 Microsoft Project와 호환되나요?
A: Aspose.Tasks는 Microsoft Project 2003-2019 형식을 지원하므로 다양한 버전과 호환됩니다.

### Q: 프로젝트 문서의 바닥글 모양을 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks는 간격 감소 및 콘텐츠 배치 조정을 포함하여 바닥글 모양을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.

### Q: Aspose.Tasks가 PNG, PDF, HTML 외의 형식으로 저장을 지원하나요?
A: 예, Aspose.Tasks는 XLSX, XML, MPP 등 다양한 형식을 지원합니다.

### Q: Aspose.Tasks의 체험판이 있나요?
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험판을 다운로드할 수 있습니다.

### Q: Aspose.Tasks 사용 중 문제가 발생하면 어디서 지원을 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼 [here](https://forum.aspose.com/c/tasks/15)에서 도움을 받을 수 있습니다.

## 자주 묻는 질문 (추가)

**Q: 바닥글 간격을 줄이면 페이지 매김에 어떤 영향을 미치나요?**  
A: 각 페이지 하단의 빈 공간을 최소화하여 한 페이지에 더 많은 작업을 배치하고 전체 페이지 수를 줄입니다.

**Q: 동일한 간격 감소 설정을 단일 페이지에만 적용할 수 있나요?**  
A: 예, `ImageSaveOptions`에서 `setRenderToSinglePage(true)`를 설정하면 페이지 매김을 제어하면서도 간격을 줄일 수 있습니다.

**Q: `setReduceFooterGap` 옵션이 다른 출력 형식에서도 사용 가능한가요?**  
A: 현재는 PNG, PDF, HTML 내보내기에서 지원됩니다. 다른 형식의 경우 레이아웃을 수동으로 조정해야 할 수 있습니다.

**Q: 프로젝트에 사용자 정의 필드가 포함되어 있으면 어떻게 되나요—보존되나요?**  
A: 모든 사용자 정의 필드는 내보내기 시 그대로 유지됩니다; 레이아웃 조정은 데이터가 아닌 간격에만 영향을 줍니다.

**Q: 라이브러리가 대형 프로젝트를 효율적으로 처리하나요?**  
A: Aspose.Tasks는 데이터를 스트리밍하여 대용량 MPP 파일을 처리할 수 있지만, 고해상도 이미지로 내보낼 때는 충분한 메모리를 확보하십시오.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}