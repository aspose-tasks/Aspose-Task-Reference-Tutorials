---
title: Aspose.Tasks에서 달력 예외 관리
linktitle: Aspose.Tasks에서 달력 예외 추가 및 제거
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java에서 달력 예외를 효율적으로 추가하고 제거하는 방법을 알아보세요. 프로젝트 관리 워크플로우를 손쉽게 향상하세요.
type: docs
weight: 10
url: /ko/java/calendar-exceptions/add-remove/
---

## 소개
프로젝트 관리에서 달력 내에서 예외를 처리하는 것은 작업을 정확하게 예약하고 리소스를 관리하는 데 중요합니다. Aspose.Tasks for Java는 달력 예외를 쉽게 추가하고 제거할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.
#### 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
- 시스템에 설치된 JDK(Java Development Kit)
- 프로젝트에 다운로드 및 구성된 Java 라이브러리용 Aspose.Tasks
- Java 프로그래밍 언어 및 프로젝트 관리 개념에 대한 기본 이해

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 효과적으로 활용하려면 Java 클래스에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.*;
```
## 1단계: 프로젝트 로드 및 달력 액세스
프로젝트 파일을 로드하고 예외를 추가하거나 제거하려는 달력에 액세스하는 것부터 시작하세요.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## 2단계: 예외 제거
달력에서 기존 예외를 제거하려면 예외가 있는지 확인한 다음 원하는 예외를 제거하십시오.
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## 3단계: 예외 추가
 달력에 새 예외를 추가하려면`CalendarException` 개체를 선택하고 시작 날짜와 종료 날짜를 정의합니다.
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## 4단계: 예외 표시
마지막으로 확인 또는 추가 처리를 위해 추가된 예외를 표시할 수 있습니다.
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## 결론
정확한 프로젝트 일정과 자원 할당을 위해서는 달력 예외 관리가 필수적입니다. Aspose.Tasks for Java를 사용하면 예외를 쉽게 추가하고 제거하여 프로젝트 일정을 효과적으로 유지할 수 있습니다.

## FAQ
### Q: Aspose.Tasks for Java를 사용하여 달력에 여러 예외를 추가할 수 있나요?

A: 예, 예외 목록을 반복하고 각 예외를 개별적으로 추가하여 달력에 여러 예외를 추가할 수 있습니다.

### Q: Aspose.Tasks for Java는 모든 버전의 Microsoft Project 파일과 호환됩니까?

A: Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일과의 호환성을 제공하여 프로젝트 관리 워크플로와의 원활한 통합을 보장합니다.

### Q: 프로젝트 달력에서 반복되는 예외를 처리하려면 어떻게 해야 합니까?

A: Aspose.Tasks for Java는 프로젝트 달력에서 반복되는 예외를 처리하는 강력한 기능을 제공하므로 복잡한 반복 패턴을 쉽게 정의할 수 있습니다.

### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?

 A: 예, 다음에서 Aspose.Tasks for Java의 무료 평가판 버전에 액세스할 수 있습니다.[웹사이트](https://releases.aspose.com/) 구매하기 전에 기능을 살펴보세요.

### Q: Aspose.Tasks for Java와 관련된 문제나 쿼리에 대한 지원은 어디서 찾을 수 있나요?

 A: Java용 Aspose.Tasks 포럼을 방문할 수 있습니다.[웹사이트](https://reference.aspose.com/tasks/java/) 커뮤니티에서 도움을 구하거나 지원팀에 직접 연락하여 맞춤형 도움을 받으세요.
