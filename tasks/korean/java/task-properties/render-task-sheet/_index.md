---
date: 2026-02-26
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하고 작업 시트를 렌더링하는 방법을 배워보세요. 이
  단계별 가이드를 통해 MPP를 PDF로 빠르게 내보낼 수 있습니다.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트를 PDF로 저장 – Aspose.Tasks for Java를 사용한 작업 시트 렌더링
url: /ko/java/task-properties/render-task-sheet/
weight: 27
---

 all translated content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 PDF로 저장 – Aspose.Tasks에서 작업 시트 렌더링

## 소개
이 포괄적인 가이드에서는 **프로젝트를 PDF로 저장**하고 Aspose.Tasks for Java를 사용하여 작업 시트를 생성하는 방법을 알아봅니다. 이해관계자 검토를 위해 MPP 파일을 PDF로 내보내야 하든, 보고서를 위해 깔끔한 작업 시트를 렌더링해야 하든, 이 튜토리얼은 모든 단계를 안내하고 각 설정이 중요한 이유를 설명하며 실행에 필요한 정확한 코드를 보여줍니다.

## 빠른 답변
- **“프로젝트를 PDF로 저장”은 무엇을 하나요?** Microsoft Project 파일(MPP)을 PDF 문서로 변환하며, 선택적으로 작업 시트 형식으로 포맷합니다.  
- **작업 시트 PDF에 사용되는 형식은 무엇인가요?** `PdfSaveOptions`의 `PresentationFormat.TaskSheet` 옵션입니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 프로덕션에서는 임시 또는 정식 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **주요 전제 조건은 무엇인가요?** Java JDK, Aspose.Tasks for Java 라이브러리, 그리고 유효한 프로젝트 파일(예: *.mpp)입니다.  
- **PDF 레이아웃을 맞춤 설정할 수 있나요?** 네, Aspose.Tasks는 스타일링 및 페이지 설정을 위한 다양한 `PdfSaveOptions` 속성을 제공합니다.

## “프로젝트를 PDF로 저장”이란?
프로젝트를 PDF로 저장하면 내부 프로젝트 데이터를 휴대 가능하고 읽기 전용인 문서로 변환합니다. 이는 Microsoft Project가 설치되지 않은 이해관계자와 일정, 작업 시트 또는 상태 보고서를 공유할 때 이상적입니다.

## 왜 작업 시트를 렌더링하나요?
작업 시트는 각 작업을 표 형식으로 표시하여 ID, 이름, 시작/종료 날짜 및 기타 필드를 보여줍니다. 이를 PDF로 렌더링하면 플랫폼 간 일관된 포맷을 보장하고 인쇄하거나 다른 문서에 삽입하기가 쉬워집니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK)** – 최신 버전이 설치되어 있고 `java`/`javac`가 PATH에 포함되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 공식 사이트에서 라이브러리를 다운로드하십시오 [here](https://releases.aspose.com/tasks/java/).  
3. 변환하려는 유효한 **프로젝트 파일**(`*.mpp`), 예: `NewProductDev.mpp`.  

## 패키지 가져오기
먼저, 필요한 Aspose.Tasks 클래스를 가져옵니다. 이러한 import를 통해 PDF 저장 옵션, 프레젠테이션 형식 및 핵심 `Project` 객체에 접근할 수 있습니다.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## 단계별 가이드

### 단계 1: 문서 디렉터리 설정
소스 MPP 파일이 위치하고 생성된 PDF가 저장될 폴더를 정의합니다. 절대 경로나 상대 경로 모두 사용할 수 있으며, 폴더가 존재하는지 확인하십시오.

```java
String dataDir = "Your Document Directory";
```

### 단계 2: 프로젝트 파일 로드
기존 MPP 파일을 로드하여 `Project` 인스턴스를 생성합니다. 이 객체는 메모리 내 전체 프로젝트 구조를 나타냅니다.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### 단계 3: 저장 옵션 구성 – MPP를 PDF로 내보내기
`PdfSaveOptions`를 인스턴스화하고 Aspose.Tasks에 PDF를 **작업 시트** 형식으로 렌더링하도록 지정합니다. 이는 *프로젝트 PDF 내보내기* 사용 사례의 핵심 단계입니다.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### 단계 4: 프로젝트를 작업 시트로 저장 – 프로젝트를 PDF로 저장
`Project` 객체에서 `save` 메서드를 호출하고 대상 파일 이름과 구성된 옵션을 전달합니다. 이 작업은 **MPP 파일을 작업 시트 형식의 PDF**로 변환합니다.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### 단계 5: 결과 검토
지정한 디렉터리(`dataDir`)로 이동합니다. 모든 작업이 깔끔하게 포맷된 `taskSheet.pdf` 파일이 보일 것입니다. PDF 뷰어로 열어 변환이 성공했는지 확인하십시오.

## 일반적인 문제 및 해결책
- **FileNotFoundException** – `dataDir`이 경로 구분자(`/` 또는 `\\`)로 끝나는지, MPP 파일 이름이 정확한지 확인하십시오.  
- **LicenseException** – 라이선스 오류가 발생하면 Aspose.Tasks API를 호출하기 전에 임시 또는 구매한 라이선스를 적용하십시오.  
- **Blank PDF** – 프로젝트에 실제 작업이 포함되어 있는지 확인하십시오; 빈 프로젝트는 빈 PDF를 생성합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks가 모든 Java 버전과 호환되나요?**  
A: 네, Aspose.Tasks는 다양한 Java 버전에서 작동합니다. 자세한 내용은 [documentation](https://reference.aspose.com/tasks/java/)을 참고하십시오.

**Q: 구매 전에 Aspose.Tasks를 체험할 수 있나요?**  
A: 물론입니다! 무료 체험 버전을 [here](https://releases.aspose.com/)에서 확인하십시오.

**Q: Aspose.Tasks 지원을 어디서 받을 수 있나요?**  
A: 지원 및 토론을 위해 [forum](https://forum.aspose.com/c/tasks/15)에서 Aspose.Tasks 커뮤니티에 참여하십시오.

**Q: Aspose.Tasks 임시 라이선스를 어떻게 얻나요?**  
A: 임시 라이선스를 [here](https://purchase.aspose.com/temporary-license/)에서 받으십시오.

**Q: Aspose.Tasks for Java를 어디서 구매하나요?**  
A: Aspose.Tasks for Java를 [here](https://purchase.aspose.com/buy)에서 구매하십시오.

## 결론
이 단계들을 따라 하면 Aspose.Tasks for Java를 사용하여 **프로젝트를 PDF로 저장**하는 방법, 특히 작업 시트를 렌더링하는 방법을 배웠습니다. 이 기능을 통해 *MPP를 PDF로 빠르게 내보내*고, 읽기 쉬운 프로젝트 스냅샷을 공유하며, 프로젝트 데이터를 보다 넓은 보고 워크플로에 통합할 수 있습니다.

---

**마지막 업데이트:** 2026-02-26  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}