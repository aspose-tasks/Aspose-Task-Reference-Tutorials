---
title: Aspose.Tasks에서 평준화 지연 속성 처리
linktitle: Aspose.Tasks에서 자원 할당에 대한 평준화 지연 속성을 처리합니다.
second_title: Aspose.Tasks 자바 API
description: 이 포괄적인 튜토리얼을 통해 Java용 Aspose.Tasks에서 리소스 할당에 대한 평준화 지연 속성을 처리하는 방법을 알아보세요.
type: docs
weight: 17
url: /ko/java/resource-assignments/leveling-delay-properties/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java에서 리소스 할당에 대한 평준화 지연 속성을 처리하는 과정을 안내합니다. Aspose.Tasks는 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java JDK가 설치되어 있는지 확인하십시오. 에서 다운로드하여 설치할 수 있습니다.[웹사이트](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Java 라이브러리용 Aspose.Tasks: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1단계: 프로젝트 객체 생성
 인스턴스화`Project` 물체:
```java
Project prj = new Project();
```
## 2단계: 작업 생성
프로젝트에 작업을 추가합니다.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## 3단계: 작업 시작 날짜 및 기간 설정
작업 시작 날짜와 기간을 설정합니다.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## 4단계: 리소스 추가
프로젝트에 리소스를 추가합니다.
```java
Resource resource = prj.getResources().add("Resource 1");
```
## 5단계: 자원 할당 생성
작업 및 자원에 대한 자원 배정을 생성합니다.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## 6단계: 레벨링 지연 설정
과제에 대한 평준화 지연을 설정합니다.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## 7단계: 결과 표시
평준화 지연 및 기타 관련 정보를 인쇄합니다.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java에서 리소스 할당에 대한 평준화 지연 속성을 처리하는 방법을 배웠습니다. 다음 단계를 수행하면 Java 프로젝트에서 자원 할당을 효율적으로 관리할 수 있습니다.
## FAQ
### Q: Aspose.Tasks를 다른 Java 라이브러리와 함께 사용할 수 있나요?

A: 예, Aspose.Tasks는 다른 Java 라이브러리와 통합되어 프로젝트 관리 기능을 향상시킬 수 있습니다.

### Q: Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?

A: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 환경에서의 호환성을 보장합니다.

### Q: Aspose.Tasks에 대한 추가 지원은 어디서 찾을 수 있나요?

 A: 다음에서 지원과 리소스를 찾을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

### Q: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?

 A: 예, Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/).

### Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A: 임시 라이센스를 요청할 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/) 평가 목적으로.