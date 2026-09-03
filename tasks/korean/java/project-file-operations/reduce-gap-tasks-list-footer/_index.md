---
date: 2026-05-20
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 내보내고, footer 간격을 줄이며, 프로젝트를 이미지로
  저장하는 방법을 배워보세요. MS Project 레이아웃을 손쉽게 최적화하세요.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Aspose.Tasks에서 프로젝트를 PDF로 내보내고 작업 목록과 footer 사이의 간격을 줄이기
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 프로젝트를 PDF로 내보내고 작업 목록과 footer 사이의 간격을 줄이기
url: /ko/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 프로젝트를 PDF로 내보내고 작업 목록과 바닥글 사이의 간격 줄이기

## 소개  
이 튜토리얼에서는 **프로젝트를 PDF로 내보내는 방법**을 배우면서 Microsoft Project 파일에서 작업 목록과 바닥글 사이의 불필요한 공간을 줄이는 방법도 살펴봅니다. 가이드를 마치면 Aspose.Tasks for Java를 사용해 깔끔한 PDF, PNG 이미지 및 HTML 페이지를 컴팩트한 레이아웃으로 생성할 수 있습니다. 단계별로 진행하면서 전문적인 보고서에 왜 중요한지 확인해 보세요.

## 빠른 답변  
- **“프로젝트를 PDF로 내보내다”는 무슨 의미인가요?** MPP 파일을 PDF 문서로 변환하여 작업, 타임라인 및 서식을 보존합니다.  
- **바닥글 간격을 줄이는 이유는?** 간격이 작아지면 특히 인쇄물이나 웹에서 보기 좋은 더 전문적인 보고서를 만들 수 있습니다.  
- **프로젝트를 이미지로 저장할 수도 있나요?** 네 – Aspose.Tasks는 PNG, JPEG 등 다양한 이미지 형식을 지원합니다.  
- **특별한 라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **필요한 Java 버전은?** 현재 Aspose.Tasks 라이브러리는 Java 8 이상에서 작동합니다.  

## “프로젝트를 PDF로 내보내다”란?  
프로젝트를 PDF로 내보내면 내부 MPP 구조가 휴대용 문서로 변환되어 Microsoft Project 없이도 모든 장치에서 열 수 있습니다. 이는 상태 보고서, 이해관계자 업데이트 또는 프로젝트 계획 보관에 이상적이며, 원본 레이아웃, 색상 및 작업 계층 구조를 그대로 유지합니다.

## 바닥글 간격을 줄여야 하는 이유  
기본 바닥글 간격은 불필요한 여백을 만들고 페이지 나눔 문제와 균형 잡히지 않은 외관을 초래합니다. 간격을 줄이면 페이지를 효율적으로 활용해 최종 PDF나 이미지가 더 읽기 쉬워지고, 페이지 수가 감소해 인쇄 비용을 절감하고 화면 탐색이 개선됩니다.

## 작업 목록과 바닥글 사이의 간격을 어떻게 줄일까요?  
`setReduceFooterGap`은 내보내기 중 바닥글 간격을 제어하는 Boolean 속성입니다.  
Aspose.Tasks는 이미지, PDF 및 HTML 저장 작업에 대해 `setReduceFooterGap(true)` 옵션을 제공합니다. 이 플래그를 활성화하면 엔진이 마지막 작업 행과 페이지 바닥글 사이의 공간을 자동으로 압축합니다. `true`로 설정하면 렌더러가 마진을 자동으로 조정해 작업 데이터가 잘리지 않으며 더 깔끔한 페이지 레이아웃을 제공합니다.

## Aspose.Tasks로 프로젝트를 이미지로 저장하기  
`ImageSaveOptions`는 프로젝트를 이미지 파일로 렌더링하는 방식을 구성합니다.  
`ImageSaveOptions` 클래스를 사용하면 일정 스냅샷을 PNG, JPEG 또는 BMP 형식으로 내보낼 수 있습니다. `setReduceFooterGap(true)`를 함께 활성화하면 생성된 이미지는 컴팩트한 PDF 레이아웃을 그대로 반영해 프레젠테이션이나 대시보드에 적합한 깔끔한 시각 자료가 됩니다.

## Java 프로젝트 PDF 내보내기  
다음 섹션에서는 MPP 파일을 로드하고 세 가지 형식으로 저장하는 **Java 프로젝트 내보내기** 전체 워크플로를 단계별로 안내합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요.
1. Java Development Kit (JDK) – 버전 8 이상.  
2. Aspose.Tasks for Java 라이브러리 – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  

## 패키지 가져오기  
코딩을 시작하기 전에 필요한 패키지를 가져옵니다:

```
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
```

## 1단계: 데이터 디렉터리 경로 제공  
```
```java
String dataDir = "Your Data Directory";
```
```  
`"Your Data Directory"`를 실제 Microsoft Project 파일(`HomeMovePlan.mpp`가 위치한 디렉터리) 경로로 교체하세요.

## 2단계: MPP 파일 읽기  
```
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
```  
위 코드는 `HomeMovePlan.mpp` 파일을 읽어옵니다.

## 3단계: ImageSaveOptions 설정 (프로젝트를 이미지로 저장)  
`ImageSaveOptions`는 프로젝트를 이미지 파일로 렌더링하는 방식을 구성합니다.  
```
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
```  
이미지 저장 옵션을 구성하고 `ReduceFooterGap`을 `true`로 설정해 작업 목록과 바닥글 사이의 간격을 줄입니다.

## 4단계: 이미지로 저장  
```
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
```  
구성된 옵션으로 프로젝트를 이미지로 저장합니다.

## 5단계: PdfSaveOptions 설정 (프로젝트를 PDF로 내보내기)  
`PdfSaveOptions`는 프로젝트를 PDF 형식으로 내보내는 설정을 지정합니다.  
```
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
```  
`ReduceFooterGap`을 `true`로 설정해 간격을 줄입니다.

## 6단계: PDF로 저장  
```
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
```  
구성된 옵션으로 프로젝트를 PDF로 저장합니다.

## 7단계: HtmlSaveOptions 설정  
`HtmlSaveOptions`는 프로젝트를 HTML로 변환할 때 스타일 및 레이아웃 옵션을 제어합니다.  
```
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
```  
`ReduceFooterGap`을 `true`로 설정합니다.

## 8단계: HTML로 저장  
```
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
```  
구성된 옵션으로 프로젝트를 HTML 파일로 저장합니다.

## 일반 사용 사례 및 팁  
- **이해관계자 보고:** 바닥글 간격을 줄인 PDF로 내보내면 보고서가 간결하고 인쇄 친화적입니다.  
- **대시보드 스냅샷:** Power BI나 Confluence에 빠르게 시각화가 필요할 때 이미지 내보내기를 사용합니다.  
- **웹 게시:** HTML 내보내기는 인터랙티브성을 유지하며 인트라넷 포털에 직접 삽입할 수 있습니다.  
- **전문가 팁:** 매우 큰 프로젝트의 경우 `ImageSaveOptions`의 `Resolution`을 300 dpi로 높여 선명도를 유지하면서도 간격 감소 효과를 활용하세요.

## 자주 묻는 질문 (추가)

**Q: 바닥글 간격을 줄이면 페이지 매김에 어떤 영향을 미치나요?**  
A: 각 페이지 하단의 빈 공간이 최소화되어 더 많은 작업을 한 페이지에 배치할 수 있어 전체 페이지 수가 감소합니다.

**Q: 단일 페이지에만 간격 감소 설정을 적용할 수 있나요?**  
A: 예, `ImageSaveOptions`에서 `setRenderToSinglePage(true)`를 설정하면 페이지 매김을 제어하면서 간격을 줄일 수 있습니다.

**Q: `setReduceFooterGap` 옵션은 다른 출력 형식에서도 사용할 수 있나요?**  
A: 현재 PNG, PDF, HTML 내보내기에서 지원됩니다. 다른 형식은 레이아웃을 수동으로 조정해야 할 수 있습니다.

**Q: 프로젝트에 사용자 정의 필드가 포함되어 있으면 어떻게 되나요?**  
A: 모든 사용자 정의 필드는 내보내기 시 그대로 유지됩니다. 레이아웃 조정은 간격에만 영향을 미치며 데이터는 변경되지 않습니다.

**Q: 라이브러리가 대형 프로젝트를 효율적으로 처리하나요?**  
A: Aspose.Tasks는 데이터를 스트리밍 처리하여 수백 페이지 규모의 MPP 파일도 전체를 메모리에 로드하지 않고 처리합니다. 고해상도 이미지를 내보낼 때는 충분한 힙 공간을 할당하세요.

---

**마지막 업데이트:** 2026-05-20  
**테스트 환경:** Aspose.Tasks 24.11 for Java  
**작성자:** Aspose

## 관련 튜토리얼

- [Save Project as Image – 24bppRgb Format with Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Save Project as Template, CSV, and Text with Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}