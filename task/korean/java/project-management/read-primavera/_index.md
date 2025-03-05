---
title: Java용 Aspose.Tasks를 사용하여 Primavera에서 MS 프로젝트 읽기
linktitle: Aspose.Tasks에서 Primavera의 프로젝트 읽기
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks를 사용하여 Primavera XML에서 MS 프로젝트 파일을 원활하게 읽는 방법을 알아보세요. 프로젝트 관리 효율성을 향상시키세요.
type: docs
weight: 20
url: /ko/java/project-management/read-primavera/
---
## 소개
프로젝트 관리에서 서로 다른 소프트웨어 플랫폼 간의 상호 운용성은 원활한 작업 흐름을 위해 매우 중요합니다. Aspose.Tasks for Java는 Primavera XML에서 Microsoft Project 파일을 읽을 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 Primavera에서 MS 프로젝트 파일을 읽는 과정을 안내하므로 작업의 Primavera 관련 속성을 효율적으로 검사할 수 있습니다.
## 전제조건
계속하기 전에 다음 필수 구성 요소가 설치 및 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 반드시 교체하세요`"Your Data Directory"` 데이터 디렉터리의 실제 경로를 사용합니다.
## 2단계: Primavera XML에서 프로젝트 읽기
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 반드시 교체하세요`"PrimaveraProject.xml"` Primavera XML 파일의 실제 이름을 사용하세요.
## 3단계: 작업 반복 및 Primavera 관련 속성 검색
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
이 코드는 프로젝트의 각 작업을 반복하여 관련 Primavera 관련 속성을 인쇄합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Primavera XML에서 MS 프로젝트 파일을 읽는 방법을 배웠습니다. 이 기능을 사용하면 다양한 플랫폼에서 프로젝트 데이터를 원활하게 통합하고 분석할 수 있어 전반적인 프로젝트 관리 효율성이 향상됩니다.
## FAQ
### Q: Aspose.Tasks for Java를 사용하여 작업의 Primavera 관련 속성을 수정할 수 있습니까?
A: 예, Aspose.Tasks for Java는 필요에 따라 작업의 Primavera 관련 속성을 수정할 수 있는 API를 제공합니다.
### Q: Java용 Aspose.Tasks는 다른 프로젝트 파일 형식 읽기를 지원합니까?
A: 예, Aspose.Tasks for Java는 MPP, XML, Primavera XML을 포함한 다양한 프로젝트 파일 형식 읽기를 지원합니다.
### Q: Aspose.Tasks for Java는 엔터프라이즈급 프로젝트 관리 애플리케이션에 적합합니까?
A: 물론 Aspose.Tasks for Java는 강력한 기능과 확장성을 제공하므로 엔터프라이즈 수준의 프로젝트 관리 애플리케이션에 적합합니다.
### Q: Aspose.Tasks for Java를 사용하여 Primavera 프로젝트에서 리소스 정보를 추출할 수 있나요?
A: 예, Aspose.Tasks for Java를 사용하면 Primavera 프로젝트의 작업 세부 정보와 함께 리소스 정보를 추출할 수 있습니다.
### Q: Aspose.Tasks for Java에 대한 추가 지원이나 문서는 어디서 찾을 수 있나요?
 A: 다음에서 포괄적인 문서를 찾아보고 지원을 위한 포럼에 액세스할 수 있습니다.[Aspose.Tasks for Java 문서](https://reference.aspose.com/tasks/java/) 페이지.