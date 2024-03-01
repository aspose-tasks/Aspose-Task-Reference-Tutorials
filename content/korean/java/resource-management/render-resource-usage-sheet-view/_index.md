---
title: Aspose.Tasks의 렌더링 리소스 사용량 및 시트 보기
linktitle: Aspose.Tasks의 렌더링 리소스 사용량 및 시트 보기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java에서 MS 프로젝트 리소스 사용량 및 시트 보기를 렌더링하는 방법을 알아보세요. 자세한 PDF 보고서를 쉽게 생성하려면 단계별 가이드를 따르십시오.
type: docs
weight: 16
url: /ko/java/resource-management/render-resource-usage-sheet-view/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스 사용량 및 시트 보기를 렌더링하는 방법을 알아봅니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치할 필요 없이 Microsoft Project 파일로 작업할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 설치 및 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java Development Kit가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 버전의 JDK를 다운로드하여 설치할 수 있습니다.
2.  Aspose.Tasks for Java: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져와야 합니다.
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 1단계: 소스 프로젝트 읽기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
// 소스 프로젝트 읽기
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
이 단계에서는 소스 프로젝트 파일의 경로를 지정합니다(`ResourceUsageView.mpp` ) 그리고`Project` 그것을 읽는 수업.
## 2단계: 필수 TimeScale 설정으로 SaveOptions 정의
```java
// 필요한 TimeScale 설정을 사용하여 SaveOptions를 일로 정의합니다.
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 여기에서 우리는`SaveOptions` 필수와 함께`TimeScale` 설정. 이 예에서는`TimeScale` 일까지.
## 3단계: 프레젠테이션 형식을 ResourceUsage로 설정
```java
// 프레젠테이션 형식을 ResourceUsage로 설정합니다.
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 프레젠테이션 형식을 다음과 같이 설정했습니다.`ResourceUsage`, 자원 사용량 보기를 렌더링하려고 함을 나타냅니다.
## 4단계: 프로젝트 저장
```java
// 프로젝트 저장
project.save(dataDir + days, options);
```
마지막으로 지정된 옵션을 사용하여 프로젝트를 저장합니다. 이 예에서는 출력 파일이 다음과 같이 저장됩니다.`result_days.pdf`.
## 5단계: 다른 TimeScale 설정을 위한 렌더 뷰
다양한 TimeScale 설정(ThirdsOfMonths 및 Months)을 사용하여 뷰를 렌더링하려면 2~4단계를 반복합니다.
```java
// 시간 표시줄 설정을 ThirdsOfMonths로 설정합니다.
options.setTimescale(Timescale.ThirdsOfMonths);
// 프로젝트 저장
project.save(thirds, options);
// 기간 설정을 월로 설정합니다.
options.setTimescale(Timescale.Months);
// 프로젝트 저장
project.save(dataDir + months, options);
```
 변경 사항을 확인하세요.`Timescale` 각 보기에 맞게 설정합니다.

## 결론
이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 MS 프로젝트 리소스 사용량 및 시트 보기를 렌더링하는 방법을 살펴보았습니다. 위에 설명된 단계를 수행하면 이러한 뷰를 PDF 형식으로 효율적으로 생성하여 프로젝트 데이터의 시각화 및 분석을 더 쉽게 할 수 있습니다.
## FAQ
### Aspose.Tasks는 리소스 사용량 및 시트 외에 다른 뷰를 렌더링할 수 있나요?
Aspose.Tasks는 간트 차트, 작업 사용량, 달력 보기 등 다양한 보기 렌더링을 지원합니다.
### Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
예, Aspose.Tasks는 MPP, MPT 및 XML 형식을 포함한 광범위한 Microsoft Project 파일 형식을 지원합니다.
### Aspose.Tasks를 사용하여 렌더링된 뷰의 모양을 사용자 정의할 수 있나요?
전적으로! Aspose.Tasks는 특정 요구 사항에 맞게 렌더링된 뷰의 모양과 레이아웃을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.
### Aspose.Tasks를 사용하려면 Microsoft Project를 시스템에 설치해야 합니까?
아니요, Aspose.Tasks는 독립 실행형 라이브러리이며 작동을 위해 Microsoft Project를 설치할 필요가 없습니다.
### Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
 예, Aspose.Tasks 사용자는 다음을 통해 기술 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).