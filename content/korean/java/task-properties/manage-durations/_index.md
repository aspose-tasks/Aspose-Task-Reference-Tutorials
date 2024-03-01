---
title: Aspose.Tasks에서 작업 기간 관리
linktitle: Aspose.Tasks에서 작업 기간 관리
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks를 살펴보고 작업 기간을 손쉽게 관리하는 방법을 알아보세요. 효과적인 프로젝트 계획 및 실행을 위한 단계별 가이드를 따르세요.
type: docs
weight: 20
url: /ko/java/task-properties/manage-durations/
---
## 소개
Aspose.Tasks for Java는 프로젝트 작업 및 기간을 효율적으로 관리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 작업 기간을 관리하는 방법을 살펴보고 각 단계를 안내합니다. 숙련된 개발자이든 초보자이든 이 가이드는 프로젝트에서 작업 기간 작업의 필수 사항을 파악하는 데 도움이 됩니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  JDK(Java Development Kit): 컴퓨터에 Java가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks 라이브러리: Aspose.Tasks 라이브러리를 다운로드하여 프로젝트에 포함합니다. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks 작업에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 1단계: 프로젝트 설정
```java
// 새 프로젝트 만들기
Project project = new Project();
```
## 2단계: 새 작업 추가
```java
// 프로젝트에 새 작업 추가
Task task = project.getRootTask().getChildren().add("Task");
```
## 3단계: 작업 기간 가져오기 및 변환
```java
// 일 단위로 작업 기간 가져오기(기본 시간 단위)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// 기간을 시간 단위로 변환
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## 4단계: 작업 기간을 1주로 업데이트
```java
// 작업 기간을 1주로 늘립니다.
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## 5단계: 작업 기간 줄이기
```java
// 작업 기간 줄이기
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
다음 단계를 수행하면 Aspose.Tasks for Java 프로젝트의 작업 기간을 성공적으로 관리할 수 있습니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 작업 기간을 관리하는 기본 사항을 다루었습니다. 이제 효과적인 작업 기간 관리를 위해 이러한 기술을 프로젝트에 자신있게 통합할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 모든 Java 버전과 호환됩니까?
Aspose.Tasks는 Java 6 이상 버전과 호환됩니다.
### 상업용 프로젝트에 Aspose.Tasks를 사용할 수 있나요?
 예, 개인 및 상업 프로젝트 모두에 Aspose.Tasks를 사용할 수 있습니다. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 세부정보를 확인하세요.
### 추가 지원과 리소스는 어디에서 찾을 수 있나요?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.
### 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가를 위해.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/) 구매하기 전에 Aspose.Tasks를 살펴보세요.