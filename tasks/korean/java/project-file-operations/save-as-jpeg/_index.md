---
date: 2025-12-20
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 JPEG 품질을 조정하고 JPEG
  이미지를 내보내는 방법을 배웁니다.
linktitle: Save Project As JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project를 JPEG로 저장할 때 JPEG 품질 조정
url: /ko/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS Project를 JPEG로 저장할 때 JPEG 품질 조정

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 JPEG 이미지로 저장할 때 **JPEG 품질을 조정**하는 방법을 배웁니다. 이 기능은 선명한 시각 보고서를 만들거나, 프로젝트 스냅샷을 프레젠테이션에 삽입하거나, 필요한 정확한 디테일 수준으로 JPEG 파일을 내보낼 때 유용합니다.

## 빠른 답변
- **“adjust JPEG quality”는 무엇을 하나요?** 내보낸 JPEG의 압축 수준을 제어하여 파일 크기와 시각 품질 사이의 균형을 맞춥니다.  
- **변환을 담당하는 라이브러리는?** Aspose.Tasks for Java는 Project 파일을 JPEG로 내보내는 간단한 API를 제공합니다.  
- **라이선스가 필요합니까?** 평가용 무료 체험이 가능하지만, 실제 운영에서는 상용 라이선스가 필요합니다.  
- **코드에서 품질을 설정할 수 있나요?** 예, `ImageSaveOptions.setJpegQuality(int)` 메서드(범위 0‑100)를 사용합니다.  
- **프로세스가 빠른가요?** 일반적인 프로젝트 파일을 JPEG로 변환하는 데 현대 하드웨어에서는 몇 초밖에 걸리지 않습니다.

## “adjust JPEG quality”란?
JPEG 품질 조정은 이미지를 JPEG 형식으로 저장할 때 적용되는 압축 비율을 설정하는 것을 의미합니다. 품질 값이 100에 가까울수록 디테일이 많이 보존되어 파일 크기가 커지고, 낮은 품질은 파일 크기를 줄이지만 시각적 선명도가 감소합니다.

## JPEG 내보내기에 Aspose.Tasks를 사용하는 이유
Aspose.Tasks는 Gantt 차트, 리소스 뷰 및 기타 프로젝트 시각화를 이미지 파일로 직접 렌더링할 수 있는 신뢰성 높고 플랫폼에 독립적인 방법을 제공합니다. 수동 스크린샷이 필요 없으며 환경에 관계없이 일관된 출력물을 보장합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요:
1. **Java Development Kit (JDK):** 시스템에 Java가 설치되어 있어야 합니다. 최신 버전은 [Java 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드 및 설치할 수 있습니다.  
2. **Aspose.Tasks for Java:** [문서](https://reference.aspose.com/tasks/java/)에 따라 Aspose.Tasks for Java를 다운로드하고 설정합니다.

## 패키지 가져오기
먼저 Java 파일에 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## 단계 1: 데이터 디렉터리 정의
MS Project 파일이 위치한 데이터 디렉터리 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```

## 단계 2: MS Project 파일 로드
Aspose.Tasks를 사용하여 MS Project 파일을 로드합니다.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## 단계 3: JPEG 품질 조정 (선택 사항)
출력 결과를 미세 조정하고 싶다면 `ImageSaveOptions` 클래스를 사용해 **JPEG 품질을 설정**할 수 있습니다. 품질 값은 0부터 100까지이며, 이는 **set jpeg quality java** 스타일로 설정하는 일반적인 방법입니다.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## 단계 4: 프로젝트를 JPEG로 저장
MS Project 파일을 JPEG 이미지로 저장합니다.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## MS Project에서 JPEG 내보내는 방법
위 단계들은 Microsoft Project 파일에서 **JPEG를 내보내는 방법**을 보여줍니다. JPEG 품질을 조정함으로써 이미지 선명도와 파일 크기 사이의 트레이드오프를 제어할 수 있어, 웹 게시, 인쇄 보고서 또는 슬라이드 삽입에 적합한 이미지를 만들 수 있습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 Microsoft Project 파일을 JPEG 이미지로 변환하면서 **JPEG 품질을 조정**하는 방법을 다루었습니다. 이 접근 방식은 프로젝트 시각화를 공유하고, 일관된 이미지 품질을 보장하며, 출력 크기에 대한 완전한 제어를 제공합니다.

## FAQ
### Q: JPEG 이미지의 품질을 조정할 수 있나요?
A: 예, `setJpegQuality()` 메서드를 사용해 0부터 100까지의 범위로 품질을 조정할 수 있습니다.  

### Q: JPEG 품질을 지정하지 않으면 어떻게 되나요?
A: 품질을 지정하지 않으면 기본 품질 값이 사용됩니다.  

### Q: Aspose.Tasks for Java는 무료로 사용할 수 있나요?
A: Aspose.Tasks for Java는 상용 라이브러리이지만, 무료 체험판으로 기능을 시험해 볼 수 있습니다. 자세한 내용은 [무료 체험 페이지](https://releases.aspose.com/)를 참고하세요.  

### Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다: [여기](https://forum.aspose.com/c/tasks/15).  

### Q: Aspose.Tasks에 대한 임시 라이선스를 구매할 수 있나요?
A: 예, [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 구매할 수 있습니다.

## 추가 자주 묻는 질문

**Q: JPEG 품질을 조정하면 Gantt 차트 가독성에 영향을 미치나요?**  
A: 높은 품질은 텍스트와 선 세부 정보를 보존하지만, 매우 낮은 품질은 작은 레이블을 읽기 어렵게 만들 수 있습니다.  

**Q: JPEG 외에 다른 이미지 형식도 내보낼 수 있나요?**  
A: 예, Aspose.Tasks는 적절한 `SaveFileFormat` 열거형을 사용해 PNG, BMP, TIFF 등을 지원합니다.  

**Q: 여러 페이지(예: 다른 뷰)를 한 번에 내보낼 수 있나요?**  
A: 원하는 뷰를 순회하면서 동일한 `ImageSaveOptions` 구성을 사용해 각각을 별도 JPEG로 저장할 수 있습니다.  

**Q: 필요한 Java 버전은 무엇인가요?**  
A: Aspose.Tasks for Java는 JDK 8 이상에서 작동합니다.  

**Q: 큰 프로젝트에서 생성되는 이미지가 너무 클 경우 어떻게 해야 하나요?**  
A: JPEG 품질을 낮추거나 `ImageSaveOptions`의 추가 설정을 통해 이미지 크기를 축소하는 방법을 고려하세요.  

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}