---
date: 2026-01-10
description: Aspose.Tasks for Java를 사용하여 리소스 할당에 대한 컨투어를 변경하고 시간별 데이터를 생성하는 방법을 배우고,
  프로젝트 관리 효율성을 향상시킵니다.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 시간별 데이터의 컨투어를 변경하는 방법
url: /ko/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 시간 단계 데이터의 컨투어 변경 방법

## 소개
이 튜토리얼에서는 리소스 할당에 대한 **컨투어 변경 방법**을 알아보고 Aspose.Tasks for Java를 사용하여 시간 단계 데이터를 생성하는 방법을 배웁니다. 시간 단계 데이터는 프로젝트 일정 전반에 걸친 작업 분포를 보여주어 일정 미세 조정, 작업 부하 균형 및 데이터 기반 의사 결정을 가능하게 합니다.

## 빠른 답변
- **컨투어란 무엇인가요?** 작업 컨투어는 작업량이 작업 기간에 어떻게 분산되는지를 정의합니다(예: Flat, Turtle, Bell).  
- **왜 컨투어를 변경하나요?** 앞쪽에 작업을 집중하거나 뒤쪽에 집중하는 등 현실적인 작업 패턴을 반영하기 위해서입니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java(최근 버전).  
- **라이선스가 필요합니까?** 네, 실제 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **콘솔에서 결과를 확인할 수 있나요?** 샘플은 각 시간 단계 구간의 시작 날짜와 값을 출력합니다.

## 컨투어 변경이란 무엇인가요?
컨투어를 변경한다는 것은 `ResourceAssignment`의 `WORK_CONTOUR` 속성을 업데이트하는 것을 의미합니다. Aspose.Tasks는 작업이 시간에 따라 할당되는 방식을 결정하는 여러 사전 정의된 컨투어(Flat, Turtle, Bell 등)를 지원합니다.

## 시간 단계 데이터를 생성하기 위해 Aspose.Tasks를 사용하는 이유
- **정확한 보고:** 보고 도구용으로 정확한 작업 분포를 내보냅니다.  
- **시나리오 계획:** 원본 일정을 변경하지 않고 다양한 컨투어를 테스트합니다.  
- **자동화:** CI 파이프라인에 통합하여 프로젝트 상태를 자동으로 검증합니다.

## 전제 조건
시작하기 전에 다음 전제 조건을 확인하십시오:
1. Java Development Kit (JDK): 시스템에 JDK가 설치되어 있는지 확인하십시오. JDK는 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드하고 설치할 수 있습니다.
2. Aspose.Tasks for Java 라이브러리: Aspose.Tasks for Java 라이브러리가 필요합니다. 라이브러리는 [website](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
먼저, Aspose.Tasks와 작업하기 위해 필요한 패키지를 가져오겠습니다:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## 단계 1: 소스 MPP 파일 읽기
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 단계 2: 작업 및 리소스 할당 가져오기
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 컨투어 변경 방법 – Flat (기본값)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 방법 – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 일반적인 문제 및 팁
- **컨투어가 업데이트되지 않나요?** 시간 단계 데이터를 *이전*에 `firstRA.set(Asn.WORK_CONTOUR, …)`를 호출했는지 확인하십시오.
- **예상치 못한 값이 나오나요?** 소스 MPP에서 작업의 시작 및 종료 날짜가 올바르게 설정되어 있는지 확인하십시오.
- **성능 팁:** 여러 컨투어를 반복할 때 불필요한 파일 I/O를 피하기 위해 동일한 `Project` 인스턴스를 재사용하십시오.

## FAQ
### 다른 Java 라이브러리와 Aspose.Tasks를 함께 사용할 수 있나요?
네, Aspose.Tasks는 다른 Java 라이브러리와 통합하여 프로젝트 관리 기능을 강화할 수 있습니다.

### Aspose.Tasks가 대규모 엔터프라이즈 프로젝트에 적합한가요?
물론입니다. Aspose.Tasks는 대규모 엔터프라이즈 프로젝트를 포함한 모든 규모의 프로젝트를 처리하도록 설계되었습니다.

### Aspose.Tasks가 다양한 프로젝트 파일 형식을 지원하나요?
네, Aspose.Tasks는 MPP, XML, MPX 등 다양한 형식을 지원합니다.

### 프로젝트 요구사항에 맞게 작업 컨투어를 사용자 정의할 수 있나요?
네, 특정 일정 요구에 맞게 사용자 정의 작업 컨투어를 정의할 수 있습니다.

### Aspose.Tasks에 대한 도움을 받을 수 있는 커뮤니티 포럼이 있나요?
네, 지원 및 토론을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문할 수 있습니다.

---

**마지막 업데이트:** 2026-01-10  
**테스트 환경:** Aspose.Tasks for Java (latest release)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}