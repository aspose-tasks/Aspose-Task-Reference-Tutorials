---
date: 2025-12-20
description: Aspose.Tasks for Java에서 PDF를 내보내는 방법을 배우고, MPP를 PDF로 변환하여 프로젝트 파일을 효율적으로
  저장하는 간단한 가이드.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 PDF 내보내기 – PDF로 저장
url: /ko/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 PDF 내보내기 – PDF로 저장

## 소개
이 튜토리얼에서는 Java용 Aspose.Tasks에서 **PDF 내보내는 방법**을 보여드리며, 프로젝트를 PDF로 저장하는 과정을 안내합니다. Aspose.Tasks를 사용하면 **MPP를 PDF로 변환**하여 팀 및 이해관계자 간에 호환성과 공유 용이성을 보장할 수 있습니다. 이제 단계별로 진행하여 어떤 프로젝트 파일이든 인쇄 가능한 PDF를 빠르게 얻어보세요.

## 빠른 답변
- **Aspose.Tasks에서 “export PDF”는 무엇을 의미합니까?** 프로젝트 파일(예: MPP)을 시각적 레이아웃을 유지하는 PDF 문서로 변환하는 것을 의미합니다.  
- **필요한 라이브러리 버전은 무엇입니까?** `PdfSaveOptions`를 지원하는 Aspose.Tasks for Java 버전이면 모두 사용 가능하며, 최신 릴리스를 권장합니다.  
- **이 변환에 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 실제 운영에서는 상용 라이선스가 필요합니다.  
- **PDF 외관을 맞춤 설정할 수 있나요?** 예 – timescale, legends 및 기타 `PdfSaveOptions`를 설정할 수 있습니다.  
- **대형 프로젝트에서도 변환 속도가 빠른가요?** 일반적으로 몇 초 내에 완료되며, 성능은 프로젝트 규모와 선택 옵션에 따라 달라집니다.

## Aspose.Tasks에서 “how to export pdf”는 무엇을 의미합니까?
Aspose.Tasks로 PDF를 내보낸다는 것은 `.mpp`, `.xml`, `.xlsx`와 같은 프로젝트 파일을 가져와 Gantt 차트, 작업 사용 보기 또는 사용자가 구성한 다른 프레젠테이션 형식을 그대로 반영하는 PDF를 생성하는 것을 말합니다. 이는 보고서 작성, 문서화 또는 비기술 이해관계자에게 읽기 전용 뷰를 공유할 때 유용합니다.

## 프로젝트 파일을 PDF로 내보내는 이유
- **보편적인 가독성:** PDF는 원본 프로젝트 소프트웨어 없이도 모든 장치에서 열 수 있습니다.  
- **전문적인 프레젠테이션:** 클라이언트용 보고서에서 서식, 색상 및 레이아웃을 유지합니다.  
- **간편한 배포:** 이메일, 인트라넷 또는 클라우드 스토리지를 통해 버전 관리 문제 없이 공유할 수 있습니다.  
- **규정 준수 및 보관:** 장기 보관 및 규제 준수를 위해 PDF가 이상적입니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하세요:

1. **Java Development Kit (JDK):** JDK 8 이상이 머신에 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java Library:** 공식 사이트에서 라이브러리를 다운로드하세요 [here](https://releases.aspose.com/tasks/java/).  
3. **프로젝트 파일:** 변환할 기존 프로젝트 파일(예: `HomeMovePlan.mpp`)을 준비합니다.

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
`"Your Data Directory"`를 `.mpp` 파일이 위치한 절대 경로로 교체하세요. 이렇게 하면 프로젝트가 메모리로 로드되어 조작하거나 내보낼 수 있습니다.

### 단계 2: 프로젝트를 PDF로 저장
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
위 코드는 **프로젝트를 PDF로 저장**하는 간단한 작업을 수행하며, 동일한 폴더에 `Project5.pdf`를 생성합니다.

### 단계 3: 셀 크기에 맞게 내용 맞추기 (고급 PDF 저장 옵션)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
여기서는 **pdf save options**를 사용해 레이아웃을 제어하는 방법을 보여줍니다:
- `setFitContent(true)`는 내용이 셀 너비에 맞도록 강제합니다.  
- `setTimescale(Timescale.Months)`는 타임스케일을 월 단위로 변경합니다.  
- `setPresentationFormat(PresentationFormat.TaskUsage)`는 작업 사용 보기(Task Usage)를 선택합니다.

### 단계 4: 범례 숨기기 (더 깔끔한 출력)
```java
o.setLegendOnEachPage(false);
```
범례를 비활성화하면 특히 대형 프로젝트에서 PDF가 더 컴팩트해집니다.

### 단계 5: 적용된 옵션으로 프로젝트 저장
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
위 단계에서 정의한 사용자 옵션을 사용해 PDF를 최종 저장합니다. 이렇게 하면 월 단위 스케일이 적용되고 페이지당 범례가 없는 깔끔한 문서가 생성됩니다.

## 일반적인 문제 및 팁
- **파일을 찾을 수 없음:** `dataDir`이 파일 구분자(`/` 또는 `\\`)로 끝나고 올바른 디렉터리를 가리키는지 확인하세요.  
- **빈 페이지:** 선택한 `PresentationFormat`이 기대하는 뷰(Gantt, Task Usage 등)와 일치하는지 확인하세요.  
- **대용량 파일은 시간이 오래 걸림:** 매우 큰 프로젝트의 경우 `o.setFitContent(false)`로 설정해 처리 시간을 단축할 수 있습니다.  

## 자주 묻는 질문

**Q: Aspose.Tasks가 모든 Java 버전과 호환되나요?**  
A: 예, Aspose.Tasks는 JDK 6 이상 모든 Java 버전을 지원합니다.

**Q: PDF 출력의 외관을 맞춤 설정할 수 있나요?**  
A: 물론입니다! Aspose.Tasks는 timescale, legend 가시성, presentation format 등 다양한 **pdf save options**를 제공하여 필요에 맞게 PDF를 조정할 수 있습니다.

**Q: Aspose.Tasks가 다른 파일 형식 변환도 지원하나요?**  
A: 예, MPP, XML, XLSX 등 여러 형식 간 변환이 가능하므로 **convert mpp to pdf**뿐만 아니라 다양한 변환 작업에 활용할 수 있습니다.

**Q: Aspose.Tasks 체험판을 사용할 수 있나요?**  
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

**Q: Aspose.Tasks 지원은 어디서 받을 수 있나요?**  
A: 지원 및 문의는 공식 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

## 결론
이 가이드를 따라 Java 프로젝트에서 Aspose.Tasks를 이용해 **PDF를 내보내는 방법**을 익혔습니다. 한 줄 저장부터 `PdfSaveOptions`를 활용한 고급 맞춤 설정까지, 보고서, 클라이언트 프레젠테이션 또는 보관용으로 깔끔하고 공유하기 쉬운 PDF를 손쉽게 만들 수 있습니다.

---

**마지막 업데이트:** 2025-12-20  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}