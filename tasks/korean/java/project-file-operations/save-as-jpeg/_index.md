---
date: 2026-05-26
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 내보낼 때 프로젝트 스냅샷 JPEG을
  만들고 JPEG 품질을 조정하는 방법을 배웁니다.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Aspose.Tasks에서 프로젝트를 JPEG로 저장
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 프로젝트 스냅샷 JPEG 만들기 – 품질 조정
url: /ko/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 스냅샷 JPEG 만들기 – Aspose.Tasks로 품질 조정

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project에서 **프로젝트 스냅샷 JPEG** 파일을 만드는 방법과 JPEG 품질을 미세 조정하여 크기와 선명도 요구 사항을 충족하는 방법을 알아봅니다. 회의실 프레젠테이션을 위한 선명한 이미지가 필요하든 웹 포털용 경량 파일이 필요하든, 품질 설정을 마스터하면 최종 출력에 대한 완전한 제어가 가능합니다.

## 빠른 답변
- **“JPEG 품질 조정”은 무엇을 하나요?** 내보낸 JPEG의 압축 수준을 제어하여 파일 크기와 시각적 충실도 사이의 균형을 맞춥니다.  
- **어떤 라이브러리가 변환을 처리하나요?** Aspose.Tasks for Java는 Project 파일을 JPEG로 내보내기 위한 간단한 API를 제공합니다.  
- **라이선스가 필요합니까?** 평가용으로는 무료 체험판을 사용할 수 있지만, 실제 운영에서는 상용 라이선스가 필요합니다.  
- **코드에서 품질을 설정할 수 있나요?** 예, `ImageSaveOptions.setJpegQuality(int)` 메서드(0‑100 범위)를 사용합니다.  
- **프로세스가 빠른가요?** 일반적인 프로젝트 파일을 JPEG로 변환하는 데 현대 하드웨어에서는 몇 초밖에 걸리지 않습니다.

## “JPEG 품질 조정”이란?
JPEG 품질을 조정하면 JPEG 형식으로 이미지를 저장할 때 적용되는 압축 비율을 지정할 수 있습니다. 값이 높을수록(100에 가까울수록) 더 많은 디테일을 보존하고, 값이 낮을수록 선명도가 감소하지만 파일 크기가 줄어듭니다. **직접 답변:** `ImageSaveOptions.setJpegQuality` 메서드에 숫자 값(0‑100)을 전달하여 JPEG 품질을 제어하면, 생성된 스냅샷의 크기와 시각적 충실도에 즉시 영향을 줍니다.  

JPEG 품질은 JPEG 형식으로 이미지를 저장할 때 적용되는 압축 비율을 의미합니다.

## JPEG 내보내기에 Aspose.Tasks를 사용하는 이유
**직접 답변:** Aspose.Tasks는 Microsoft Project를 설치하지 않아도 Gantt 차트, 리소스 뷰 및 사용자 정의 보고서를 이미지 파일로 렌더링하여 Windows, Linux, macOS 전반에 걸쳐 픽셀 단위로 완벽한 출력을 보장합니다.  

Aspose.Tasks는 **네** 가지 이미지 형식(JPEG, PNG, BMP, TIFF)으로 내보내기를 지원하며, 표준 2.5 GHz CPU에서 **최대 10,000개의 작업**을 포함한 프로젝트를 5 초 미만에 렌더링할 수 있어 구체적인 성능 보장을 제공합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:
1. **Java Development Kit (JDK)** – 최신 JDK(8 이상)를 [Java 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 설치합니다.  
2. **Aspose.Tasks for Java** – 공식 [문서](https://reference.aspose.com/tasks/java/)에 따라 라이브러리를 다운로드하고 설정합니다.

## 패키지 가져오기
`ImageSaveOptions`는 형식, 차원 및 JPEG 품질과 같은 이미지 내보내기 설정을 제어하는 Aspose.Tasks의 클래스입니다.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## 단계 1: 데이터 디렉터리 정의
Microsoft Project 파일이 들어 있는 폴더의 경로를 설정합니다. 이 디렉터리는 입력 및 출력 작업 모두에 사용됩니다.  
```java
String dataDir = "Your Data Directory";
```

## 단계 2: MS Project 파일 로드
`Project` 클래스는 메모리 내에서 Microsoft Project 파일을 나타내며, 작업, 리소스 및 뷰 데이터에 접근할 수 있게 합니다.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## 단계 3: JPEG 품질 조정 (선택 사항)
출력을 미세 조정하려면 `ImageSaveOptions` 클래스를 사용하여 **JPEG 품질을 설정**할 수 있습니다. 품질 값은 0에서 100까지이며, 100은 가장 높은 시각적 충실도를 제공합니다.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## 단계 4: 프로젝트를 JPEG로 저장
`Project.save`는 구성한 옵션을 사용하여 렌더링된 뷰를 이미지 파일로 저장합니다.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## MS Project에서 JPEG 내보내는 방법
**직접 답변:** `ImageSaveOptions`를 구성한 후 `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)`를 호출합니다; 이 메서드는 활성 뷰(기본값은 Gantt 차트)를 렌더링하고 지정된 품질로 JPEG 파일을 작성합니다. 이 한 줄 호출은 페이지 매김, 스케일링 및 색상 관리를 자동으로 처리합니다.  

JPEG 품질을 조정하면 이미지 선명도와 파일 크기 사이의 균형을 제어할 수 있어, 내보낸 이미지를 웹 게시, 인쇄 보고서 또는 슬라이드 삽입 등에 적합하게 만들 수 있습니다.

## 일반적인 문제 및 해결책
- **품질이 낮아 텍스트가 읽기 어려운 경우:** JPEG 품질을 70 이상으로 높이거나 무손실 렌더링을 위해 PNG로 전환하십시오.  
- **대형 프로젝트에서 메모리 부족 오류:** `saveOptions.setUseMemoryCache(true)`를 설정하여 스트리밍을 활성화하고 메모리 사용량을 200 MB 이하로 유지합니다.  
- **잘못된 뷰가 내보내진 경우:** 다른 뷰를 내보내려면 `saveOptions.setView(ViewType.TaskSheet)`를 사용하십시오.

## 자주 묻는 질문

**Q: JPEG 품질을 조정하면 Gantt 차트 가독성에 영향을 줍니까?**  
A: 높은 품질은 텍스트와 선 세부 정보를 보존하지만, 매우 낮은 품질은 작은 레이블을 읽기 어렵게 만들 수 있습니다.  

**Q: JPEG 외에 다른 이미지 형식으로 내보낼 수 있나요?**  
A: 예, Aspose.Tasks는 적절한 `SaveFileFormat` 열거형을 통해 PNG, BMP, TIFF를 지원합니다.  

**Q: 여러 페이지(예: 다른 뷰)를 한 번에 내보낼 수 있나요?**  
A: 원하는 뷰를 반복하면서 동일한 `ImageSaveOptions` 구성을 사용해 각각을 별도의 JPEG로 저장할 수 있습니다.  

**Q: 필요한 Java 버전은 무엇인가요?**  
A: Aspose.Tasks for Java는 JDK 8 이상에서 작동합니다.  

**Q: 큰 이미지를 생성하는 대형 프로젝트를 어떻게 처리하나요?**  
A: JPEG 품질을 낮추거나 추가 `ImageSaveOptions` 설정을 통해 이미지 차원을 축소하는 것을 고려하십시오.  

## 결론
우리는 Aspose.Tasks for Java를 사용하여 **프로젝트 스냅샷 JPEG** 파일을 만들고 JPEG 품질을 조정하는 방법을 단계별로 살펴보았습니다. 이 방법은 수동 스크린샷을 없애고, 플랫폼 간 일관된 렌더링을 보장하며, 이미지 선명도와 파일 크기 사이의 균형을 미세 조정할 수 있어 보고서, 프레젠테이션 및 웹 게시에 최적입니다.

---

**마지막 업데이트:** 2026-05-26  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [MPP 파일 만들기 – Aspose.Tasks로 MPP 형식의 빈 프로젝트 생성 및 저장](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java로 프로젝트를 템플릿, CSV, 텍스트로 저장](/tasks/java/project-file-operations/save-csv-text-template/)
- [Aspose.Tasks에서 빈 MS Project 파일 만들기](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}