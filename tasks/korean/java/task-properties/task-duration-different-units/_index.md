---
date: 2026-02-28
description: Aspose.Tasks for Java를 사용하여 분, 일, 시간, 주, 월 단위의 기간을 얻는 방법을 배워보세요. 코드 예제가
  포함된 자세한 가이드.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 다양한 단위로 기간 가져오기
url: /ko/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 다양한 단위로 기간 가져오기

## 소개
작업의 **기간을 가져오는 방법**을 이해하는 것은 모든 프로젝트 관리 워크플로우의 핵심 요소입니다. 세밀한 추적을 위해 분이 필요하든, 고수준 계획을 위해 월이 필요하든, Aspose.Tasks for Java는 변환을 간단하게 해줍니다. 이 튜토리얼에서는 작업의 기간을 분, 일, 시간, 주, 월 단위로 가져오는 방법을 단계별로 안내하고, 각 단위가 실제 프로젝트에서 왜 유용한지 설명합니다.

## 빠른 답변
- **“기간을 가져오는 방법”이란 무엇인가요?** 작업의 시간 범위를 추출하고 필요한 단위로 변환하는 과정입니다.  
- **어떤 API 메서드가 변환을 수행하나요?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **코드를 실행하려면 라이선스가 필요합니까?** 테스트용 무료 체험판으로 실행할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다.  
- **사용자 정의 단위로 변환할 수 있나요?** 변환을 체인하거나 `TimeSpan`을 사용해 사용자 정의 계산을 할 수 있습니다.  
- **코드가 Java 17과 호환되나요?** 네, Aspose.Tasks는 Java 8 이상 버전을 지원합니다.

## Aspose.Tasks에서 “how to get duration”란?
Aspose.Tasks는 작업의 길이를 `Duration` 객체로 저장합니다. `convert` 메서드에 `TimeUnitType`(Minute, Hour, Day, Week, Month)을 지정하면 동일한 기본 값을 원하는 단위로 표현된 값으로 가져올 수 있습니다. 이 유연성을 통해 보고서를 생성하거나 계산을 수행하거나 다른 시스템에 데이터를 전달할 때 수동 계산이 필요하지 않습니다.

## 기간 변환에 Aspose.Tasks를 사용하는 이유
- **정확성:** 달력 예외, 근무 시간, 비표준 달력을 자동으로 처리합니다.  
- **성능:** 한 줄 변환으로 루프나 사용자 정의 파싱이 필요 없습니다.  
- **이식성:** Windows, Linux, macOS 환경에서 동일하게 동작합니다.  
- **통합성:** 이미 Aspose.Tasks를 사용하고 있는 기존 Java 애플리케이션에 손쉽게 통합됩니다.

## 사전 요구 사항
- Java Development Kit (JDK) 설치
- Aspose.Tasks for Java 라이브러리. [여기](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.
- Java 프로그래밍에 대한 기본 이해

## 패키지 가져오기
Java 프로젝트에 Aspose.Tasks 라이브러리를 포함하십시오. 코드 시작 부분에 다음 import 문을 추가합니다:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 단계 1: 프로젝트 설정
IntelliJ, Eclipse, VS Code 등 선호하는 IDE에서 새 Java 프로젝트를 만들고 Aspose.Tasks JAR 파일을 프로젝트 클래스패스에 추가합니다. 이렇게 하면 컴파일 시 위 클래스들을 사용할 수 있습니다.

## 단계 2: 프로젝트 템플릿 읽기
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

`"Your Document Directory"`를 실제 `.xml` 또는 `.mpp` 프로젝트 파일이 들어 있는 폴더 경로로 바꾸세요.

## 단계 3: 작업 가져오기
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

`getById(1)` 호출은 ID가 1인 작업을 가져옵니다. 파일 내 다른 작업을 대상으로 하려면 ID를 적절히 조정하십시오.

## 단계 4: 분 단위 기간 – 분 단위로 기간을 가져오는 방법?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

`mins` 변수에 이제 작업 길이가 분 단위로 저장됩니다.

## 단계 5: 일 단위 기간 – 일 단위로 기간을 가져오는 방법?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

보고서 작성이나 리소스 할당 시 일 수준의 세분화가 필요할 때 이 값을 사용하십시오.

## 단계 6: 시간 단위 기간 – 시간 단위로 기간을 가져오는 방법?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

시간 단위는 근무표 작성이나 하루를 근무 교대로 나눌 때 유용합니다.

## 단계 7: 주 단위 기간 – 주 단위로 기간을 가져오는 방법?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

주 단위는 고수준 Gantt 차트나 마일스톤 계획에 자주 사용됩니다.

## 단계 8: 월 단위 기간 – 월 단위로 기간을 가져오는 방법?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

월 단위 기간은 프로젝트 단계와 회계 기간을 맞출 때 도움이 됩니다.

## 일반적인 문제 및 해결책
| 증상 | 가능 원인 | 해결 방법 |
|------|-----------|-----------|
| `task`에서 `NullPointerException` | 잘못된 작업 ID 또는 하위 작업 누락 | `project.getRootTask().getChildren()`를 사용해 작업 ID가 존재하는지 확인 |
| 예상치 못한 값(예: 0) | 프로젝트가 비근무일이 포함된 사용자 정의 달력을 사용 | 프로젝트 달력이 올바르게 정의되었는지 확인하거나 `project.getCalendar()`로 검사 |
| 변환 결과가 소수점 주 단위 | 주가 프로젝트 기본 주 길이(보통 5일)를 기준으로 계산됨 | 달력 주가 필요하면 5를 곱하거나 달력 설정을 조정 |

## 자주 묻는 질문
### Q: Aspose.Tasks for Java를 모든 Java IDE와 함께 사용할 수 있나요?
A: 네, Aspose.Tasks for Java는 모든 Java 통합 개발 환경(IDE)과 호환됩니다.

### Q: Microsoft Project 파일에서 작업 ID를 어떻게 얻을 수 있나요?
A: 프로젝트 파일을 수동으로 확인하거나 `project.getRootTask().getChildren()`을 호출해 컬렉션을 순회하면서 각 작업의 `ID`를 읽을 수 있습니다.

### Q: 대규모 프로젝트를 처리하는 데 Aspose.Tasks가 적합한가요?
A: 물론입니다. Aspose.Tasks는 수천 개의 작업과 리소스를 가진 대형 프로젝트도 효율적으로 처리하도록 설계되었습니다.

### Q: 추가 문서는 어디에서 찾을 수 있나요?
A: 포괄적인 API 레퍼런스, 코드 샘플, 모범 사례 가이드는 [문서](https://reference.aspose.com/tasks/java/)에서 확인하세요.

### Q: 구매 전에 Aspose.Tasks for Java를 체험할 수 있나요?
A: 네, [무료 체험](https://releases.aspose.com/)을 통해 기능을 평가해 볼 수 있습니다.

---

**마지막 업데이트:** 2026-02-28  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}