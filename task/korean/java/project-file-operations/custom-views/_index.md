---
title: Aspose.Tasks에서 사용자 정의 MS 프로젝트 뷰 생성
linktitle: Aspose.Tasks의 사용자 정의 보기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 손쉽게 사용자 정의 MS 프로젝트 뷰를 만드는 방법을 알아보세요. 맞춤형 보기를 통해 프로젝트 관리 효율성을 향상합니다.
type: docs
weight: 24
url: /ko/java/project-file-operations/custom-views/
---
## 소개
프로젝트 관리에서 보기를 사용자 정의하면 작업 및 리소스 관리의 명확성과 효율성이 크게 향상될 수 있습니다. Aspose.Tasks for Java는 특정 프로젝트 요구 사항에 맞는 사용자 정의 보기를 생성할 수 있는 강력한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 사용자 정의 MS 프로젝트 뷰를 만드는 방법을 단계별로 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 자바 개발 환경
시스템에 Java가 설치되어 있는지 확인하십시오.
### Aspose.Tasks for Java
 Java용 Aspose.Tasks를 다운로드하여 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
이제 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
// 보기가 없는 빈 프로젝트 만들기
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
## 2단계: 뷰 생성
```java
// 표준 Gantt 차트 보기 만들기
View view = new GanttChartView();
```
## 3단계: 보기 속성 사용자 정의
```java
// 일부 보기 속성 설정
view.setShowInMenu(true); // 메뉴에 뷰를 표시할지 여부를 나타냅니다.
view.setHighlightFilter(true); // 뷰에 대한 필터를 강조 표시할지 여부를 나타냅니다.
```
## 4단계: 보기 설정 조정
```java
// 일부 보기 설정 조정
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // 모든 페이지에 인쇄할 첫 번째 열 수 설정
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // 모든 페이지에 지정된 개수의 첫 번째 열을 인쇄할지 여부를 나타냅니다.
```
## 5단계: 프로젝트에 뷰 추가
```java
// 프로젝트에 뷰 추가
project.getViews().add(view);
```
## 6단계: 프로젝트 저장
```java
// 생성된 뷰로 프로젝트를 저장합니다.
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // WriteViewData 플래그를 사용하여 프로젝트 수정 사항을 유지합니다.보기
project.save(dataDir + "workWithView_output.mpp", options);
```
## 7단계: 보기 속성 확인
```java
// 새로 추가된 뷰의 속성을 확인하세요.
System.out.println("View Uid: " + view.getUid()); // 뷰의 고유 식별자를 인쇄합니다.
System.out.println("View Screen: " + view.getScreen()); // 보기의 화면 유형을 인쇄합니다.
System.out.println("View Type: " + view.getType()); // 뷰 유형 인쇄
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // 뷰의 상위 프로젝트 인쇄
```
## 결론
사용자 정의 MS 프로젝트 보기는 특정 요구 사항에 따라 프로젝트 데이터를 시각화하는 유연한 방법을 제공합니다. Aspose.Tasks for Java를 사용하면 사용자 정의 뷰 생성이 간단해지기 때문에 프로젝트 관리자는 워크플로를 효과적으로 간소화할 수 있습니다.
## 자주 묻는 질문
### Q1: Gantt 차트 이외의 보기를 사용자 정의할 수 있습니까?
A: 예, Aspose.Tasks for Java는 테이블과 그래프를 포함하여 Gantt 차트 외에도 다양한 유형의 보기를 사용자 정의할 수 있는 유연성을 제공합니다.
### Q2: Aspose.Tasks for Java는 대규모 프로젝트에 적합합니까?
답: 물론이죠. Aspose.Tasks for Java는 모든 규모의 프로젝트를 처리하도록 설계되었으며 효율적인 프로젝트 관리를 위한 강력한 기능을 제공합니다.
### Q3: Aspose.Tasks for Java는 뷰를 다른 형식으로 내보내기를 지원합니까?
A: 예, Aspose.Tasks for Java는 PDF, XLSX, HTML과 같은 다양한 형식으로 뷰 내보내기를 지원하여 다양한 플랫폼과의 호환성을 보장합니다.
### Q4: Aspose.Tasks for Java를 사용하여 사용자 정의 뷰 생성을 자동화할 수 있습니까?
답: 물론이죠. Aspose.Tasks for Java는 자동화를 위한 포괄적인 API를 제공하므로 개발자는 필요에 따라 프로그래밍 방식으로 사용자 정의 보기를 생성하고 관리할 수 있습니다.
### Q5: Java 지원을 위한 Aspose.Tasks에 대한 커뮤니티 포럼이 있습니까?
 A: 예, 다음에서 도움을 받고 다른 사용자와 교류할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) Java 관련 쿼리 및 토론용입니다.