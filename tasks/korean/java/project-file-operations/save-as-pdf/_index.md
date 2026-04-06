---
date: 2026-03-27
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하는 방법을 배우세요. MPP를 PDF로 변환하고
  프로젝트 파일을 효율적으로 내보내는 간단한 가이드입니다.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 프로젝트를 PDF로 저장하는 방법 – 내보내기 가이드
url: /ko/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks를 사용하여 프로젝트를 PDF로 저장하는 방법 – 내보내기 가이드

## 소개
이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 **프로젝트를 PDF로 저장하는 방법**을 알아봅니다. 한 줄 변환부터 고급 PDF 사용자 지정까지 모든 과정을 단계별로 안내해 드리며, MPP(또는 기타 지원 형식)를 깔끔하고 공유 가능한 PDF 문서로 변환할 수 있습니다. 빠른 인쇄용 보고서가 필요하든 완전하게 스타일링된 간트 차트가 필요하든, 이 단계들을 따라 하면 빠르게 원하는 결과를 얻을 수 있습니다.

## 빠른 답변
- **Aspose.Tasks에서 “PDF 내보내기”가 의미하는 것은?** 프로젝트 파일(예: MPP)을 시각적 레이아웃을 유지한 PDF 문서로 변환하는 것을 의미합니다.  
- **필요한 라이브러리 버전은?** `PdfSaveOptions`를 지원하는 Java용 Aspose.Tasks 버전이면 모두 사용 가능하며, 최신 릴리스를 권장합니다.  
- **이 변환에 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 실제 운영에서는 상용 라이선스가 필요합니다.  
- **PDF 외관을 사용자 지정할 수 있나요?** 예 – timescale, legends 및 기타 `PdfSaveOptions`를 설정할 수 있습니다.  
- **대형 프로젝트에서도 변환이 빠른가요?** 일반적으로 몇 초 내에 완료되며, 성능은 프로젝트 크기와 선택한 옵션에 따라 달라집니다.

## Aspose.Tasks에서 “프로젝트를 PDF로 저장”이란?
Aspose.Tasks를 사용하여 프로젝트를 PDF로 저장한다는 것은 `.mpp`, `.xml`, `.xlsx`와 같은 프로젝트 파일을 가져와서 간트 차트, 작업 사용 보기 또는 사용자가 지정한 다른 프레젠테이션 형식을 그대로 반영한 PDF를 생성하는 것을 의미합니다. 이는 보고서 작성, 문서화, 비기술 이해관계자와의 읽기 전용 뷰 공유 등에 유용합니다.

## 왜 간트 차트를 PDF로 내보내나요?
- **보편적인 가독성:** PDF는 원본 프로젝트 소프트웨어 없이도 모든 장치에서 열 수 있습니다.  
- **전문적인 프레젠테이션:** 색상, 글꼴 및 레이아웃을 유지하여 고객용 보고서에 적합합니다.  
- **쉬운 배포:** 이메일, 인트라넷 또는 클라우드 스토리지를 통해 버전 관리 걱정 없이 공유할 수 있습니다.  
- **컴플라이언스 및 보관:** PDF는 장기 보관 및 규제 준수에 이상적입니다.

## 사전 요구 사항
시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK):** 머신에 JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java 라이브러리:** 공식 사이트 [here](https://releases.aspose.com/tasks/java/)에서 라이브러리를 다운로드하십시오.  
3. **프로젝트 파일:** 변환할 기존 프로젝트 파일(예: `HomeMovePlan.mpp`)을 준비하십시오.

## 패키지 가져오기
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## 단계별 가이드

### 단계 1: 입력 프로젝트 파일 읽기
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
`"Your Data Directory"`를 `.mpp` 파일이 위치한 절대 경로로 교체하십시오. 이렇게 하면 프로젝트가 메모리로 로드되어 조작하거나 내보낼 수 있습니다.

### 단계 2: 프로젝트를 PDF로 저장 (기본 변환)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
위 코드는 간단한 **프로젝트를 PDF로 저장** 작업을 수행하며, 동일한 폴더에 `Project5.pdf`를 생성합니다.

### 단계 3: 셀 크기에 내용 맞추기 (고급 PDF 저장 옵션)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
여기서는 레이아웃을 제어하기 위해 **pdf save options** 사용을 보여줍니다:
- `setFitContent(true)`는 내용을 셀 너비에 맞추도록 강제합니다.  
- `setTimescale(Timescale.Months)`는 타임스케일을 월 단위로 변경합니다.  
- `setPresentationFormat(PresentationFormat.TaskUsage)`는 작업 사용 보기(Task Usage)를 선택합니다.

### 단계 4: 범례 숨기기 (더 깔끔한 출력)
```java
o.setLegendOnEachPage(false);
```
범례를 비활성화하면 특히 대형 프로젝트에서 PDF를 더 간결하게 만들 수 있습니다.

### 단계 5: 적용된 옵션으로 프로젝트 저장
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
이 마지막 단계에서는 위에서 정의한 사용자 옵션을 사용해 PDF를 작성하며, 페이지당 범례가 없는 깔끔한 월 단위 스케일 문서를 생성합니다.

## 간트 차트를 PDF로 내보내기 – 사용자 정의 스타일링
특정 모양의 간트 차트만 내보내고 싶다면 `PresentationFormat`을 `GanttChart`로 설정하고 `setBarColor` 또는 `setShowCriticalTasks`와 같은 추가 옵션을 조정하십시오. 이 방법을 사용하면 시각 요소를 완전히 제어하면서 **export gantt chart to pdf**를 수행할 수 있습니다.

## 일반적인 문제 및 팁
- **파일을 찾을 수 없음:** `dataDir`이 파일 구분자(`/` 또는 `\\`)로 끝나고 올바른 디렉터리를 가리키는지 확인하십시오.  
- **빈 페이지:** 선택한 `PresentationFormat`이 기대하는 뷰(예: Gantt, Task Usage)와 일치하는지 확인하십시오.  
- **대용량 파일은 시간이 오래 걸림:** 매우 큰 프로젝트의 경우 처리 시간을 줄이기 위해 `o.setFitContent(false)` 설정을 고려하십시오.  

## 자주 묻는 질문

**Q: Aspose.Tasks가 모든 Java 버전과 호환되나요?**  
A: 예, Aspose.Tasks는 JDK 6 이상 모든 Java 버전을 지원합니다.

**Q: PDF 출력의 외관을 사용자 지정할 수 있나요?**  
A: 물론입니다! Aspose.Tasks는 timescale, legend 가시성, presentation format 등 다양한 **pdf save options**를 제공하여 PDF를 필요에 맞게 조정할 수 있습니다.

**Q: Aspose.Tasks가 변환을 위한 다른 파일 형식을 지원하나요?**  
A: 예, MPP, XML, XLSX 등 다양한 형식 간 변환이 가능하여 **convert mpp to pdf** 및 기타 변환 작업에 다재다능한 도구입니다.

**Q: Aspose.Tasks의 체험 버전을 제공하나요?**  
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험판을 받을 수 있습니다.

**Q: Aspose.Tasks 지원을 어디서 받을 수 있나요?**  
A: 지원 및 도움을 위해 공식 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

## 결론
이 가이드를 따라 하면 Aspose.Tasks를 사용하여 Java 프로젝트에서 **프로젝트를 PDF로 저장하는 방법**을 알게 됩니다. 한 줄 저장부터 `PdfSaveOptions`를 활용한 고급 사용자 지정까지 가능합니다. 이러한 기술을 활용해 보고서, 고객 프레젠테이션 또는 보관용으로 깔끔하고 공유 가능한 PDF를 제작하십시오.

---

**Last Updated:** 2026-03-27  
**테스트 대상:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}