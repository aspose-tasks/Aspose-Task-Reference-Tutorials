---
title: Aspose.Tasks에서 MS 프로젝트 업데이트 및 일정 변경
linktitle: Aspose.Tasks에서 프로젝트 업데이트 및 완료되지 않은 작업 일정 변경
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 MS 프로젝트 파일을 업데이트하고 일정을 변경하는 방법을 알아보세요.
weight: 23
url: /ko/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS 프로젝트 업데이트 및 일정 변경

## 소개
Microsoft Project는 사용자가 작업, 리소스 및 일정을 효율적으로 관리할 수 있도록 널리 사용되는 프로젝트 관리 소프트웨어입니다. Aspose.Tasks for Java는 프로그래밍 방식으로 Microsoft Project 파일을 조작할 수 있는 강력한 API 세트를 제공합니다. 이 튜토리얼에서는 MS 프로젝트 파일을 업데이트하고 Aspose.Tasks for Java를 사용하여 완료되지 않은 작업 일정을 변경하는 방법을 알아봅니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Aspose.Tasks for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍 언어에 대한 기본 이해.

## 패키지 가져오기
먼저 Java 코드에 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 1단계: 프로젝트 설정
새 프로젝트 개체를 초기화하고 기간 및 종속성과 함께 그 안에 작업을 정의합니다.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// 작업 및 기간 정의
// ...
// 작업 종속성 정의
// ...
// 초기 프로젝트 상태 저장
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## 2단계: 프로젝트 작업 업데이트
프로젝트 작업을 업데이트하여 특정 날짜까지 완료된 것으로 표시하세요.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// 업데이트된 프로젝트 저장
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## 3단계: 완료되지 않은 작업 일정 변경
완료되지 않은 작업이 지정된 날짜 이후에 시작되도록 일정을 변경합니다.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// 일정이 변경된 프로젝트 저장
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 결론
이 튜토리얼에서는 MS 프로젝트 파일을 업데이트하고 Aspose.Tasks for Java를 사용하여 완료되지 않은 작업 일정을 변경하는 방법을 배웠습니다. 이는 진행 상황이나 우선순위 변경에 따라 프로젝트 일정을 조정해야 하는 시나리오에서 특히 유용할 수 있습니다.

## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있습니까?
A: 예, Aspose.Tasks for Java는 작업, 종속성, 리소스 및 기타 프로젝트 요소를 효율적으로 관리할 수 있는 강력한 API를 제공합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 도움이나 문의사항이 있으면
### Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?
 A: 예, 임시 라이센스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 A: 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/tasks/java/) 포괄적인 가이드 및 API 참조를 확인하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
