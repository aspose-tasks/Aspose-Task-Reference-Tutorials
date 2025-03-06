---
title: Aspose.Tasks에서 작업 완료 날짜 분할
linktitle: Aspose.Tasks에서 작업 완료 날짜 분할
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 작업 완료 날짜를 쉽게 분할하는 방법을 알아보세요. 정확한 일정으로 프로젝트 관리를 강화합니다.
weight: 28
url: /ko/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 완료 날짜 분할

## 소개
프로젝트 관리에서는 성공적인 프로젝트 완료를 위해 작업 일정을 이해하는 것이 중요합니다. Aspose.Tasks for Java는 프로젝트 작업을 효율적으로 조작할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 작업 완료 날짜를 분할하여 프로젝트 일정을 효과적으로 관리하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
-  Aspose.Tasks for Java 라이브러리가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
- Java 개발 환경이 설정되었습니다.
## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 포함시키는 것부터 시작하세요.
```java
import com.aspose.tasks.*;
```
## 1단계: 분할 작업 찾기
프로젝트 내에서 분할하려는 작업을 찾으세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프로젝트 읽기
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## 2단계: 프로젝트 달력 찾기
정확한 날짜 계산을 위해 프로젝트 달력을 검색하세요.
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## 3단계: 다양한 기간으로 작업 완료 날짜 계산
이제 다양한 기간에 대한 작업 완료 날짜를 계산합니다.
## 3.1단계: 8시간 지속
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
위의 코드를 다양한 기간 동안 반복하여 그에 따라 시간을 조정하세요.
## 결론
작업 완료 날짜를 조작하는 기술을 익히는 것은 효과적인 프로젝트 관리에 매우 중요합니다. Aspose.Tasks for Java는 이 프로세스를 단순화하여 프로젝트 일정을 쉽게 간소화할 수 있습니다.
## 자주 묻는 질문
### Q1: Java용 Aspose.Tasks를 어떻게 다운로드할 수 있나요?
 A1: 다운로드할 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
### Q2: Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?
 A2: 문서를 참조하세요[여기](https://reference.aspose.com/tasks/java/).
### Q3: Aspose.Tasks에 대한 임시 라이선스는 어떻게 얻나요?
 A3: 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).
### Q4: Aspose.Tasks에 대한 지원은 어디서 구할 수 있나요?
 A4: 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/tasks/15).
### Q5: Aspose.Tasks를 구매할 수 있나요?
 A5: 그렇습니다, 당신은 그것을 구매할 수 있습니다[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
