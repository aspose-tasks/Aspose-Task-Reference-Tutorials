---
title: Aspose.Tasks에서 특정 간트 차트 데이터 읽기
linktitle: Aspose.Tasks에서 특정 간트 차트 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 특정 간트 차트 데이터를 추출하는 방법을 알아보세요. Java 애플리케이션에 원활하게 통합하기 위한 단계별 튜토리얼입니다.
weight: 16
url: /ko/java/project-data-reading/read-specific-gantt-chart-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 특정 간트 차트 데이터 읽기

## 소개
간트 차트는 프로젝트 관리를 위한 귀중한 도구로, 사용자가 작업, 일정 및 종속성을 시각화할 수 있도록 해줍니다. Aspose.Tasks for Java를 사용하면 개발자는 Gantt 차트에서 특정 데이터를 효율적으로 추출하여 애플리케이션에 통합할 수 있습니다. 이 튜토리얼에서는 특정 간트 차트 데이터를 읽는 과정을 단계별로 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): 원하는 IDE를 선택하세요. 널리 사용되는 선택에는 IntelliJ IDEA, Eclipse 또는 NetBeans가 있습니다.

## 패키지 가져오기
먼저 Aspose.Tasks 기능에 액세스하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```
## 1단계: 프로젝트 파일 로드
간트 차트 데이터가 포함된 프로젝트 파일을 로드하는 것으로 시작합니다. 데이터 디렉터리 경로를 제공하고 파일 이름을 지정합니다.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```
## 2단계: 간트 차트 보기에 액세스
프로젝트에서 Gantt 차트 보기를 검색합니다. 목록의 첫 번째 보기라고 가정하겠습니다.
```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```
## 3단계: 뷰 속성 추출
이제 Gantt 차트 보기의 다양한 속성을 추출하고 검사를 위해 인쇄해 보겠습니다.
```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// 다른 부동산에 대해 계속...
```
## 4단계: 막대 스타일 추출
간트 차트 보기에서 막대 스타일을 반복하고 세부 정보를 인쇄합니다.
```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // 인쇄 막대 스타일 세부정보...
}
```
## 5단계: 격자선 추출
간트 차트 보기의 눈금선에 대한 정보를 검색하고 인쇄합니다.
```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// 눈금선 세부정보 인쇄...
```
## 6단계: 텍스트 스타일 추출
간트 차트 보기에 사용되는 텍스트 스타일을 검색하고 인쇄합니다.
```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // 텍스트 스타일 세부정보 인쇄...
}
```
## 7단계: 진행 라인 추출
간트 차트 보기에서 진행 라인의 속성에 액세스하고 인쇄합니다.
```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// 기타 진행 라인 세부정보 인쇄...
```
## 8단계: 기간 계층 추출
Gantt 차트 보기에서 기간 계층에 대한 정보를 검색하고 인쇄합니다.
```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// 다른 기간 계층의 세부정보 인쇄...
```

## 결론
축하해요! Aspose.Tasks for Java를 사용하여 특정 간트 차트 데이터를 읽는 방법을 성공적으로 배웠습니다. 다음 단계를 수행하면 Java 애플리케이션 내에서 간트 차트 정보를 효율적으로 추출하고 조작할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 다른 Java 라이브러리 및 프레임워크와 원활하게 통합되도록 설계되었습니다.
### Q: Aspose.Tasks는 대규모 기업 프로젝트에 적합합니까?
답: 물론이죠. Aspose.Tasks는 강력한 기능과 뛰어난 성능을 제공하므로 모든 규모의 프로젝트에 적합합니다.
### Q: Aspose.Tasks는 여러 프로젝트 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 MPP, XML 및 MPX를 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### Q: Aspose.Tasks를 사용하여 Gantt 차트의 모양을 사용자 정의할 수 있나요?
답: 물론이죠. Aspose.Tasks는 요구 사항에 따라 Gantt 차트 모양을 사용자 정의하기 위한 광범위한 API를 제공합니다.
### Q: Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
A: 예, Aspose.Tasks는 포럼과 전용 지원 채널을 통해 포괄적인 기술 지원을 제공합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
