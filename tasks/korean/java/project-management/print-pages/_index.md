---
title: Aspose.Tasks에서 이미지를 분리하기 위해 페이지 인쇄
linktitle: Aspose.Tasks에서 이미지를 분리하기 위해 페이지 인쇄
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java에서 페이지를 인쇄하여 이미지를 분리하는 방법을 알아보세요. 이 단계별 가이드를 통해 프로젝트 시각화를 개선하세요.
weight: 22
url: /ko/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 이미지를 분리하기 위해 페이지 인쇄

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 페이지를 인쇄하여 이미지를 분리하는 과정을 안내합니다. 이 기능은 프로젝트 레이아웃이나 중요한 작업을 별도로 시각화해야 할 때 특히 유용할 수 있습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java 라이브러리: 프로젝트에 Aspose.Tasks for Java 라이브러리를 다운로드하고 포함합니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
Java 파일 시작 부분에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## 1단계: 프로젝트 데이터 로드
먼저 MPP 파일에서 프로젝트 데이터를 로드합니다.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## 2단계: 이미지 저장 옵션 설정
시작 날짜, 종료 날짜, 중요 작업, 범례 및 눈금선을 포함하여 이미지 저장 옵션을 정의합니다.
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## 3단계: 눈금선 사용자 정의
유형, 색상 및 패턴을 지정하여 이미지의 격자선을 사용자 정의합니다.
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## 4단계: 이미지 저장
프로젝트 레이아웃을 이미지로 단일 파일 및 별도 파일로 저장합니다.
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## 결론
이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 페이지를 인쇄하여 이미지를 분리하는 방법을 시연했습니다. 위에 설명된 단계를 수행하면 요구 사항에 따라 프로젝트 레이아웃과 중요한 작업을 효율적으로 시각화할 수 있습니다.
## FAQ
### Q: 프로젝트 레이아웃을 저장할 때 이미지 형식을 사용자 정의할 수 있나요?
 A: 예, Aspose.Tasks for Java는 PNG, JPEG, BMP 등과 같은 다양한 이미지 형식을 지원합니다.`ImageSaveOptions` 수업.
### Q: Aspose.Tasks for Java는 다른 Java 개발 환경과 호환됩니까?
A: 예, Aspose.Tasks for Java는 Eclipse, IntelliJ IDEA 및 NetBeans를 포함한 대부분의 Java 개발 환경과 호환됩니다.
### Q: Java용 Aspose.Tasks를 Maven 또는 Gradle 프로젝트에 통합할 수 있나요?
A: 예. 적절한 종속성을 추가하여 Java용 Aspose.Tasks를 Maven 또는 Gradle 프로젝트에 쉽게 통합할 수 있습니다.`pom.xml` 또는`build.gradle` 파일.
### Q: Aspose.Tasks for Java는 프로젝트 데이터를 이미지 이외의 다른 형식으로 내보내는 것을 지원합니까?
A: 예, Aspose.Tasks for Java는 프로젝트 데이터를 PDF, HTML, XLSX 등과 같은 다양한 형식으로 내보내는 것을 지원하여 데이터 시각화 및 보고에 유연성을 제공합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 커뮤니티 지원이 있나요?
 A: 예. 커뮤니티 지원을 찾고, 질문하고, 다른 사용자와 소통할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
