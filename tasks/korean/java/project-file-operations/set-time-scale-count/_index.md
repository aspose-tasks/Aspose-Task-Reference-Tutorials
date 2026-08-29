---
date: 2026-03-29
description: Aspose.Tasks for Java를 사용하여 Gantt 차트 시간 눈금 수를 사용자 정의하면서 프로젝트 PDF 파일을
  만드는 방법을 배웁니다. 이 가이드는 전체 제어를 통해 Gantt를 PDF로 내보내는 단계별 방법을 보여줍니다.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트 PDF 만들기 – 간트 차트 시간 눈금 맞춤
url: /ko/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 PDF 만들기 – 간트 차트 시간 눈금 사용자 정의

## 소개
완벽하게 조정된 간트 차트를 반영하는 **프로젝트 PDF 만들기** 파일이 필요하다면, 시간 눈금 개수를 제어하는 것이 핵심입니다. Aspose.Tasks for Java를 사용하면 하단 및 중간 시간 눈금 티어를 프로그래밍 방식으로 설정하고 눈금 표시를 숨긴 다음, **프로젝트를 PDF로 저장**하여 쉽게 배포할 수 있습니다. 이 튜토리얼에서는 개발 환경 설정부터 맞춤형 간트 뷰를 보여주는 정교한 PDF 생성까지 필요한 모든 과정을 단계별로 안내합니다.

## 빠른 답변
- **“간트 차트 사용자 정의”가 의미하는 바는?** 보고 요구에 맞게 시간 눈금 티어, 색상 및 레이아웃을 조정하는 것입니다.  
- **하단 티어 개수를 설정하는 API 메서드는?** `view.getBottomTimescaleTier().setCount(int)`.  
- **프로젝트에서 직접 PDF를 생성할 수 있나요?** 예—`project.save(..., SaveFileFormat.Pdf)`를 사용합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상업용 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Java 버전은?** 최신 Aspose.Tasks 라이브러리는 Java 8 이상에서 작동합니다.

## Aspose.Tasks에서 “간트 차트 사용자 정의”란?
간트 차트를 사용자 정의한다는 것은 시간 눈금 간격, 눈금 표시, 작업 막대와 같은 시각적 요소를 프로그래밍 방식으로 변경하여 차트가 **프로젝트 시각화 관리** 방식에 맞도록 만드는 것을 의미합니다. 시간 눈금 개수를 변경하면 각 구간이 며칠, 몇 주, 몇 달을 나타내는지를 제어할 수 있어 다양한 청중에게 차트를 더 명확하게 보여줄 수 있습니다.

## 맞춤형 간트 차트로 프로젝트 PDF를 만드는 이유
- **이해관계자용 출력:** PDF는 모든 환경에서 볼 수 있어 모든 사람이 동일한 일정 레이아웃을 확인할 수 있습니다.  
- **인쇄 친화적:** 시간 눈금 티어를 정밀하게 제어하면 혼잡하거나 모호한 인쇄물을 방지할 수 있습니다.  
- **자동화:** PDF 생성을 CI 파이프라인이나 보고 서비스에 통합하여 수동 작업을 전혀 필요 없게 합니다.  

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java 개발 환경** – JDK 8 이상 설치.  
2. **Aspose.Tasks for Java 라이브러리** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **기본 Java 지식** – Java 구문 및 객체 지향 개념에 익숙함.  

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

### 단계 1: 데이터 디렉터리 설정
프로젝트 파일을 읽고 쓸 위치를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 머신의 절대 경로로 교체하십시오.

### 단계 2: 새 Project 인스턴스 만들기
모든 작업 및 보기 설정을 보관할 새로운 `Project` 객체를 인스턴스화합니다:

```java
Project project = new Project();
```

### 단계 3: 간트 차트 보기 구성
`GanttChartView` 객체를 생성합니다—여기에서 차트 모양을 제어하기 위한 **Gantt view Java** 코드를 **생성**하게 됩니다:

```java
GanttChartView view = new GanttChartView();
```

### 단계 4: 하단 티어의 시간 눈금 개수 설정
하단 티어를 두 개의 구간으로 표시하고 눈금 표시를 숨기도록 조정합니다:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 단계 5: 중간 티어의 시간 눈금 개수 설정
같은 구성을 중간 티어에도 적용합니다:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 단계 6: 맞춤형 보기를 Project에 추가
방금 구성한 보기를 `Project` 인스턴스에 연결합니다:

```java
project.getViews().add(view);
```

### 단계 7: 샘플 작업 추가 (테스트 데이터)
맞춤형 간트 차트를 보여주기 위해 특정 기간을 가진 몇 개의 작업을 생성합니다:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 단계 8: Project를 PDF로 저장
마지막으로, **맞춤형 간트 차트**를 포함한 프로젝트를 PDF 파일로 내보냅니다:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

생성된 PDF는 하단 및 중간 시간 눈금 티어가 **사용자 정의**된 방식을 보여주며, 이해관계자에게 명확하고 인쇄 가능한 일정 뷰를 제공합니다.

## 일반적인 문제 및 해결 방법
- **PDF가 비어 있음** – `dataDir` 경로가 파일 구분자(`/` 또는 `\`)로 끝나고 디렉터리가 존재하는지 확인하십시오.  
- **눈금이 여전히 표시됨** – 두 티어 모두에서 `setShowTicks(false)`가 호출되었는지 확인하십시오.  
- **기간이 적용되지 않음** – 기간을 생성할 때 `TimeUnitType.Hour`(또는 적절한 단위)를 사용하고 있는지 확인하십시오.  

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 대규모 프로젝트 파일을 처리할 수 있나요?**  
A: 예, 이 라이브러리는 방대한 프로젝트 데이터를 고성능으로 처리하도록 최적화되었습니다.

**Q: Aspose.Tasks for Java가 다양한 Java IDE와 호환되나요?**  
A: 물론입니다 – Eclipse, IntelliJ IDEA, NetBeans 및 기타 인기 IDE와 원활하게 작동합니다.

**Q: 시간 눈금 설정 외에도 간트 차트의 외관을 사용자 정의할 수 있나요?**  
A: 예, Aspose.Tasks는 막대 색상, 글꼴, 그리드 라인 등 다양한 스타일 옵션을 제공합니다.

**Q: Aspose.Tasks for Java용 체험 버전이 있나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험 버전을 받을 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: Aspose.Tasks 포럼 [여기](https://forum.aspose.com/c/tasks/15)에서 지원 및 도움을 받을 수 있습니다.

**Q: 프로그래밍 방식으로 간트 차트의 배경 색상을 변경하려면 어떻게 해야 하나요?**  
A: `java.awt.Color`를 가져온 후 `view.getGanttChartProperties().setBackgroundColor(Color)` 메서드를 사용합니다.

## 결론
이 단계들을 따라 하면 **프로젝트 PDF 만들기** 파일을 완전히 맞춤화된 간트 차트 시간 눈금으로 생성하고, **프로젝트 시각화**를 개선하며, Aspose.Tasks for Java를 사용해 **프로젝트를 PDF로 저장**하는 방법을 배웠습니다. 이 접근 방식은 시각적 출력에 대한 완전한 제어를 제공하여 팀이나 클라이언트와 명확하고 전문적인 일정을 쉽게 공유할 수 있게 합니다.

---

**마지막 업데이트:** 2026-03-29  
**테스트 환경:** Aspose.Tasks for Java (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}