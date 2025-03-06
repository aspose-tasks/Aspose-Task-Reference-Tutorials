---
title: Aspose.Tasks를 사용하여 MS 프로젝트 달력에서 작업 주 읽기
linktitle: Aspose.Tasks를 사용하여 달력에서 작업 주 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력에서 작업 주를 읽는 방법을 알아보세요. 이 포괄적인 튜토리얼에서 단계별 지침을 얻으세요.
weight: 15
url: /ko/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS 프로젝트 달력에서 작업 주 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 달력에서 작업 주 정보를 읽는 방법을 살펴보겠습니다. Aspose.Tasks는 Microsoft Project 문서를 프로그래밍 방식으로 조작하고 관리할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 라이브러리용 Aspose.Tasks가 다운로드되어 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
먼저, 코드를 시작하는 데 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## 1단계: 데이터 디렉터리 설정
MS 프로젝트 파일이 있는 디렉터리 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: 프로젝트 인스턴스 생성 및 달력 액세스
Project 클래스의 새 인스턴스를 만들고 달력 및 작업 주 컬렉션에 액세스합니다.
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## 3단계: 작업 주간 반복
작업 주 모음을 반복하고 해당 정보를 표시합니다.
```java
for (WorkWeek workWeek : collection) {
    // 작업 주 이름, 시작 및 종료 날짜 표시
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // 평일 및 근무 시간에 액세스
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // 필요한 경우 추가 처리 작업 시간
    }
}
```
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 달력에서 작업 주 정보를 읽는 방법을 배웠습니다. 이 강력한 라이브러리를 사용하면 프로젝트 파일을 원활하게 조작할 수 있으므로 개발자는 다양한 작업을 효율적으로 자동화할 수 있습니다.
## FAQ
### Aspose.Tasks for Java를 사용하여 근무 주 정보를 수정할 수 있나요?
예, Aspose.Tasks는 근무 주 및 관련 정보를 수정, 추가 또는 삭제할 수 있는 API를 제공합니다.
### Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
예, Aspose.Tasks는 MPP 및 XML 형식을 포함하여 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Aspose.Tasks를 다른 Java 프레임워크와 통합할 수 있나요?
물론, Aspose.Tasks는 향상된 기능을 위해 다른 Java 프레임워크 및 라이브러리와 원활하게 통합될 수 있습니다.
### Aspose.Tasks에 사용할 수 있는 평가판이 있나요?
 예, 다음에서 Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
Aspose.Tasks 포럼에서 지원과 지원을 찾을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
