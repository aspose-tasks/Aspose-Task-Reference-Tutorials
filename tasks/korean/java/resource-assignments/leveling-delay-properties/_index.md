---
date: 2026-01-07
description: Aspose.Tasks for Java를 사용하여 프로젝트에 리소스를 추가하고 리소스 할당에 대한 레벨링 지연 속성을 처리하는
  방법을 배웁니다.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 프로젝트에 리소스를 추가하고 레벨링 지연 속성을 처리하는 방법
url: /ko/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 프로젝트에 리소스를 추가하고 레벨링 지연 속성을 처리하는 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **프로젝트에 리소스를 추가하는 방법**과 리소스 할당에 대한 레벨링 지연 속성을 관리하는 방법을 배웁니다. 스케줄링 엔진을 구축하거나 프로젝트 업데이트를 자동화하든, 이 단계들을 숙달하면 Microsoft Project를 설치하지 않아도 프로젝트 데이터를 정확하게 유지할 수 있습니다.

## 빠른 답변
- **“프로젝트에 리소스를 추가한다”는 것은 무엇을 의미하나요?** 새로운 리소스 항목을 생성하여 작업에 할당할 수 있게 합니다.  
- **할당 후 레벨링 지연을 설정할 수 있나요?** 예, `Asn.DELAY` 또는 `Asn.LEVELING_DELAY` 필드를 사용합니다.  
- **이 코드를 실행하려면 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 실행할 수 있지만, 운영 환경에서는 유료 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상을 지원합니다.  
- **모든 MS Project 파일 형식과 호환되나요?** Aspose.Tasks는 .MPP, .XML, .XER 등 다양한 MS Project 파일 형식을 지원합니다.  

## Aspose.Tasks에서 “프로젝트에 리소스를 추가”란 무엇인가요?
프로젝트에 리소스를 추가한다는 것은 `Project` 모델 내부에 `Resource` 객체를 생성하는 것을 의미합니다. 이 객체는 이후 `ResourceAssignment`를 통해 작업에 연결될 수 있어 작업량, 비용 및 레벨링 설정을 추적할 수 있습니다.

## 왜 레벨링 지연 속성을 처리해야 할까요?
레벨링 지연은 리소스가 과다 할당될 때 스케줄러가 작업을 분산하도록 도와줍니다. 지연을 설정하면 엔진에 할당 시작을 연기하도록 지시하여 충돌을 방지하고 프로젝트를 현실적으로 유지할 수 있습니다.

## 전제 조건
1. Java Development Kit (JDK): 시스템에 Java JDK가 설치되어 있는지 확인하십시오. [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html)에서 다운로드하고 설치할 수 있습니다.  
2. Aspose.Tasks for Java 라이브러리: [download page](https://releases.aspose.com/tasks/java/)에서 Aspose.Tasks for Java 라이브러리를 다운로드하십시오.

## 패키지 가져오기
먼저, Aspose.Tasks 기능을 사용하기 위해 Java 프로젝트에 필요한 패키지를 가져옵니다:
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

## 단계 1: Project 객체 생성
모든 작업, 리소스 및 할당을 담는 컨테이너 역할을 하는 `Project` 객체를 인스턴스화합니다:
```java
Project prj = new Project();
```

## 단계 2: 작업 생성
프로젝트에 작업을 추가합니다. 이는 **작업을 추가하는 방법**을 프로그래밍 방식으로 보여줍니다:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 단계 3: 작업 시작 날짜 및 기간 설정
작업이 언제 시작하고 얼마나 오래 진행될지 정의합니다:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 단계 4: 리소스 추가
이제 새로운 `Resource` 항목을 생성하여 **프로젝트에 리소스를 추가**합니다:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 단계 5: 리소스 할당 생성
작업과 새로 추가된 리소스를 연결합니다:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 단계 6: 레벨링 지연 설정
할당에 대한 레벨링 지연을 구성합니다. 값을 0으로 설정하면 추가 지연이 없으며, 필요에 따라 값을 조정할 수 있습니다:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 단계 7: 결과 표시
중요한 속성을 출력하여 모든 설정이 올바르게 적용되었는지 확인합니다:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 일반적인 함정 및 팁
- **함정:** 작업 시작 날짜를 설정하지 않으면 할당이 프로젝트 시작일로 기본 설정될 수 있습니다.  
- **팁:** `prj.getDuration(value, TimeUnitType.Day)`를 사용하여 지연의 세분성을 제어하십시오.  
- **팁:** 여러 리소스를 추가한 후 `prj.updateResourceAssignments()`를 호출하여 스케줄러가 레벨링을 다시 계산하도록 합니다.  

## 결론
이 단계들을 따라 하면 이제 **프로젝트에 리소스를 추가하는 방법**을 알고, 작업에 할당하고 Aspose.Tasks for Java를 사용하여 레벨링 지연 속성을 관리할 수 있습니다. 이 지식을 통해 실제 리소스 제약과 동기화된 견고한 프로젝트 자동화 솔루션을 구축할 수 있습니다.

## FAQ

### Q: Aspose.Tasks를 다른 Java 라이브러리와 함께 사용할 수 있나요?
예, Aspose.Tasks는 다른 Java 라이브러리와 통합되어 프로젝트 관리 기능을 향상시킬 수 있습니다.

### Q: Aspose.Tasks가 다양한 버전의 Microsoft Project 파일과 호환되나요?
예, Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원하여 여러 환경에서 호환성을 보장합니다.

### Q: Aspose.Tasks에 대한 추가 지원은 어디에서 찾을 수 있나요?
다음 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원 및 리소스를 확인할 수 있습니다.

### Q: 구매 전에 Aspose.Tasks를 체험해볼 수 있나요?
예, [releases page](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험판을 받을 수 있습니다.

### Q: Aspose.Tasks 임시 라이선스를 어떻게 얻을 수 있나요?
평가 목적으로 [temporary license page](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 요청할 수 있습니다.

## 추가 자주 묻는 질문

**Q: 비제로 레벨링 지연을 설정하면 어떻게 되나요?**  
A: 스케줄러가 지정된 기간만큼 할당 시작을 연기하여 과다 할당을 해결하는 데 도움이 됩니다.

**Q: 프로젝트를 저장한 후 레벨링 지연을 조회할 수 있나요?**  
A: 예, 프로젝트 파일을 다시 열어 할당의 `Asn.DELAY` 속성을 읽을 수 있습니다.

**Q: 모든 할당에 한 번에 레벨링 지연을 적용할 방법이 있나요?**  
A: `prj.getResourceAssignments()`를 순회하면서 각 할당에 대해 루프 내에서 지연을 설정할 수 있습니다.

---

**마지막 업데이트:** 2026-01-07  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}