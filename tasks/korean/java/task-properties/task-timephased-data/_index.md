---
title: Aspose.Tasks의 작업 시간대별 데이터
linktitle: Aspose.Tasks의 작업 시간대별 데이터
second_title: Aspose.Tasks 자바 API
description: Java 및 마스터 작업의 시간대별 데이터 관리를 위한 Aspose.Tasks를 살펴보세요. 라이브러리를 다운로드하고, 무료 평가판을 즐기고, 프로젝트 추적을 간소화하세요.
weight: 34
url: /ko/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 작업 시간대별 데이터

## 소개
프로젝트 관리 영역에서는 효율적인 프로젝트 실행을 위해 작업 시간대별 데이터를 정확하게 추적하는 것이 중요합니다. Aspose.Tasks for Java는 강력한 기능과 유연성을 제공하여 이 프로세스를 간소화하는 강력한 도구로 등장합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 활용하여 작업 시간대별 데이터를 효과적으로 관리하는 방법을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오.
-  Java 라이브러리용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하여 프로젝트에 포함하세요. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
- 문서 디렉터리: 프로젝트 문서에 대한 디렉터리를 설정합니다.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## 1단계: 프로젝트 시작 날짜 설정
```java
Project project = new Project(dataDir + "project.xml");
// 패키지 가져오기를 위한 추가 코드
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
설명: 달력 객체를 초기화하고 시작 날짜를 설정한 후 프로젝트에 적용합니다.
## 2단계: 작업 및 자원 정의
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
설명: 작업 및 자원을 생성하고 표준 및 초과 근무 수당을 설정합니다.
## 3단계: 작업 기간 설정
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
설명: 작업 기간을 정의합니다(예: 6일).
## 4단계: 작업에 자원 할당
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
설명: 태스크에 자원을 지정하십시오.
## 5단계: 자원 할당 구성
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
설명: 자원 할당에 대해 중지, 재개, 작업 윤곽 등의 매개변수를 설정합니다.
## 6단계: 기준선 설정
```java
project.setBaseline(BaselineType.Baseline);
```
설명: 프로젝트의 기준선을 설정하십시오.
## 7단계: 작업 완료 업데이트
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
설명: 태스크의 완료율을 표시합니다.
## 8단계: 시간대별 데이터 검색
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
설명: 남은 작업 할당에 대한 시간대별 데이터를 검색합니다.
## 9단계: 시간대별 데이터 표시
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// 다른 값을 표시하기 위한 추가 코드
```
설명: 시간대별 데이터를 출력하여 표시합니다.
## 결론
프로젝트 성공을 위해서는 작업 시간대별 데이터를 효과적으로 관리하는 것이 필수입니다. Aspose.Tasks for Java는 포괄적인 기능 세트를 제공하여 이 프로세스를 단순화합니다. 이 튜토리얼을 따르면 Aspose.Tasks를 Java 프로젝트에 원활하게 통합하여 프로젝트 타임라인과 리소스 할당을 정확하게 제어할 수 있습니다.
## 자주 묻는 질문
### Q: 모든 Java 프로젝트에서 Java용 Aspose.Tasks를 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 모든 Java 기반 프로젝트와 호환됩니다.
### Q: Java용 Aspose.Tasks에 대한 추가 지원은 어디서 찾을 수 있나요?
 답: 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 지원과 토론을 위해.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 무료 평가판을 사용해 볼 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 임시 라이센스를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Java용 Aspose.Tasks는 어디에서 구매할 수 있나요?
 A: Java용 Aspose.Tasks를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
