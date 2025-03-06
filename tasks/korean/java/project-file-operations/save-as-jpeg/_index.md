---
title: Aspose.Tasks에서 MS 프로젝트를 JPEG로 변환
linktitle: Aspose.Tasks에 프로젝트를 JPEG로 저장
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 JPEG 이미지로 쉽게 변환하는 방법을 알아보세요. 생산성을 높이십시오.
type: docs
weight: 20
url: /ko/java/project-file-operations/save-as-jpeg/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 JPEG 이미지로 저장하는 방법을 살펴보겠습니다. 이는 프로젝트 시각화를 공유하거나 프로젝트 데이터를 보고서 또는 프리젠테이션에 통합하는 데 특히 유용할 수 있습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요. 최신 버전을 다운로드하여 설치할 수 있습니다.[자바 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Java용 Aspose.Tasks: 다음에 제공된 지침에 따라 Java용 Aspose.Tasks를 다운로드하고 설정합니다.[선적 서류 비치](https://reference.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 필요한 패키지를 Java 파일로 가져옵니다.
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## 1단계: 데이터 디렉터리 정의
MS 프로젝트 파일이 있는 데이터 디렉터리의 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: MS 프로젝트 파일 로드
Aspose.Tasks를 사용하여 MS 프로젝트 파일을 로드합니다.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## 3단계: JPEG 품질 구성(선택 사항)
 JPEG 품질을 조정하려면 다음을 사용하여 설정할 수 있습니다.`ImageSaveOptions` 수업. 품질 범위는 0부터 100까지입니다.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // JPEG 품질을 50으로 설정
```
## 4단계: 프로젝트를 JPEG로 저장
MS 프로젝트 파일을 JPEG 이미지로 저장합니다.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일을 JPEG 이미지로 저장하는 방법을 배웠습니다. 이 기능을 사용하면 프로젝트 데이터를 다양한 문서 및 프레젠테이션에 쉽게 공유하고 통합할 수 있습니다.
## FAQ
### Q: JPEG 이미지의 품질을 조정할 수 있나요?
 A: 예, 다음을 사용하여 품질을 조정할 수 있습니다.`setJpegQuality()` 0에서 100까지의 범위를 갖는 방법입니다.
### Q: JPEG 품질을 지정하지 않으면 어떻게 되나요?
A: 품질을 지정하지 않으면 기본 품질이 사용됩니다.
### Q: Java용 Aspose.Tasks는 무료로 사용할 수 있나요?
 A: Aspose.Tasks for Java는 상용 라이브러리이지만 무료 평가판을 통해 해당 기능을 탐색할 수 있습니다. 방문하다[무료 평가판 페이지](https://releases.aspose.com/) 자세한 내용은.
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks의 임시 라이선스를 구매할 수 있나요?
 A: 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).