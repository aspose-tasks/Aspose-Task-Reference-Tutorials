---
date: 2026-05-26
description: Aspose.Tasks for Java를 사용하여 프로젝트에 뷰를 추가하고, 사용자 정의 뷰를 저장하며, 강력한 MS Project
  보고를 위해 뷰 속성을 설정하는 방법을 배웁니다.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Aspose.Tasks의 사용자 정의 뷰
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 프로젝트에 뷰 추가하는 방법
url: /ko/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트에 보기 추가하기 - Aspose.Tasks 사용

## 소개
프로젝트에 보기를 추가하는 방법을 찾고 계시다면, 이해관계자가 필요로 하는 정확한 보고서를 만들 수 있습니다. MS Project 보기를 사용자 정의하면 가장 관련성 높은 데이터를 표시하고, 복잡함을 줄이며, 의사결정을 빠르게 할 수 있습니다. **Aspose.Tasks for Java**는 강력하고 타입 안전한 API를 제공하여 MPP 파일 내부에 사용자 정의 보기를 생성, 구성 및 지속할 수 있게 합니다. 이 가이드에서는 환경 준비부터 보기 저장까지 모든 단계를 자세히 안내하므로, 깔끔하고 재사용 가능한 솔루션을 제공할 수 있습니다.

## 빠른 답변
- **주된 목적은 무엇입니까?** Aspose.Tasks for Java를 사용하여 프로젝트에 보기를 추가하고 MPP 파일 내부에 지속합니다.  
- **어떤 클래스가 보기를 생성합니까?** `GanttChartView` (또는 `TaskSheetView`와 같은 다른 보기 유형).  
- **보기를 메뉴에 표시하려면 어떻게 해야 합니까?** 저장하기 전에 `view.setShowInMenu(true)`를 호출합니다.  
- **프로젝트와 함께 보기를 저장하려면 어떻게 합니까?** `setWriteViewData(true)`와 함께 `MPPSaveOptions`를 사용합니다.  
- **라이선스가 필요합니까?** 예 – 프로덕션 배포에는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## “프로젝트에 보기 추가”란 무엇입니까?
*프로젝트에 보기를 추가한다*는 것은 새로운 시각적 표현(예: Gantt 차트, 작업 시트)을 생성하고 그 정의를 MPP 파일에 삽입하여 Microsoft Project가 나중에 표시할 수 있게 하는 것을 의미합니다. 이 작업은 Aspose.Tasks를 사용하면 완전히 프로그래밍 방식으로 수행되어 수동 UI 단계를 없앨 수 있습니다.

## 사용자 정의 보기를 사용하는 이유
Aspose.Tasks는 **50개 이상의 보기 관련 속성**을 지원하며 **수십만 개의 작업**이 있는 프로젝트도 전체 파일을 메모리에 로드하지 않고 처리할 수 있습니다. 보기를 한 번 정의하고 지속함으로써 모든 팀 구성원에게 일관된 보고를 보장하고 수동 구성 오류 위험을 줄일 수 있습니다.

## 전제 조건
- **Java Development Kit** (JDK 8 이상)이 머신에 설치 및 구성되어 있어야 합니다.  
- **Aspose.Tasks for Java** 라이브러리 – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
- 프로덕션 사용을 위한 유효한 **Aspose.Tasks 라이선스** 파일 (무료 평가판도 평가용으로 사용할 수 있습니다).

## 패키지 가져오기
`GanttChartView`, `MPPSaveOptions` 및 관련 클래스는 `com.aspose.tasks` 네임스페이스에 있습니다. 소스 파일 상단에 import하십시오:

`GanttChartView`는 Gantt 차트 보기 정의를 나타냅니다.  
`MPPSaveOptions`는 보기 데이터를 포함한 프로젝트 저장 방식을 제어합니다.  
`Project`는 MS Project 파일을 나타내는 주요 클래스입니다.  
`View`는 모든 보기 유형의 기본 클래스입니다.

```text
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
```

## 1단계: 프로젝트 설정
`Project` 인스턴스를 새로 만들거나 기존 파일을 로드합니다. 이 객체는 작업, 리소스 및 보기 등 모든 프로젝트 데이터를 보유합니다. `Prj`는 프로젝트 이름과 같은 프로젝트 속성에 대한 상수 키를 제공합니다.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## 2단계: 보기 생성
`GanttChartView`는 Aspose.Tasks가 제공하는 클래식 Gantt 차트의 표현입니다. 열, 막대 스타일, 시간 눈금 등을 제어할 수 있습니다.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## 3단계: 보기 속성 사용자 정의 *(set view properties)*
여기에서 보기의 외관을 세밀하게 조정할 수 있습니다: 첫 번째 표시 열을 설정하고, 막대 색상을 정의하며, 시간 눈금 세분성을 조정합니다. `setShowInMenu(boolean)`은 보기가 MS Project 메뉴에 표시되는지를 결정합니다. `setHighlightFilter(boolean)`은 보기에서 필터가 강조 표시되는지를 나타냅니다.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### 보기 메뉴 표시 방법
`view.setShowInMenu(true)`를 호출하면 새로 만든 보기가 MS Project **View** 메뉴에 표시되어 최종 사용자가 추가 구성 없이 즉시 접근할 수 있습니다.

## 4단계: 보기 설정 조정
페이지 레이아웃, 인쇄 옵션, 열 너비와 같은 고급 설정은 이 단계에서 구성됩니다. 적절한 조정으로 인쇄된 보고서가 화면 보기와 일치하도록 보장합니다.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## 5단계: 프로젝트에 보기 추가 *(add custom view java)*
보기를 구성한 후, 프로젝트의 `Views` 컬렉션에 추가합니다. `getViews()`는 프로젝트 내 보기 컬렉션을 반환합니다. 이 단계는 실제로 **프로젝트에 보기 추가**를 수행하여 파일 내부 구조의 일부가 되게 합니다.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## 6단계: 프로젝트 저장 *(save project view)*
프로젝트를 지속할 때 Aspose.Tasks에 보기 데이터를 기록하도록 알려야 합니다. `MPPSaveOptions` 클래스가 이 동작을 제어합니다. `setWriteViewData(boolean)`은 저장기에 보기 정의를 삽입하도록 지시합니다.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### 프로젝트 보기 저장이 중요한 이유
`options.setWriteViewData(true)`를 설정하면 Aspose.Tasks가 사용자 정의 보기 정의를 MPP 파일에 삽입하도록 지시합니다. 이 플래그가 없으면 보기는 메모리 내에만 존재하고 파일을 닫으면 사라집니다.

## 7단계: 보기 속성 확인
저장 후 프로젝트를 다시 로드하여 UI에 보기가 올바르게 표시되고 모든 속성(열, 막대 스타일 등)이 유지되는지 확인할 수 있습니다.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## 일반적인 사용 사례
- **이해관계자 보고:** 주요 마일스톤과 중요 경로 작업만을 고위 경영진에게 표시합니다.  
- **리소스 할당:** 용량 계획을 위해 리소스를 할당된 작업과 나란히 표시합니다.  
- **인쇄용 스냅샷:** 페이지 크기, 방향 및 열 가시성을 구성하여 오프라인 검토용 깔끔한 PDF를 생성합니다.

## 문제 해결 팁
- **보기가 메뉴에 표시되지 않음:** 저장하기 *전*에 `view.setShowInMenu(true)`가 호출되고 `MPPSaveOptions.setWriteViewData(true)`가 활성화되어 있는지 확인하십시오.  
- **인쇄물에 열 누락:** `setFirstColumnsCount`가 정의한 열 수와 일치하는지 확인하고 `setPrintFirstColumnsCountOnAllPages(true)`를 활성화하십시오.  
- **라이선스 예외:** `Project` 객체를 만들기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.lic");`를 사용해 라이선스 파일을 로드하십시오.

## 자주 묻는 질문

**Q: Gantt 차트 외에도 보기를 사용자 정의할 수 있나요?**  
A: 예 – Aspose.Tasks를 사용하면 사용자 정의 작업 시트, 리소스 시트, 심지어 사용자 정의 테이블까지 만들 수 있어 모든 시각적 요소를 완전히 제어할 수 있습니다.

**Q: Aspose.Tasks for Java가 대규모 프로젝트에 적합한가요?**  
A: 물론입니다. 이 라이브러리는 **500,000개 이상의 작업**을 스트리밍 API로 처리하여 메모리 사용량을 200 MB 이하로 유지합니다.

**Q: Aspose.Tasks for Java가 보기를 다양한 형식으로 내보내는 것을 지원하나요?**  
A: 예 – API를 통해 보기를 PDF, XLSX, HTML 및 여러 이미지 형식으로 직접 내보낼 수 있습니다.

**Q: Aspose.Tasks for Java를 사용해 사용자 정의 보기 생성을 자동화할 수 있나요?**  
A: 물론입니다. API는 완전하게 스크립트화할 수 있어 배치 작업이나 CI 파이프라인에서 보기를 생성, 수정 및 지속할 수 있습니다.

**Q: Aspose.Tasks for Java 지원을 위한 커뮤니티 포럼이 있나요?**  
A: 예, 다른 개발자와 Aspose 직원에게서 도움을 받을 수 있는 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 확인하십시오.

---

**마지막 업데이트:** 2026-05-26  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [MPP 파일 만들기 – Aspose.Tasks를 사용해 빈 프로젝트를 MPP 형식으로 생성 및 저장](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks에서 Gantt 차트 보기를 위한 데이터 디렉터리 설정](/tasks/java/project-configuration/configure-gantt-chart/)
- [MPP 파일 로드 Java - Aspose.Tasks로 프로젝트 속성 관리](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}