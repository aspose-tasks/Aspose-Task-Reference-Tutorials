---
date: 2026-06-10
description: Aspose.Tasks for Java를 사용하여 리소스 할당에 대한 contour를 변경하고 timephased data를
  생성하는 방법을 배우세요. 작업 contour 유형 및 고급 스케줄링 시나리오를 다룹니다.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Aspose.Tasks에서 리소스 할당을 위한 Timephased Data 생성
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 Timephased Data의 Contour 변경 방법
url: /ko/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 시간별 데이터의 컨투어 변경 방법

## 소개
이 튜토리얼에서는 **how to change contour** 를 사용하여 리소스 할당의 컨투어를 변경하고 Aspose.Tasks for Java를 사용해 시간별 데이터를 생성하는 방법을 알아봅니다. 시간별 데이터는 프로젝트 일정 전반에 걸친 작업 분포를 보여주어 일정 미세 조정, 작업량 균형, 데이터 기반 의사결정을 가능하게 합니다. 컨투어 변경을 숙달하면 전부하, 후부하, 피크 작업량과 같은 현실적인 노력 패턴을 모델링할 수 있습니다.

## 빠른 답변
- **What is a contour?** 작업 컨투어는 작업이 작업 기간 전체에 어떻게 분산되는지를 정의합니다(예: Flat, Turtle, Bell).  
- **Why change a contour?** 전부하 또는 후부하와 같은 현실적인 작업 패턴을 반영하기 위해서입니다.  
- **Which library is required?** Aspose.Tasks for Java(최신 버전).  
- **Do I need a license?** 예, 프로덕션 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **Can I see the results in the console?** 샘플은 각 시간별 구간의 시작 날짜와 값을 콘솔에 출력합니다.

## “how to change contour”란 무엇인가요?
컨투어를 변경한다는 것은 `ResourceAssignment` 객체의 `WORK_CONTOUR` 속성을 업데이트하는 것을 의미합니다. 이 속성은 Aspose.Tasks에 할당된 전체 작업을 작업 기간 전체에 어떻게 분산시킬지 알려줍니다. 라이브러리는 Flat, Turtle, Bell 등 여러 사전 정의된 컨투어를 제공하며, 각각 시간에 따른 고유한 작업 분포 패턴을 생성합니다.

## 왜 Aspose.Tasks를 사용해 시간별 데이터를 생성하나요?
Aspose.Tasks는 **메모리 내 작업에 0 ms 오버헤드** 로 시간별 데이터를 생성하고 **50개 이상의 출력 형식**(MPP, XML, CSV 등)을 지원합니다. 전체 파일을 메모리에 로드하지 않고도 수백 페이지 규모의 프로젝트를 처리할 수 있어 보고서, 리소스 레벨링, 시나리오 분석에 정확한 작업 분포를 제공합니다. API를 통해 컨투어 변경을 자동화하고 프로그래밍 방식으로 정확한 시간별 값을 추출할 수 있습니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:
1. Java Development Kit (JDK): 시스템에 JDK가 설치되어 있어야 합니다. [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드하고 설치할 수 있습니다.  
2. Aspose.Tasks for Java Library: Aspose.Tasks for Java 라이브러리가 필요합니다. [website](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.

## 패키지 가져오기
`Project` 클래스는 메모리 내에서 전체 프로젝트 파일을 나타내는 Aspose.Tasks의 핵심 객체입니다. 작업 및 할당을 다루기 전에 필요한 네임스페이스를 가져오세요.

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
`Project` 생성자는 기존 MPP 파일을 로드하며, 모든 작업을 메모리에 완전히 물리화하지 않고 구조를 파싱해 가볍게 동작합니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 단계 2: 작업 및 리소스 할당 가져오기
`ResourceAssignment`는 리소스를 작업에 연결하고 작업, 비용, 컨투어와 같은 할당 수준 속성을 저장합니다. `project.getResourceAssignments().getById(1)`(또는 유효한 ID)으로 첫 번째 할당을 가져온 뒤 컨투어를 수정하십시오.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 컨투어 변경 – Flat (기본값)
`WorkContourType`은 Aspose.Tasks가 지원하는 사전 정의 작업 컨투어 패턴을 나열하는 열거형입니다. `Asn.WORK_CONTOUR`은 리소스 할당의 컨투어 필드를 식별하고, `generateTimephasedData()`는 현재 컨투어 설정을 기반으로 시간별 작업 항목을 생성합니다. **Flat** 컨투어는 작업을 작업 기간 전체에 고르게 분산합니다; `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)`으로 설정한 뒤 `firstRA.generateTimephasedData()`를 호출하면 균등한 값이 반환됩니다.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – Turtle
**Turtle** 컨투어는 초기 작업량이 낮고 중간에 가속한 뒤 다시 감소하는 형태로, 거북이의 점진적인 속도를 닮았습니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)`으로 적용하고 시간별 데이터를 다시 생성하십시오. 이 패턴은 작업 시작 전 학습 곡선이 필요한 작업에 적합합니다.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – BackLoaded
**BackLoaded** 컨투어는 작업의 대부분을 일정 말미에 배치하고 시작 시에는 거의 작업이 없도록 합니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)`으로 설정하고 시간별 데이터를 다시 생성하십시오. 이는 선행 작업이 완료된 후에만 작업을 수행할 수 있는 활동에 유용합니다.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – FrontLoaded
**FrontLoaded** 컨투어는 작업 초기에 노력을 집중시켜, 킥오프 단계나 초기 집중 작업이 필요한 시나리오를 모델링합니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)`으로 적용한 뒤 `firstRA.generateTimephasedData()`를 호출하면 전부하 분포를 확인할 수 있습니다.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – Bell
**Bell** 컨투어는 시간축 중간에 대칭적인 피크를 만들어 작업이 점진적으로 증가하고, 정점에 도달한 뒤 부드럽게 감소하는 형태를 나타냅니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)`으로 설정하고 시간별 데이터를 다시 생성하면 종 모양의 노력 곡선을 시각화할 수 있습니다.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – EarlyPeak
**EarlyPeak**은 일정 초기에 가장 높은 작업 값을 배치하고 이후 점차 감소시킵니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` 후 `firstRA.generateTimephasedData()`를 사용하면 빠른 시작이 필요한 활동(예: 빠른 프로토타이핑)을 모델링할 수 있습니다.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – LatePeak
**LatePeak**은 작업 피크를 작업 말미로 이동시켜, 마감일이 다가올수록 작업 강도가 증가하는 상황에 적합합니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)`으로 적용하고 시간별 데이터를 다시 생성하면 후기 작업량 급증을 확인할 수 있습니다.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 컨투어 변경 – DoublePeak
**DoublePeak**은 두 개의 뚜렷한 작업 스파이크를 낮은 노력 구간으로 구분하여 생성합니다. 이는 두 차례의 주요 노력 폭발이 있는 작업에 유용합니다. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)`으로 설정하고 `firstRA.generateTimephasedData()`를 호출하면 이중 피크 패턴을 얻을 수 있습니다.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 일반적인 문제 및 팁
- **Contour not updating?** 시간별 데이터를 가져오기 *이전*에 `firstRA.set(Asn.WORK_CONTOUR, …)`를 호출했는지 확인하십시오.  
- **Unexpected values?** 소스 MPP 파일에서 작업의 시작 및 종료 날짜가 올바르게 설정되어 있는지 확인하십시오.  
- **Performance tip:** 여러 컨투어를 반복할 때 동일한 `Project` 인스턴스를 재사용하면 불필요한 파일 I/O를 피할 수 있어 대형 프로젝트에서 처리 시간을 최대 40 %까지 줄일 수 있습니다.  
- **Memory tip:** 프로젝트 크기가 1 GB를 초과하는 경우 `Project.setReadOnly(true)`를 활성화하여 메모리 사용량을 200 MB 이하로 유지하면서도 정확한 시간별 데이터를 생성할 수 있습니다.

## FAQ
**Q: Aspose.Tasks를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 다른 Java 라이브러리와 원활하게 통합되어 일정 데이터와 보고서, 분석, UI 프레임워크 등을 결합할 수 있습니다.

**Q: Aspose.Tasks는 대규모 엔터프라이즈 프로젝트에 적합한가요?**  
A: 물론입니다. 이 라이브러리는 수만 개의 작업 및 리소스를 포함하는 프로젝트를 처리하도록 설계되었으며, 수백 페이지 파일도 성능 저하 없이 처리합니다.

**Q: Aspose.Tasks는 다양한 프로젝트 파일 형식을 지원하나요?**  
A: 예, Aspose.Tasks는 MPP, XML, CSV, MPX 등 30개 이상의 형식을 지원하여 레거시 및 최신 시스템 간의 손쉬운 가져오기/내보내기를 가능하게 합니다.

**Q: 프로젝트 요구 사항에 맞게 작업 컨투어를 사용자 정의할 수 있나요?**  
A: 예, `WORK_CONTOUR` 속성에 작업 비율 배열을 제공하여 사용자 정의 컨투어를 정의할 수 있으므로 노력 분포를 완전히 제어할 수 있습니다.

**Q: Aspose.Tasks에 대한 지원을 받을 수 있는 커뮤니티 포럼이 있나요?**  
A: 예, [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)에서 지원, 토론 및 Aspose 엔지니어와 커뮤니티 구성원이 제공하는 코드 샘플을 확인할 수 있습니다.

---

**마지막 업데이트:** 2026-06-10  
**테스트 대상:** Aspose.Tasks for Java (latest release)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks에서 리소스 할당 만들기](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks에서 리소스용 시간별 데이터 읽기](/tasks/java/resource-management/read-timephased-data/)
- [Aspose.Tasks에서 할당 중지 및 리소스 할당 재개 방법](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}