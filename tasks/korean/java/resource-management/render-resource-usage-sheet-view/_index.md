---
date: 2026-01-15
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하고 MS Project 리소스 사용량 및 시트 뷰를
  렌더링하는 방법을 배워보세요. 단계별 가이드를 따라 프로젝트를 손쉽게 PDF로 내보내세요.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트를 PDF로 저장 – Aspose.Tasks에서 리소스 사용량 및 시트 보기 렌더링
url: /ko/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 PDF로 저장 – Aspose.Tasks에서 리소스 사용량 및 시트 보기 렌더링

## 소개
이 튜토리얼에서는 Microsoft Project 파일의 리소스 사용량 및 시트 보기를 렌더링하면서 **프로젝트를 PDF로 저장**하는 방법을 알아봅니다. 이해관계자를 위한 인쇄 가능한 보고서를 생성하거나 MPP 파일을 보편적으로 볼 수 있는 형식으로 변환해야 할 때, Aspose.Tasks for Java을 사용하면 Microsoft Project를 설치할 필요 없이 간단히 처리할 수 있습니다.

## 빠른 답변
- **“save project as pdf”가 무엇을 하나요?** 선택한 보기를 유지하면서 Project 파일(MPP)을 PDF 문서로 변환합니다.  
- **어떤 보기를 내보낼 수 있나요?** Resource Usage, Sheet, Gantt, Task Usage 등.  
- **PDF에서 시간 눈금을 변경할 수 있나요?** 예 — 옵션에는 Days, ThirdsOfMonths, Months가 포함됩니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 독립적으로 작동합니다.  
- **프로덕션에 라이선스가 필요합니까?** 예, 비체험 사용을 위해 상업용 라이선스가 필요합니다.

## “save project as PDF”란 무엇인가요?
프로젝트를 PDF로 저장하면 선택한 Project 보기의 정적이며 고해상도 표현이 생성됩니다. 이는 클라이언트와 공유하거나, 보관하거나, 기본 프로젝트 파일을 노출하지 않고 인쇄할 때 이상적입니다.

## 왜 Aspose.Tasks를 사용해 프로젝트를 PDF로 내보내나요?
- **외부 종속성 없음** – Java를 지원하는 모든 플랫폼에서 작동합니다.  
- **세밀한 제어** – 보기, 시간 눈금 및 레이아웃을 선택할 수 있습니다.  
- **높은 정확도** – PDF가 원본 Project 보기의 모습을 그대로 반영합니다.  
- **자동화 준비** – CI 파이프라인, 보고 서비스 또는 배치 변환기에 통합할 수 있습니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK)** – 최신 버전을 권장합니다.  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.

## 패키지 가져오기
먼저, 필요한 클래스를 Java 프로젝트에 가져옵니다:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 단계별 가이드

### 1단계: 소스 프로젝트 읽기
변환하려는 MPP 파일을 로드합니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 2단계: 필요한 시간 눈금으로 SaveOptions 정의 (프로젝트를 PDF로 내보내기)
PDF 내보내기 옵션을 구성하고 원하는 시간 눈금을 설정합니다.  
*예제로 **Days**를 사용합니다.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 3단계: Presentation Format을 ResourceUsage로 설정
렌더링하려는 보기를 선택합니다. 여기서는 **Resource Usage** 보기를 사용합니다.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 4단계: 프로젝트 저장 (MPP를 PDF로 변환)
변환을 실행하고 PDF 파일을 생성합니다.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### 5단계: 다른 시간 눈금 설정에 대한 보기 렌더링 (시간 눈금 변경 PDF)
앞 단계들을 반복하여 **ThirdsOfMonths**, **Months**와 같은 다른 시간 눈금의 PDF를 생성합니다.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## 일반적인 문제 및 해결책
- **File not found errors** – `dataDir`이 올바른 폴더를 가리키고 MPP 파일 이름이 정확히 일치하는지 확인하십시오.  
- **Blank PDF output** – `PresentationFormat`이 데이터가 포함된 보기와 일치하는지 확인하십시오(예: ResourceUsage).  
- **Incorrect timescale** – 각 `project.save()` 호출 전에 `options.setTimescale()`이 호출되었는지 다시 확인하십시오.

## 자주 묻는 질문

### Aspose.Tasks가 Resource Usage와 Sheet 외에 다른 보기도 렌더링할 수 있나요?
Aspose.Tasks는 Gantt Chart, Task Usage, Calendar 보기 등 다양한 보기를 렌더링하는 것을 지원합니다.

### Aspose.Tasks가 다양한 버전의 Microsoft Project 파일과 호환되나요?
예, Aspose.Tasks는 MPP, MPT, XML 형식을 포함한 다양한 Microsoft Project 파일 형식을 지원합니다.

### Aspose.Tasks를 사용해 렌더링된 보기의 모양을 맞춤 설정할 수 있나요?
물론입니다! Aspose.Tasks는 특정 요구에 맞게 렌더링된 보기의 모양과 레이아웃을 맞춤 설정할 수 있는 다양한 옵션을 제공합니다.

### Aspose.Tasks가 시스템에 Microsoft Project가 설치되어 있어야 하나요?
아니요, Aspose.Tasks는 독립형 라이브러리이며 작동을 위해 Microsoft Project가 설치될 필요가 없습니다.

### Aspose.Tasks 사용자를 위한 기술 지원이 제공되나요?
예, Aspose.Tasks 사용자는 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 기술 지원을 받을 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose