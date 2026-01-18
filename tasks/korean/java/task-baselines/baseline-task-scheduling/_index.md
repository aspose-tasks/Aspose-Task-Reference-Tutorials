---
date: 2026-01-18
description: Aspose.Tasks for Java를 사용하여 프로젝트 관리 기준선을 일정에 반영하는 방법을 배우고, 이를 통해 프로젝트
  기준선을 관리하고 계획 대비 실제 진행 상황을 비교할 수 있습니다.
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트 관리 기준 – Aspose.Tasks를 활용한 작업 일정 관리
url: /ko/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 관리 기준선 – Aspose.Tasks를 활용한 작업 일정 관리

## 프로젝트 관리 기준선 소개
**프로젝트 관리 기준선**을 관리하는 것은 효과적인 프로젝트 관리의 핵심입니다. 이를 통해 원래 계획을 캡처하고 나중에 **계획 대비 실제 진행 상황**을 비교하여 변동을 조기에 파악할 수 있습니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용해 작업 기준선을 일정에 반영하는 방법을 단계별로 안내하며, **프로젝트 기준선을** 자신 있게 관리하고 프로젝트를 정상 궤도에 유지할 수 있는 도구를 제공합니다.

## 빠른 답변
- **프로젝트 관리 기준선은 무엇을 나타내나요?**  
  기준선은 나중에 편차 분석을 위해 원래 일정, 비용 및 범위를 기록합니다.  
- **Java에서 기준선 일정을 처리하는 라이브러리는?**  
  Aspose.Tasks for Java는 기준선을 생성하고 관리하기 위한 강력한 API를 제공합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?**  
  테스트용 무료 체험판으로 실행할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다.  
- **주요 전제 조건은 무엇입니까?**  
  Java Development Kit (JDK)와 Aspose.Tasks for Java 라이브러리.  
- **기준선 날짜를 설정 후 확인할 수 있나요?**  
  네—`TaskBaseline` 객체를 사용해 시작, 종료 및 기간 값을 읽을 수 있습니다.

## 프로젝트 관리 기준선이란?
프로젝트 관리 기준선은 실행 초기에 승인된 프로젝트 일정, 예산 및 범위의 버전을 캡처한 것입니다. 이는 프로젝트 전반에 걸쳐 성과를 측정하고 편차를 식별하는 기준점으로 활용됩니다.

## 왜 Aspose.Tasks를 사용해 기준선 일정을 잡나요?
Aspose.Tasks는 Microsoft Project가 설치되지 않은 순수 Java API를 제공합니다. 이를 통해 **프로젝트 인스턴스를 생성하고**, 작업을 정의하며, 기준선을 설정하고, 기준선 정보를 프로그래밍 방식으로 가져올 수 있어 자동 보고서 작성이나 맞춤형 PM 도구와의 통합에 이상적입니다.

## 전제 조건
시작하기 전에 아래 항목이 준비되어 있는지 확인하세요.

### Java Development Environment
시스템에 Java Development Kit (JDK)가 설치되어 있는지 확인하십시오. JDK는 [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드 및 설치할 수 있습니다.

### Aspose.Tasks for Java Library
Aspose.Tasks for Java 라이브러리를 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드하고 Java 프로젝트에 포함시키세요.

## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것으로 시작합니다:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

이제 제공된 예제를 여러 단계로 나누어 살펴보겠습니다:

## 단계 1: 새 프로젝트 인스턴스 만들기
```java
Project project = new Project();
```

## 단계 2: 작업 정의 및 기준선 설정
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 단계 3: 기준선 정보 접근
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 단계 4: 기준선 기간 표시
```java
System.out.println(baseline.getDuration().toString());
```

## 단계 5: 기준선 시작 날짜 표시
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 단계 6: 기준선 종료 날짜 표시
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

이 단계들을 따라 하면 Aspose.Tasks for Java를 활용해 **프로젝트 기준선**을 효과적으로 관리할 수 있습니다.

## 일반적인 문제 및 해결책
- **Baseline not set:** 작업을 추가한 **후에** `project.setBaseline(BaselineType.Baseline)`을 호출했는지 확인하세요. 그렇지 않으면 기준선 컬렉션이 비어 있습니다.  
- **Null values:** `task.getBaselines()`가 빈 리스트를 반환한다면, 기준선을 설정하기 전에 작업이 프로젝트 계층에 추가되었는지 확인하십시오.  
- **Date format:** `getStart()`와 `getFinish()` 메서드는 `Date` 객체를 반환합니다. 사용자 정의 표시 형식이 필요하면 포맷터를 사용하세요.

## FAQ
### Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
네, Aspose.Tasks for Java는 다양한 복잡도의 프로젝트를 효율적으로 관리할 수 있는 강력한 기능을 제공합니다.

### Aspose.Tasks for Java가 다른 Java 라이브러리와 호환되나요?
물론입니다. Aspose.Tasks for Java는 다른 Java 라이브러리와 원활히 통합되어 프로젝트 관리 기능을 확장합니다.

### Aspose.Tasks for Java를 사용해 작업 기준선을 맞춤 설정할 수 있나요?
예, Aspose.Tasks for Java는 프로젝트 요구 사항에 맞게 작업 기준선을 맞춤 설정하고 관리할 수 있는 광범위한 기능을 제공합니다.

### Aspose.Tasks for Java의 체험판이 있나요?
네, [release page](https://releases.aspose.com/)에서 Aspose.Tasks for Java의 무료 체험판을 이용할 수 있습니다.

### Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?
문의 사항이나 도움이 필요하면 Aspose.Tasks 포럼을 방문하세요: [here](https://forum.aspose.com/c/tasks/15).

## 자주 묻는 질문

**Q: Aspose.Tasks에서 새 프로젝트 인스턴스를 어떻게 만들나요?**  
A: `Project` 클래스를 인스턴스화합니다 (`Project project = new Project();`). 이렇게 하면 작업 및 기준선을 추가할 준비가 된 새로운 프로젝트 파일이 생성됩니다.

**Q: `BaselineType.Baseline`과 다른 기준선 유형의 차이는 무엇인가요?**  
A: `BaselineType.Baseline`은 기본 기준선(기준선 1)을 의미합니다. Aspose.Tasks는 추가 스냅샷을 위해 Baseline 2‑10도 지원합니다.

**Q: 기준선 데이터를 Excel이나 CSV로 내보낼 수 있나요?**  
A: 네, `TaskBaseline` 객체를 순회하면서 값을 CSV 파일에 기록하면 표준 Java I/O를 사용해 내보낼 수 있습니다.

**Q: 기준선을 설정하면 기존 작업 날짜에 영향을 주나요?**  
A: 기준선을 설정하면 현재 날짜가 캡처되지만 작업의 실제 일정은 변경되지 않습니다. 기준선 설정 후에도 시작/종료 날짜를 조정할 수 있습니다.

**Q: 프로그래밍 방식으로 여러 기준선을 비교할 수 있나요?**  
A: 물론입니다. `task.getBaselines().get(index)`를 통해 각 기준선을 가져와 `Start`, `Finish`, `Duration` 속성을 비교하면 됩니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose