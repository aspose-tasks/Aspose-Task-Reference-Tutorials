---
title: Aspose.Tasks에서 시간대별 데이터 생성
linktitle: Aspose.Tasks에서 자원 할당을 위한 시간대별 데이터 생성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 리소스 할당을 위한 시간대별 데이터를 생성하는 방법을 알아보세요. 이 포괄적인 가이드를 통해 프로젝트 관리 효율성을 향상시키세요.
type: docs
weight: 24
url: /ko/java/resource-assignments/timephased-data-generation/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 리소스 할당을 위한 시간대별 데이터를 생성하는 프로세스를 안내합니다. 시간대별 데이터는 프로젝트 내에서 시간이 지남에 따라 리소스가 할당되는 방식에 대한 귀중한 통찰력을 제공하여 프로젝트 관리자가 정보에 입각한 결정을 내리는 데 도움을 줍니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하십시오. 다음에서 JDK를 다운로드하고 설치할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java 라이브러리: Aspose.Tasks for Java 라이브러리가 필요합니다. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 Aspose.Tasks 작업에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## 1단계: 소스 MPP 파일 읽기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
// 소스 MPP 파일 읽기
Project project = new Project(dataDir + "project.mpp");
```
## 2단계: 작업 및 자원 배정 받기
```java
// 프로젝트의 첫 번째 작업 가져오기
Task task = project.getRootTask().getChildren().getById(1);
// 프로젝트의 첫 번째 자원 배정 받기
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## 3단계: 평면 등고선을 사용하여 시간대별 데이터 생성
```java
// 평평한 윤곽선이 기본 윤곽선입니다.
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 4단계: 윤곽선을 거북이로 변경
```java
// 윤곽선을 거북이로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 5단계: 윤곽선을 BackLoaded로 변경
```java
// 윤곽선을 BackLoaded로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 6단계: 윤곽선을 FrontLoaded로 변경
```java
// 윤곽선을 FrontLoaded로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 7단계: 윤곽선을 종 모양으로 변경
```java
// 윤곽선을 벨로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 8단계: 윤곽선을 EarlyPeak으로 변경
```java
// 윤곽선을 EarlyPeak으로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 9단계: 윤곽선을 LatePeak으로 변경
```java
// 등고선을 LatePeak으로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 10단계: 윤곽선을 DoublePeak으로 변경
```java
// 윤곽선을 DoublePeak으로 변경
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 자원 할당을 위한 시간대별 데이터를 생성하는 방법을 다루었습니다. 다양한 작업 윤곽을 이해하면 프로젝트 관리자가 프로젝트의 리소스 할당 및 일정을 효과적으로 관리하는 데 도움이 될 수 있습니다.
## FAQ
### Aspose.Tasks를 다른 Java 라이브러리와 함께 사용할 수 있나요?
예, Aspose.Tasks는 다른 Java 라이브러리와 통합되어 프로젝트 관리 기능을 향상시킬 수 있습니다.
### Aspose.Tasks는 대규모 기업 프로젝트에 적합합니까?
물론 Aspose.Tasks는 대규모 기업 프로젝트를 포함하여 모든 규모의 프로젝트를 처리하도록 설계되었습니다.
### Aspose.Tasks는 다양한 프로젝트 파일 형식을 지원합니까?
예, Aspose.Tasks는 MPP, XML 및 MPX를 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### 내 프로젝트 요구 사항에 따라 작업 윤곽을 맞춤 설정할 수 있나요?
예, Aspose.Tasks를 사용하면 사용자는 특정 프로젝트 요구 사항에 맞게 사용자 정의 작업 윤곽을 정의할 수 있습니다.
### Aspose.Tasks에 대한 도움을 받을 수 있는 커뮤니티 포럼이 있나요?
 네, 방문하실 수 있습니다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원과 토론을 위해.