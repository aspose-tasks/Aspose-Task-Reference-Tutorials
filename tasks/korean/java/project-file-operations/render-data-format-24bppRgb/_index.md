---
date: 2025-12-17
description: Aspose.Tasks for Java를 사용하여 프로젝트를 이미지로 저장하고 이미지 해상도를 변경하는 방법을 배웁니다. 이
  단계별 가이드는 24bppRgb 형식으로 MS Project 데이터를 렌더링하는 방법을 보여줍니다.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: 프로젝트를 이미지로 저장 – Aspose.Tasks를 사용한 24bppRgb 형식
url: /ko/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 이미지로 저장 – 24bppRgb 포맷 (Aspose.Tasks 사용)

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 24bppRgb 픽셀 포맷으로 **프로젝트를 이미지로 저장**하는 방법을 배웁니다. MS Project 데이터를 이미지로 렌더링하면 일정의 시각적 스냅샷을 공유하거나, 보고서에 타임라인을 삽입하거나, 프로젝트 포털용 썸네일을 생성할 때 유용합니다. 또한 **이미지 해상도 java**를 조정하는 방법도 보여드립니다.

## 빠른 답변
- **프로젝트를 이미지로 렌더링할 수 있나요?** 예, Aspose.Tasks를 사용하면 프로젝트를 TIFF, PNG, JPEG 등으로 저장할 수 있습니다.  
- **어떤 픽셀 포맷이 가장 높은 색 깊이를 제공하나요?** `Format24bppRgb`는 진정한 컬러(24‑bit) 이미지를 제공합니다.  
- **이미지 해상도는 어떻게 조정하나요?** `ImageSaveOptions`의 `setHorizontalResolution` 및 `setVerticalResolution`을 사용합니다.  
- **프로덕션 환경에 라이선스가 필요하나요?** 평가용이 아닌 경우 상업용 라이선스가 필요합니다.  
- **모든 Java 버전과 호환되나요?** Java 8 이상에서 작동합니다.

## “프로젝트를 이미지로 저장”이란?
프로젝트를 이미지로 저장한다는 것은 Microsoft Project 파일(`.mpp`)의 시각적 표현을 래스터 포맷(예: TIFF)으로 변환하는 것을 의미합니다. 결과 파일은 브라우저에서 표시하거나 문서에 삽입하거나 원본 Project 애플리케이션 없이 인쇄할 수 있습니다.

## 왜 24bppRgb 포맷을 사용하나요?
24bppRgb 픽셀 포맷은 각 픽셀을 빨강, 초록, 파랑 각각 8비트로 저장하여 알파 채널 없이 진정한 컬러 품질을 제공합니다. 색 정확도가 중요한 고해상도 보고서에 이상적이며, 32‑bit 포맷에 비해 파일 크기도 적당합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하고 설치하세요.  
3. **기본 Java 지식** – Java 문법 및 프로젝트 설정에 익숙하면 코드 스니펫을 따라가기 쉽습니다.

## 패키지 가져오기
먼저, Java 프로젝트에 필요한 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 정의
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 `.mpp` 파일이 위치한 절대 경로로 바꾸세요.

### 단계 2: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
이 코드는 Microsoft Project 파일(`project.mpp`)을 읽어 `Project` 객체를 생성합니다.

### 단계 3: 이미지 저장 옵션 구성
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
여기서는 출력 포맷을 TIFF로 지정하고 **72 dpi** 해상도를 설정합니다(필요에 따라 값을 변경하세요 – 여기서 **이미지 해상도 java**를 변경합니다). 또한 24bppRgb 픽셀 포맷을 선택해 진정한 컬러 출력을 얻습니다.

### 단계 4: 프로젝트 데이터를 이미지로 저장
```java
project.save(dataDir + "resFile.tif", options);
```
`save` 메서드는 위에서 정의한 옵션을 사용해 렌더링된 이미지를 `resFile.tif`에 기록합니다.

## 일반적인 문제와 해결 방법
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **빈 이미지 출력** | 프로젝트 뷰가 비어 있음 | 저장 전에 `project.setDefaultView(ViewType.Gantt);` 호출 |
| **저화질 이미지** | 해상도가 너무 낮음 | `setHorizontalResolution` 및 `setVerticalResolution`을 높임(예: 150 dpi) |
| **지원되지 않는 픽셀 포맷** | 오래된 Aspose.Tasks 버전 사용 | 최신 Aspose.Tasks for Java 릴리스로 업그레이드 |

## 결론
이제 Aspose.Tasks for Java를 사용해 24bppRgb 포맷으로 **프로젝트를 이미지로 저장**하고 해상도를 조정하는 방법을 알게 되었습니다. 이 방법을 통해 프로젝트 일정의 선명하고 색 정확도가 높은 시각적 표현을 생성해 공유, 보고 또는 보관에 활용할 수 있습니다.

## FAQ
### Q: 다른 이미지 포맷으로도 프로젝트 데이터를 렌더링할 수 있나요?
A: 예, Aspose.Tasks는 PNG, JPEG, BMP 등 다양한 이미지 포맷을 지원합니다.  
### Q: Aspose.Tasks는 다양한 MS Project 버전과 호환되나요?
A: 예, Aspose.Tasks는 2003, 2007, 2010, 2013, 2016 등 여러 버전을 지원합니다.  
### Q: 렌더링 이미지의 해상도와 픽셀 포맷을 맞춤 설정할 수 있나요?
A: 예, Aspose.Tasks를 사용해 요구 사항에 맞게 해상도와 픽셀 포맷을 자유롭게 조정할 수 있습니다.  
### Q: 상업적 사용을 위해 Aspose.Tasks 라이선스가 필요합니까?
A: 예, 상업적 사용 시 라이선스를 구매해야 합니다. 테스트용 임시 라이선인은 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.  
### Q: Aspose.Tasks 지원을 어디서 받을 수 있나요?
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

---

**마지막 업데이트:** 2025-12-17  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}