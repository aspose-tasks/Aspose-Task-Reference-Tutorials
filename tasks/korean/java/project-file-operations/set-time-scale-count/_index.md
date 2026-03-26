---
date: 2025-12-21
description: Aspose.Tasks for Java를 사용하여 Gantt 차트 뷰를 사용자 정의하고, 프로젝트 시각화를 관리하며, 프로젝트를
  PDF로 저장하는 방법을 배웁니다. 시간 축 개수를 손쉽게 조정하십시오.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 간트 차트 맞춤 설정 – Aspose.Tasks에서 MS Project 시간 눈금 개수 마스터하기
url: /ko/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt 차트 사용자 지정 – Aspose.Tasks에서 MS Project 시간 눈금 카운트 마스터하기

## 소개
Microsoft Project에서 **Gantt 차트**를 끌어야 하는 경우, 시간 눈금 카운트를 제어하는 ​​것이 핵심 기술입니다. Aspose.Tasks for Java를 사용하면 하단 및 기본 시간 눈금 티어를 프로그래밍 방식으로 설정하고, 눈금 표시를 처리한 후 **프로젝트를 PDF로 생성**하여 이해를 공유할 수 있습니다. 이 튜토리얼은 환경 설정부터 사용자가 지정한 Ganttify를 복잡하게 PDF 생성까지 전체 과정을 완료하도록 안내합니다.

## 빠른 답변
- **“Gantt 차트 사용자 지정”이란 무엇입니까?** 시간 눈금 티어, 색상 및 위치를 조정하여 보고 요청 사항에 만족하는 작업입니다.
- **하단 티어 카운트를 설정하는 API 메서드는?** `view.getBottomTimescaleTier().setCount(int)`.
- **프로젝트에서 직접 PDF를 생성할 수 있습니까?** 예—`project.save(..., SaveFileFormat.Pdf)`를 사용합니다.
- **프로덕션 사용에 필요한 가요?** 기적이 필요하며, 무료 체험판을 제공하고 있습니다.
- **지원되는 Java 버전은?** 최신 Aspose.Tasks 라이브러리는 Java8에서 이상 동작합니다.

## Aspose.Tasks의 "간트 차트 사용자 정의"란 무엇입니까?
Gantt 차트를 사용자가 지정한다는 것은 시간 눈금 슬라이더, 눈금 표시, 작업 린드 등을 나타내는 요소를 프로그래밍 방식으로 변경하여 **프로젝트 관리**에 놀라운 차트를 조정하는 것을 의미합니다. 시간 눈 카금 운트를 변경하면 각 동작을 통해 달, 몇 주, 몇 주 동안 관심을 제어할 수 있어 다양한 대상에게 차트를 더 많이 이해할 수 있습니다.

## 전제 조건
시작하기 전에 다음을 준비하세요:

1. **Java 개발환경** – JDK 8이상 설치.
2. **Aspose.Tasks for Java 라이브러리** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하세요.
3. **기본 Java 지식** – Java™와 함께 움직이는 개념에 대한 개념입니다.

## 패키지 가져오기
Java 프로젝트에 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 단계별 가이드

### 1단계: 데이터 디렉터리 설정
프로젝트 파일을 읽고 쓸 디렉터리를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 실제 머신의 절대 경로로 교체하세요.

### 2단계: 새 프로젝트 인스턴스 생성
모든 작업 및 뷰 설정을 보관할 새로운 `Project` 객체를 인스턴스화합니다:

```java
Project project = new Project();
```

### 3단계: 간트 차트 보기 구성
`GanttChartView` 객체를 생성합니다—이 객체를 통해 **Gantt 뷰 Java** 코드를 생성하고 차트 외관을 제어합니다:

```java
GanttChartView view = new GanttChartView();
```

### 4단계: 하단 계층 시간 눈금 개수 설정
하단 티어를 두 개의 간격으로 표시하고 눈금 표시를 숨깁니다:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 5단계: 중간 계층 시간 눈금 개수 설정
중간 티어에도 동일한 구성을 적용합니다:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 6단계: 사용자 지정 보기를 프로젝트에 추가
구성한 뷰를 `Project` 인스턴스에 추가합니다:

```java
project.getViews().add(view);
```

### 7단계: 샘플 작업(테스트 데이터) 추가
사용자 지정 Gantt 차트를 보여줄 수 있도록 특정 기간을 가진 작업 몇 개를 생성합니다:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 8단계: 프로젝트를 PDF로 저장
마지막으로 **사용자 지정된 Gantt 차트**를 포함한 프로젝트를 PDF 파일로 내보냅니다:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

생성된 PDF는 하단 및 중간 시간 눈금 티어가 **사용자 지정**된 모습을 보여주어 이해관계자에게 명확하고 인쇄 가능한 일정 뷰를 제공합니다.

## 일반적인 문제 및 문제 해결
- **PDF가 빈 페이지로 표시** – `dataDir`가 정의 파일 구분자(`/` 또는 `\`)로 표시, 릴레이가 실제로 존재하는지 확인하세요.
- **눈금이 상태 표시되었습니다** – 두 팀 모두 `setShowTicks(false)`가 호출되었는지 확인하세요.
- **기간이 적용되지 않습니다** – 작업 기간을 생성할 때 `TimeUnitType.Hour`(또는 의도적인 단위)를 사용하도록 확인하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 프로젝트 파일을 처리할 수 있나요?**
A: 예를 들어, 라이벌은 애플리케이션 모듈을 복잡하게 처리하도록 최적화되어 있습니다.

**Q: Aspose.Tasks for Java가 다양한 Java IDE와 호환되나요?**
A: 물론입니다 – Eclipse, IntelliJ IDEA, NetBeans 등 주요 IDE와 별개히 작동합니다.

**Q: 시간 눈금 설정 독수리 Gantt 차트 구성을 더 커스터마이즈할 수 있나요?**
A: 예, Aspose.Tasks는 링크 색상, 색상, 그리드 라인 등 광범위한 스타일 옵션을 제공합니다.

**Q: Aspose.Tasks for Java의 체험 버전을 제공하는데요?**
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험 버전을 받아보실 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 받을 수 없나요?**
A: Aspose.Tasks [여기](https://forum.aspose.com/c/tasks/15)에서 지원 및 지원을 받을 수 있습니다.

**Q: Gantt 차트 배경 색상을 어떻게 변경하려면 어떻게 해야 합니까?**
A: `java.awt.Color`를 가져오는 `view.getGanttChartProperties().setBackgroundColor(Color)` 메서드를 사용합니다.

## 결론
이 단계들을 따라서는 **Gantt 차트** 시간 눈금 티어를 **사용자 지정**하고 **프로젝트 요구**를 개선하며 Aspose.Tasks for Java를 사용하여 **프로젝트를 PDF로 저장**하는 방법을 적합하게 합니다. 이 접근 방식은 보고에 대한 완전한 제어를 제공하여 팀이나 클라이언트와 전문적인 작업 정보를 쉽게 공유할 수 있습니다.

---

**최종 업데이트:** 2025-12-21
**테스트 대상:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)
**저자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}