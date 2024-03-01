---
title: Aspose.Tasks에서 MS 프로젝트 속성을 효율적으로 관리
linktitle: Aspose.Tasks에서 기본 프로젝트 속성 관리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 기본 MS 프로젝트 속성을 관리하는 방법을 알아보세요. 프로젝트 관리 워크플로를 손쉽게 간소화하세요.
type: docs
weight: 11
url: /ko/java/project-management/default-properties/
---
## 소개
Aspose.Tasks for Java를 사용하여 프로젝트 관리 프로세스를 간소화하고 싶으십니까? Microsoft Project 파일의 기본 속성을 관리하면 효율성이 크게 향상될 수 있습니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 기본 MS 프로젝트 속성을 관리하는 방법에 대한 단계별 지침을 안내합니다.
## 전제조건
튜토리얼을 자세히 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. 자바 개발 키트(JDK)
   - 시스템에 JDK가 설치되어 있는지 확인하십시오.
   -  다음에서 다운로드할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Java 라이브러리용 Aspose.Tasks
   - 프로젝트에 Aspose.Tasks for Java 라이브러리를 다운로드하고 포함하세요.
   -  다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
먼저 Java 파일에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 2단계: 기본 속성 표시
```java
// 기본 속성 표시
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## 3단계: 기본 속성 설정
```java
// 기본 속성 설정
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## 4단계: 프로젝트를 XML 형식으로 저장
```java
// 프로젝트를 XML 형식으로 저장
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## 5단계: 결과 표시
```java
// 변환 결과를 표시합니다.
System.out.println("Process completed Successfully");
```
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 기본 MS 프로젝트 속성을 효율적으로 관리할 수 있습니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 기본 MS 프로젝트 속성을 관리하는 방법을 배웠습니다. 이러한 기술을 활용하면 프로젝트 관리 워크플로를 최적화하여 생산성과 구성을 향상할 수 있습니다.
## FAQ
### Q1: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A1: 예, Aspose.Tasks는 .NET, Python 및 Java와 같은 다양한 프로그래밍 언어를 지원합니다.
### Q2: Aspose.Tasks는 개인용과 기업용 모두에 적합합니까?
A2: 물론이죠! 소규모 개인 프로젝트를 관리하든 대규모 기업 이니셔티브를 관리하든 Aspose.Tasks는 모든 것을 충족시켜줍니다.
### Q3: Aspose.Tasks는 고객 지원을 제공합니까?
답변 3: 예, 다음 웹사이트에서 도움과 커뮤니티 지원을 찾을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q4: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?
 A4: 물론이죠! 무료 평가판을 이용하실 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Q5: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 A5: 임시 면허는 다음 기관에서 받을 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로.