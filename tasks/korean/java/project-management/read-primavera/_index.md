---
date: 2026-04-24
description: Aspose Tasks Java를 사용하여 Primavera XML을 MS Project에 가져오는 방법을 배우고, 원활한
  데이터 교환과 향상된 프로젝트 관리를 실현하세요.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Aspose.Tasks에서 Primavera 프로젝트 읽기
second_title: Aspose.Tasks Java API
title: aspose tasks java – Primavera XML을 MS Project로 읽기
url: /ko/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Primavera에서 Aspose.Tasks for Java를 사용하여 MS Project 읽기

## 소개
오늘날 빠르게 변화하는 프로젝트 관리 환경에서는 Primavera P6와 Microsoft Project 간에 일정을 이동하면서 세부 정보를 잃지 않아야 할 때가 많습니다. 이 튜토리얼에서는 **Primavera XML** 파일을 읽고 **aspose tasks java**를 사용하여 MS Project로 가져오는 방법을 보여줍니다. 가이드를 마치면 Primavera 고유의 작업 속성을 Java 애플리케이션으로 가져와 분석, 보고 또는 추가 자동화를 위한 단일 진실 소스로 활용할 수 있습니다.

## 빠른 답변
- **Aspose.Tasks for Java는 무엇을 하나요?** Primavera XML 및 Microsoft Project (MPP)를 포함한 다양한 프로젝트 파일 형식을 읽고 씁니다.  
- **라이선스가 필요합니까?** 무료 체험판으로 평가할 수 있지만, 실제 사용을 위해서는 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상이 필요합니다.  
- **Primavera XML 외에 다른 형식을 가져올 수 있나요?** 예, aspose tasks java는 MPP, XML 등 다양한 형식을 지원합니다.  
- **이 방법이 대규모 엔터프라이즈 프로젝트에 적합합니까?** 물론입니다—Aspose.Tasks는 고성능 엔터프라이즈 수준 시나리오를 위해 설계되었습니다.

## aspose tasks java – Primavera XML 읽기
Primavera XML을 읽는다는 것은 Oracle Primavera P6에서 내보낸 XML을 파싱하여 프로젝트 일정 데이터(작업, 기간, 리소스 및 Primavera 고유 속성)를 추출하고 이를 Microsoft Project와 같은 다른 도구에서 사용할 수 있도록 하는 것을 의미합니다.

## Primavera XML을 읽기 위해 Aspose.Tasks for Java를 사용하는 이유
- **전체 충실도:** Primavera 고유 속성이 모두 보존됩니다.  
- **외부 종속성 없음:** Pure Java 라이브러리로 Primavera나 MS Project 설치가 필요 없습니다.  
- **확장성:** 수천 개의 작업을 가진 대규모 프로젝트도 효율적으로 처리합니다.  
- **크로스 플랫폼:** Windows, Linux, macOS에서 작동합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하십시오:
1. **Java Development Kit (JDK)** – Java 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [here](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. 읽고자 하는 Primavera XML 파일(예: `PrimaveraProject.xml`).

## Aspose.Tasks를 사용하여 Java에서 프로젝트 파일을 읽는 방법
아래는 전체 과정을 단계별로 안내하는 가이드입니다.

### 패키지 가져오기
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### 단계 1: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 Primavera XML 파일이 위치한 절대 경로로 교체하십시오.

### 단계 2: Primavera XML에서 프로젝트 읽기
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
`"PrimaveraProject.xml"`을 실제 Primavera 내보내기 파일명으로 업데이트하십시오.

### 단계 3: 작업을 순회하며 Primavera 고유 속성 가져오기
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
이 루프는 각 작업의 Primavera 고유 세부 정보(예: Activity ID, WBS 순서, 기간 유형, 비용 분류 등)를 출력합니다.

## 일반적인 문제 및 해결책
- **파일을 찾을 수 없음 오류:** `dataDir`이 경로 구분자(`/` 또는 `\\`)로 끝나는지, XML 파일명이 정확한지 확인하십시오.  
- **Primavera 속성 누락:** XML이 모든 필수 필드와 함께 내보내졌는지 확인하십시오; 오래된 Primavera 버전은 일부 속성을 생략할 수 있습니다.  
- **대용량 파일 성능:** 수만 개 작업이 있는 프로젝트의 경우 JVM 힙 크기(`-Xmx2g` 이상)를 늘리는 것을 고려하십시오.

## 자주 묻는 질문
### Q: Aspose.Tasks for Java를 사용하여 작업의 Primavera 고유 속성을 수정할 수 있나요?
A: 예, Aspose.Tasks for Java는 필요에 따라 작업의 Primavera 고유 속성을 수정할 수 있는 API를 제공합니다.

### Q: Aspose.Tasks for Java가 다른 프로젝트 파일 형식 읽기를 지원합니까?
A: 예, Aspose.Tasks for Java는 MPP, XML, Primavera XML 등 다양한 프로젝트 파일 형식 읽기를 지원합니다.

### Q: Aspose.Tasks for Java가 엔터프라이즈 수준 프로젝트 관리 애플리케이션에 적합합니까?
A: 물론입니다. Aspose.Tasks for Java는 강력한 기능과 확장성을 제공하여 엔터프라이즈 수준 프로젝트 관리 애플리케이션에 적합합니다.

### Q: Aspose.Tasks for Java를 사용하여 Primavera 프로젝트에서 리소스 정보를 추출할 수 있나요?
A: 예, Aspose.Tasks for Java는 Primavera 프로젝트에서 작업 세부 정보와 함께 리소스 정보를 추출할 수 있습니다.

### Q: Aspose.Tasks for Java에 대한 추가 지원이나 문서는 어디에서 찾을 수 있나요?
A: 자세한 문서와 포럼 지원은 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 페이지에서 확인할 수 있습니다.

## 결론
이제 **Primavera XML** 파일을 읽고 **aspose tasks java**를 사용하여 Java 애플리케이션으로 상세 작업 정보를 가져오는 방법을 배웠습니다. 이 기능은 Primavera와 Microsoft Project 간의 격차를 메우고 플랫폼 전반에 걸친 가시성을 제공하며 전체 프로젝트 관리 효율성을 높입니다.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}