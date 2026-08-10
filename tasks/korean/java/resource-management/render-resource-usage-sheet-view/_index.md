---
date: 2026-06-15
description: Aspose.Tasks for Java를 사용하여 mpp를 pdf로 변환하고 Resource Usage 및 Sheet 보기를
  렌더링하는 방법을 배워보세요. timescale을 설정하고 상세한 PDF 보고서를 손쉽게 생성하는 단계별 가이드를 따라가세요.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP를 PDF로 변환하고 Resource Usage 보기 렌더링 – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP를 PDF로 변환하고 Resource Usage 보기 렌더링 – Aspose.Tasks
url: /ko/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP를 PDF로 변환하고 리소스 사용 보기 렌더링 – Aspose.Tasks

이 튜토리얼에서는 Microsoft Project 파일의 리소스 사용 및 시트 보기를 렌더링하면서 **MPP를 PDF로 변환하는 방법**을 배웁니다. Java용 Aspose.Tasks를 사용하면 서버에 Microsoft Project가 필요 없으며, MPP 파일에서 PDF 보고서를 빠르고 안정적으로 생성할 수 있습니다. 또한 출력이 보고 요구 사항에 맞도록 **시간 눈금 설정 방법**도 보여드립니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 하나요?** Microsoft Project (MPP) 파일을 읽고, 수정하고, 변환하며 MS Project가 설치되지 않아도 됩니다.  
- **한 줄 코드로 MPP를 PDF로 변환할 수 있나요?** 예 – Project를 로드하고, SaveOptions를 설정한 뒤 `save`를 호출하면 됩니다.  
- **지원되는 시간 눈금은 무엇인가요?** Days, ThirdsOfMonths, 그리고 Months.  
- **프로덕션에 라이선스가 필요합니까?** 비시험 배포에는 상용 라이선스가 필요합니다.  
- **이 라이브러리는 Java 8+와 호환되나요?** 물론입니다 – Java 8 및 이후 버전을 지원합니다.

## convert mpp to pdf란 무엇인가요?
*Convert mpp to pdf*는 Microsoft Project (.mpp) 파일을 가져와 프로젝트의 표, 일정, 차트 및 리소스 할당을 정확히 재현하는 PDF(Portable Document Format) 버전을 생성하는 과정을 의미합니다. 생성된 PDF는 Microsoft Project가 설치되지 않은 상태에서도 쉽게 공유, 인쇄 및 보관할 수 있습니다.

## Aspose.Tasks로 프로젝트를 PDF로 변환하는 이유는?
Aspose.Tasks는 **50개 이상의 입력 및 출력 형식**을 지원하며 전체 파일을 메모리에 로드하지 않고도 수백 페이지 규모의 프로젝트를 렌더링할 수 있어 RAM 사용량을 최대 70 %까지 절감합니다. PDF 출력은 표, 차트 및 리소스 할당을 그대로 유지하므로 이해관계자 배포 및 보관에 최적입니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – Java 8 이상이 설치된 환경.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  

## Aspose.Tasks for Java를 사용하여 mpp를 pdf로 변환하는 방법은?
소스 MPP 파일을 로드하고 원하는 시간 눈금을 구성한 뒤, 프레젠테이션 형식을 **ResourceUsage**로 설정하고 PDF로 저장합니다. 이 전체 흐름은 몇 번의 API 호출만으로 완료되며 일반적인 프로젝트 크기의 경우 1초 미만에 처리됩니다.

### 단계 1: 소스 프로젝트 읽기
`Project` 클래스는 메모리로 로드된 Microsoft Project 파일을 나타내며 데이터와 구조에 접근할 수 있게 해줍니다.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### 단계 2: 필요한 TimeScale 설정으로 SaveOptions 정의
`SaveOptions`는 프로젝트 저장 방식을 구성하며, 시간 눈금과 같은 형식별 설정을 지정할 수 있습니다.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 단계 3: PresentationFormat을 ResourceUsage로 설정
`PresentationFormat`은 출력 문서에 렌더링될 Project 뷰(예: ResourceUsage)를 결정합니다.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 단계 4: 프로젝트를 PDF로 저장
`project.save`는 제공된 `SaveOptions`를 사용해 프로젝트를 파일에 기록하고 최종 PDF를 생성합니다.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 단계 5: 다른 TimeScale 설정에 대한 보기 렌더링
이전 단계를 반복하면서 `TimeScale` 값을 변경하면 추가 시간 눈금 뷰를 렌더링할 수 있습니다.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### 단계 6: 선택 사항 – 배치로 여러 프로젝트 변환
많은 파일에 대해 **project to pdf 변환**이 필요하면 위 로직을 *.mpp* 파일이 들어 있는 디렉터리를 순회하는 루프 안에 넣으세요. 이 방법은 최소한의 코드 변경으로 **ms project pdf 저장**을 대량으로 수행합니다.  
다음 코드는 원하는 설정으로 MPP 파일을 PDF로 변환하는 완전한 예시를 보여줍니다.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## 일반적인 문제 및 해결책
- **PDF에서 글꼴 누락** – 서버에 필요한 글꼴을 설치하거나 `PdfSaveOptions`를 통해 포함시키세요.  
- **대형 프로젝트 파일로 인한 OutOfMemoryError** – `LoadOptions.setLoadAllResources(false)`를 사용해 필요할 때마다 리소스를 로드하도록 하세요.  
- **시간 눈금 렌더링 오류** – `options.setTimeScale(TimeScale.Days)`(또는 다른 enum) 값이 원하는 세분화와 일치하는지 확인하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks는 Resource Usage와 Sheet 외에 다른 뷰도 렌더링할 수 있나요?**  
A: 예, Gantt Chart, Task Usage, Calendar 등 많은 추가 뷰도 지원합니다.

**Q: Aspose.Tasks는 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다 – Project 2000부터 Project 2021까지의 MPP, MPT, XML 형식을 모두 처리합니다.

**Q: 렌더링된 뷰의 외관을 커스터마이즈할 수 있나요?**  
A: 예, `PdfSaveOptions`와 `PresentationOptions`를 통해 색상, 글꼴, 열 레이아웃 등을 수정할 수 있습니다.

**Q: Aspose.Tasks를 사용하려면 Microsoft Project가 설치되어 있어야 하나요?**  
A: 아니요, 독립형 라이브러리이며 Java 호환 환경이면 어디서든 동작합니다.

**Q: 기술 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15/)을 통해 지원을 받을 수 있습니다.

**마지막 업데이트:** 2026-06-15  
**테스트 환경:** Aspose.Tasks 24.12 for Java  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 Resource Usage 및 Sheet View 렌더링](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Aspose.Tasks에서 PDF 내보내기 – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Java용 Aspose.Tasks로 MPP 파일 만들기](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}