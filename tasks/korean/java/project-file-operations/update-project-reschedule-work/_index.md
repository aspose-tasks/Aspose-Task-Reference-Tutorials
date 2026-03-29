---
date: 2026-03-29
description: Aspose.Tasks for Java를 사용하여 미완료 작업을 재조정하고, 프로젝트 작업을 업데이트하며, MS Project
  파일을 XML로 저장하는 방법을 배웁니다.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 미완료 작업 재조정 및 Aspose.Tasks를 사용한 MS Project 파일 업데이트
url: /ko/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 미완료 작업 재일정 및 MS Project 파일 업데이트

## 소개
Microsoft Project는 팀이 작업을 계획하고, 리소스를 할당하며, 일정을 추적하도록 돕는 널리 사용되는 프로젝트 관리 도구입니다. Aspose.Tasks for Java는 개발자에게 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 풍부한 API를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **프로젝트 작업 업데이트**, **미완료 작업 재일정**, 그리고 XML 형식으로 **MS Project 파일 저장**하는 방법을 배웁니다.

## 빠른 답변
- **“미완료 작업 재일정”이란 무엇입니까?** 남아 있는 작업을 선택한 날짜 이후에 시작하도록 이동시키며, 완료된 부분은 그대로 유지합니다.  
- **작업을 완료된 것으로 표시하는 메서드는 무엇입니까?** `project.updateProjectWorkAsComplete(date, false)`.  
- **변경 사항을 어떻게 저장합니까?** `project.save(<path>, SaveFileFormat.Xml)`를 사용합니다.  
- **프로덕션에서 라이선스가 필요합니까?** 예, 상업적 사용을 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇입니까?** Java 8 이상이 완전히 지원됩니다.

## “미완료 작업 재일정”이란?
미완료 작업을 재일정하면 아직 완료되지 않은 모든 작업의 시작 날짜를 지정된 마감 날짜 이후로 조정합니다. 이는 지연이나 범위 변경으로 인해 프로젝트 일정이 변경될 때 유용합니다.

## 프로젝트 작업을 업데이트하고 작업을 재일정하기 위해 Aspose.Tasks를 사용하는 이유는?
- **세밀한 제어:** 작업 완료 비율과 날짜를 직접 설정합니다.  
- **UI 불필요:** 다수의 프로젝트 파일에 대한 대량 업데이트를 자동화합니다.  
- **크로스 플랫폼:** Java가 실행되는 모든 시스템에서 작동합니다.  
- **데이터 무결성 유지:** 모든 종속성, 제약 조건 및 리소스가 일관성을 유지합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:
1. 시스템에 설치된 Java Development Kit (JDK).  
2. Aspose.Tasks for Java 라이브러리. [here](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
3. Java 프로그래밍 언어에 대한 기본 이해.

## 패키지 가져오기
먼저, Java 코드에서 필요한 패키지를 가져옵니다:
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

## 단계 1: 프로젝트 설정
`Project` 객체를 새로 초기화하고, 작업을 정의하며, 기간을 설정하고, 종속성을 설정합니다. 이렇게 하면 나중에 업데이트하고 재일정할 기본 프로젝트가 생성됩니다.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## 단계 2: 프로젝트 작업 업데이트
특정 날짜까지 작업을 완료된 것으로 표시합니다. 이 단계는 **프로젝트 작업 업데이트** 작업을 보여주며, 이는 재일정 전에 흔히 수행되는 첫 번째 작업입니다.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## 단계 3: 미완료 작업 재일정
이제 남아 있는 (미완료) 작업을 동일한 마감 날짜 이후에 시작하도록 이동합니다. 이것이 핵심 **미완료 작업 재일정** 기능입니다.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **프로젝트 작업 업데이트**, **미완료 작업 재일정**, 그리고 **MS Project 파일을 XML로 저장**하는 방법을 다루었습니다. 이러한 기능은 실제 진행 상황이나 비즈니스 우선순위 변화에 따라 프로젝트 일정을 조정해야 할 때 필수적입니다.

## FAQ
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 작업, 종속성, 리소스 및 기타 프로젝트 요소를 효율적으로 관리할 수 있는 강력한 API를 제공합니다.  
### Q: Aspose.Tasks for Java용 체험 버전이 있나요?
A: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 받을 수 있습니다.  
### Q: Aspose.Tasks for Java에 대한 지원을 어떻게 받을 수 있나요?
A: 지원이나 문의 사항이 있으면 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 를 방문하십시오.  
### Q: Aspose.Tasks for Java용 임시 라이선스를 구매할 수 있나요?
A: 예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.  
### Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
A: 자세한 가이드와 API 참조는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## 추가 자주 묻는 질문

**Q: 저장된 파일이 이전 버전의 Microsoft Project와 호환되도록 하려면 어떻게 해야 하나요?**  
A: `SaveFileFormat.Xml`을 사용하여 프로젝트를 저장하십시오; XML은 다양한 Project 버전에서 널리 지원됩니다.

**Q: 전체 프로젝트가 아니라 특정 작업 집합만 재일정할 수 있나요?**  
A: 예, 특정 작업을 반복하면서 새 시작 날짜를 계산한 후 `task.setStart(date)`를 호출하면 됩니다.

**Q: 미완료 작업을 재일정할 때 리소스 할당은 어떻게 되나요?**  
A: 리소스 할당은 새로운 작업 시작 날짜에 맞게 자동으로 이동되어 할당 로직을 유지합니다.

**Q: 프로그래밍 방식으로 재일정 작업을 취소할 수 있나요?**  
A: 원본 프로젝트 파일(또는 백업)을 다시 로드하여 변경 사항을 되돌릴 수 있습니다.

**Q: Aspose.Tasks가 .mpp와 같은 다른 형식으로 저장을 지원하나요?**  
A: 물론입니다. `SaveFileFormat.MPP`를 사용하면 기본 Microsoft Project 형식으로 저장할 수 있습니다.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}