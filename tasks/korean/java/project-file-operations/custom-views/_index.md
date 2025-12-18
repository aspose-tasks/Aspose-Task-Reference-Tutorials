---
date: 2025-12-18
description: Aspose.Tasks for Java에서 뷰를 만드는 방법을 배우고, 프로젝트 뷰를 저장하고 뷰 속성을 설정하는 방법을 포함합니다.
  맞춤형 MS Project 뷰로 프로젝트 관리 효율성을 향상시키세요.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: '뷰 만들기 방법: Aspose.Tasks에서 사용자 정의 MS Project 뷰'
url: /ko/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 보기 만들기 방법: Aspose.Tasks에서 사용자 지정 MS Project 보기

## 소개
If you’re looking for **how to create view** that matches your project’s unique reporting needs, you’ve come to the right place. In project management, customizing views can dramatically improve clarity and efficiency when handling tasks and resources. **Aspose.Tasks for Java** equips you with a rich API to **add custom view java**‑style solutions, letting you tailor MS Project views exactly the way you need them. In this tutorial we’ll walk through the process step‑by‑step, from setting up a project to saving the project view.

## 빠른 답변
- **주요 목적은 무엇입니까?** Aspose.Tasks for Java를 사용하여 사용자 지정 MS Project 보기를 만들고 지속시키기 위해.  
- **어떤 클래스가 보기를 생성합니까?** `GanttChartView` (또는 다른 보기 유형).  
- **보기가 메뉴에 표시되도록 하려면 어떻게 해야 하나요?** `view.setShowInMenu(true)`를 설정합니다.  
- **보기를 프로젝트와 함께 저장하려면 어떻게 해야 하나요?** `MPPSaveOptions`에 `setWriteViewData(true)`를 사용합니다.  
- **라이선스가 필요합니까?** 예, 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## 전제 조건
시작하기 전에 다음 전제 조건을 확인하십시오:

### Java 개발 환경
시스템에 Java가 설치되어 있는지 확인하십시오.

### Aspose.Tasks for Java
Aspose.Tasks for Java를 [here](https://releases.aspose.com/tasks/java/)에서 다운로드하고 설치하십시오.

## 패키지 가져오기
먼저, Java 프로젝트에 필요한 패키지를 가져오세요:
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

## 단계 1: 프로젝트 설정
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## 단계 2: 보기 생성
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## 단계 3: 보기 속성 사용자 지정 *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### 보기 메뉴 표시 방법
The call `view.setShowInMenu(true)` ensures the newly created view appears in the MS Project **view menu**, giving end‑users quick access.

## 단계 4: 보기 설정 조정
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## 단계 5: 프로젝트에 보기 추가 *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## 단계 6: 프로젝트 저장 *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### 프로젝트 보기 저장이 중요한 이유
Setting `options.setWriteViewData(true)` tells Aspose.Tasks to **save project view** information inside the MPP file, so the custom view persists across sessions.

## 단계 7: 보기 속성 확인
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## 일반적인 사용 사례
- **Stakeholder Reporting:** 고수준 마일스톤과 핵심 작업만 표시하는 보기를 생성합니다.  
- **Resource Allocation:** 리소스를 할당된 작업과 함께 나열하여 빠른 용량 확인이 가능한 보기를 구축합니다.  
- **Print‑Ready Documents:** 페이지 설정을 조정(단계 4와 같이)하여 인쇄 가능한 프로젝트 스냅샷을 생성합니다.

## 문제 해결 팁
- **View Not Appearing in Menu:** `view.setShowInMenu(true)`가 저장 전에 호출되었는지 확인하십시오.  
- **Missing Columns in Printout:** `setFirstColumnsCount`가 필요한 열 수와 일치하고 `setPrintFirstColumnsCountOnAllPages(true)`가 활성화되어 있는지 확인하십시오.  
- **License Exceptions:** 라이선스 오류가 발생하면 `Project` 객체를 만들기 전에 유효한 Aspose.Tasks 라이선스 파일이 로드되었는지 확인하십시오.

## 자주 묻는 질문
### Q1: Gantt 차트 외에도 보기를 사용자 지정할 수 있나요?
A: 예, Aspose.Tasks for Java는 Gantt 차트 외에도 테이블 및 그래프를 포함한 다양한 유형의 보기를 사용자 지정할 수 있는 유연성을 제공합니다.

### Q2: Aspose.Tasks for Java가 대규모 프로젝트에 적합한가요?
A: 예, 이 라이브러리는 어떤 규모의 프로젝트든 처리하도록 설계되었으며, 강력한 성능과 메모리 관리 기능을 제공합니다.

### Q3: Aspose.Tasks for Java가 보기를 다양한 형식으로 내보내는 것을 지원하나요?
A: 예, 보기를 PDF, XLSX, HTML 등 다양한 형식으로 내보낼 수 있어 플랫폼 간 원활한 공유가 가능합니다.

### Q4: Aspose.Tasks for Java를 사용해 사용자 지정 보기를 자동으로 생성할 수 있나요?
A: 물론입니다. API를 통해 완전 자동화가 가능하며, 프로그래밍 방식으로 사용자 지정 보기를 생성하고 관리할 수 있습니다.

### Q5: Aspose.Tasks for Java 지원을 위한 커뮤니티 포럼이 있나요?
A: 예, Java 관련 문의 및 토론을 위해 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 도움을 받고 다른 사용자와 교류할 수 있습니다.

---

**마지막 업데이트:** 2025-12-18  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}