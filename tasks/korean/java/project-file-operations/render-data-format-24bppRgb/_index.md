---
title: Aspose.Tasks에서 24bppRgb 형식으로 MS 프로젝트 데이터 렌더링
linktitle: Aspose.Tasks에서 24bppRgb 형식으로 데이터 렌더링
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 MS Project 데이터를 Java의 이미지로 렌더링하는 방법을 알아보세요. 원활한 통합을 위해 단계별 튜토리얼을 따르세요.
type: docs
weight: 11
url: /ko/java/project-file-operations/render-data-format-24bppRgb/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 형식 24bppRgb로 데이터를 렌더링하는 과정을 안내합니다. 프로젝트 데이터를 이미지 형식으로 렌더링하면 프로젝트 진행 상황을 시각적으로 공유하거나 보고서를 작성하는 등 다양한 목적에 유용할 수 있습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍에 대한 기본 지식: Java 프로그래밍 언어에 익숙하면 코드 예제를 이해하고 구현하는 데 도움이 됩니다.

## 패키지 가져오기
먼저 Java 프로젝트에서 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 데이터 디렉터리 정의
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
```
이 단계에서는 프로젝트 데이터가 있는 디렉터리를 정의합니다. 바꾸다`"Your Data Directory"` 데이터 디렉터리의 실제 경로를 사용합니다.
## 2단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
여기서는 MS 프로젝트 파일(`project.mpp` ) Aspose.Tasks를 사용하여 저장합니다.`project` 물체.
## 3단계: 이미지 저장 옵션 구성
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
이 단계에는 프로젝트 데이터를 이미지로 저장하기 위한 옵션을 구성하는 작업이 포함됩니다. 이미지 형식(TIFF), 수평 및 수직 해상도, 픽셀 형식(24bppRgb)을 지정합니다.
## 4단계: 프로젝트 데이터를 이미지로 저장
```java
project.save(dataDir + "resFile.tif", options);
```
마지막으로 프로젝트 데이터를 이미지 파일(`resFile.tif`) 지정된 옵션을 사용합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 형식 24bppRgb로 프로젝트 데이터를 렌더링하는 방법을 배웠습니다. 제공된 단계를 따르면 다양한 목적을 위해 프로젝트 데이터를 이미지 형식으로 쉽게 변환할 수 있습니다.
## FAQ
### Q: 프로젝트 데이터를 다른 이미지 형식으로 렌더링할 수 있습니까?
A: 예, Aspose.Tasks는 프로젝트 데이터를 PNG, JPEG, BMP 등과 같은 다양한 이미지 형식으로 렌더링하는 것을 지원합니다.
### Q: Aspose.Tasks는 다른 버전의 MS Project와 호환됩니까?
A: 예, Aspose.Tasks는 2003, 2007, 2010, 2013 및 2016을 포함한 여러 버전의 MS Project를 지원합니다.
### Q: 렌더링된 이미지의 해상도와 픽셀 형식을 사용자 정의할 수 있습니까?
A: 예, Aspose.Tasks를 사용하여 요구 사항에 따라 해상도와 픽셀 형식을 사용자 정의할 수 있습니다.
### Q: Aspose.Tasks를 상업적으로 사용하려면 라이선스가 필요합니까?
 A: 예, Aspose.Tasks를 상업적으로 사용하려면 라이선스를 구매해야 합니다. 다음에서 테스트 목적으로 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 A: Aspose.Tasks에 대한 지원은 다음에서 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).