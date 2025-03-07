---
title: Aspose.Tasks에서 작업 데이터를 MPP 형식으로 업데이트합니다.
linktitle: Aspose.Tasks에서 작업 데이터를 MPP 형식으로 업데이트합니다.
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 작업 데이터를 MPP 형식으로 업데이트하는 방법을 알아보세요. 효율적인 프로젝트 관리를 위한 단계별 가이드를 따르세요.
weight: 35
url: /ko/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 데이터를 MPP 형식으로 업데이트합니다.

## 소개
Aspose.Tasks for Java를 사용하여 작업 데이터를 MPP 형식으로 업데이트하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 각 단계를 명확하게 이해할 수 있도록 프로세스를 안내합니다. Aspose.Tasks for Java는 Microsoft Project 파일 작업을 위한 강력한 솔루션을 제공하며, 이 가이드가 끝나면 MPP 형식의 작업 데이터를 효율적으로 업데이트할 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  Java용 Aspose.Tasks: Aspose.Tasks 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/tasks/java/).
- JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
- 통합 개발 환경(IDE): Java 개발을 위해 원하는 IDE를 사용하세요.
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요. 다음 스니펫은 패키지를 가져오는 방법을 보여줍니다.
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. 초기 작업 생성 및 구성
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (나머지 코드 계속)
```
## 2. 시작 날짜 및 기간 설정
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (나머지 코드 계속)
```
## 3. 요약 작업 만들기
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (나머지 코드 계속)
```
## 4. 마감일 및 작업 메모 설정
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (나머지 코드 계속)
```
## 5. 작업 제약 조건 구성
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (나머지 코드 계속)
```
## 6. 추가 작업 생성
```java
//10개의 새 작업 만들기
for (int i = 0; i < 10; i++) {
    //... (나머지 코드 계속)
}
//... (나머지 코드 계속)
```
## 7. 프로젝트 저장
```java
// 프로젝트 저장
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 작업 데이터를 MPP 형식으로 성공적으로 업데이트했습니다.
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 MPP 형식의 작업 데이터 업데이트에 대한 포괄적인 가이드를 완료했습니다. 이 강력한 라이브러리는 프로젝트 관리 작업을 단순화하여 Java 개발자에게 유용한 도구입니다.
## 자주 묻는 질문
### Q: Java 설명서용 Aspose.Tasks는 어디에서 찾을 수 있나요?
 A: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/tasks/java/).
### Q: Java용 Aspose.Tasks를 어떻게 다운로드할 수 있나요?
 A: 다음에서 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/tasks/java/).
### Q: 무료 평가판이 제공됩니까?
 A: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 A: 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tasks/15).
### Q: 테스트 목적으로 임시 라이선스를 제공합니까?
 A: 네, 임시 면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
