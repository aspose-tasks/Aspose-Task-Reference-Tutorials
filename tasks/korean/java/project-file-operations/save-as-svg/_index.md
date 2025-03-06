---
title: MS 프로젝트를 Java에서 SVG로 변환
linktitle: Aspose.Tasks에 SVG로 저장
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 파일을 Java에서 SVG로 저장하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 18
url: /ko/java/project-file-operations/save-as-svg/
---
## 소개
Aspose.Tasks for Java는 프로젝트 관리 파일 작업을 위한 강력한 라이브러리로, 개발자가 프로젝트 데이터를 조작하고, 다양한 작업을 수행하고, 보고서를 효율적으로 생성할 수 있도록 해줍니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트를 SVG로 저장하는 방법을 살펴보겠습니다. SVG(Scalable Vector Graphics)는 웹에서 벡터 그래픽을 표시하는 데 널리 사용되는 형식으로, 확장성과 고품질 렌더링을 제공합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
### 자바 개발 환경
시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 JDK를 다운로드하여 설치할 수 있습니다.
### Java 라이브러리용 Aspose.Tasks
 웹사이트에서 Aspose.Tasks for Java 라이브러리를 다운로드하여 설치하세요. 제공된 문서에서 다운로드 링크를 찾을 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 Java 프로그램에 필요한 패키지를 가져와야 합니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 2단계: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"`프로젝트 파일이 있는 디렉터리의 경로를 사용하세요.
## 3단계: 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
이 단계에서는 지정된 데이터 디렉터리에서 "HomeMovePlan.mpp"라는 프로젝트 파일을 로드합니다.
## 4단계: SVG로 저장
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
이 단계에서는 로드된 프로젝트를 지정된 데이터 디렉터리에 "project5.svg"라는 이름의 SVG 형식으로 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트를 SVG로 저장하는 방법을 배웠습니다. 제공된 단계를 따르면 프로젝트 파일을 SVG 형식으로 효율적으로 변환하여 웹 기반 애플리케이션 또는 시각화 도구와 원활하게 통합할 수 있습니다.
## FAQ
### Aspose.Tasks for Java는 모든 버전의 Microsoft Project 파일과 호환됩니까?
예, Aspose.Tasks for Java는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### SVG 출력의 모양을 사용자 정의할 수 있습니까?
예, 글꼴, 색상, 레이아웃 구성과 같은 매개변수를 조정하여 SVG 출력의 모양을 사용자 정의할 수 있습니다.
### Aspose.Tasks for Java를 상업적으로 사용하려면 라이선스가 필요합니까?
 예, Aspose.Tasks for Java를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. 홈페이지에서 라이센스를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### 구매하기 전에 Java용 Aspose.Tasks를 사용해 볼 수 있나요?
 예, 웹사이트에서 Aspose.Tasks for Java 무료 평가판을 요청할 수 있습니다.[여기](https://purchase.aspose.com/buy) 그 특징과 능력을 평가합니다.
### Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 포럼을 방문하면 Aspose.Tasks for Java에 대한 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15)에서 질문을 하고 커뮤니티와 상호 작용할 수 있습니다.