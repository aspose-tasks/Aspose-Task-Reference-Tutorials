---
date: 2026-02-05
description: Aspose.Tasks를 사용하여 Microsoft Project 캘린더에서 작업 주(Workweeks)를 Java로 읽는
  방법을 배워보세요. 전체 코드 예제가 포함된 단계별 가이드를 따라가세요.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용해 MS Project 캘린더에서 Workweeks Java 읽는 방법
url: /ko/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 캘린더 Aspose.Tasks에서 Workweeks Java 읽는 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 캘린더에서 **Workweeks Java를 읽는 방법**을 배웁니다. 보고서 도구를 만들든, 일정 동기화를 하든, 프로젝트 데이터 추출을 자동화하든, 프로그래밍 방식으로 작업 주 정의에 접근하면 수많은 수작업 시간을 절감할 수 있습니다. 필요한 설정 과정을 단계별로 안내하고, 작업 주 세부 정보를 가져오는 정확한 코드를 보여드리며, 각 단계를 설명해 여러분이 자신의 프로젝트에 적용할 수 있도록 돕습니다.

## 빠른 답변
- **“read workweeks java”가 무엇을 의미하나요?** Java 코드를 사용하여 Project 파일에서 작업 주 정의를 추출하는 것을 의미합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java (무료 체험 가능).  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 체험판으로 충분하지만, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **지원되는 파일 형식은 무엇인가요?** *.mpp*와 Project XML 파일 모두 지원됩니다.  
- **구현에 얼마나 걸리나요?** 라이브러리를 설정하면 일반적으로 10분 이내에 완료됩니다.

## Microsoft Project 캘린더에서 Workweeks Java 읽는 방법
Java에서 작업 주를 읽는다는 것은 Aspose.Tasks API를 사용하여 Microsoft Project 파일 내부의 캘린더 객체에 있는 `WorkWeekCollection`에 접근하는 것을 의미합니다. 각 `WorkWeek`는 시작/종료 날짜와 리소스 일정에 영향을 주는 일일 작업 시간 정의를 포함합니다.

## 왜 Microsoft Project 캘린더에서 Workweeks Java를 읽어야 할까요?
- **자동화:** 일정 데이터를 수동으로 복사·붙여넣는 작업을 없앱니다.  
- **통합:** 작업 주 정보를 ERP, HR 또는 맞춤형 보고 시스템에 전달합니다.  
- **일관성:** 모든 하위 도구가 Project 파일에 정의된 동일한 캘린더 규칙을 따르도록 보장합니다.

## 전제 조건
코드에 들어가기 전에 다음이 준비되어 있는지 확인하세요:

1. **Java Development Kit (JDK)** – 버전 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 공식 사이트에서 최신 JAR를 다운로드하세요: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **샘플 Project 파일** (`ReadWorkWeeksInformation.mpp`)을 알려진 폴더에 배치합니다.

## 패키지 가져오기
먼저, 캘린더와 작업 주와 상호 작용하는 데 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 단계 1: 데이터 디렉터리 설정
`.mpp` 파일이 들어 있는 폴더를 정의합니다. 플레이스홀더를 실제 경로로 교체하세요:

```java
String dataDir = "Your Data Directory";
```

## 단계 2: Project 인스턴스 생성 및 캘린더 접근
`Project` 객체를 인스턴스화하고, 원하는 캘린더를 UID로 선택한 뒤, 해당 캘린더의 `WorkWeekCollection`을 가져옵니다:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **팁:** 캘린더 UID가 확실하지 않다면 `project.getCalendars()`를 반복하여 각 캘린더의 이름과 UID를 출력할 수 있습니다.

## 단계 3: 작업 주 반복
각 `WorkWeek`를 순회하면서 이름, 시작/종료 날짜 및 일일 작업 시간을 표시합니다:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**출력 예시:** 콘솔에 각 작업 주의 라벨(예: “Standard”), 적용 기간, 그리고 각 요일별 정확한 작업 시간이 표시됩니다.

## 일반적인 문제와 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| `calendar` 접근 시 `NullPointerException` | UID가 잘못되었거나 캘린더가 존재하지 않음 | `project.getCalendars().size()`로 UID를 확인하고 먼저 사용 가능한 캘린더를 나열하세요. |
| 작업 주에 대한 출력 없음 | 선택한 캘린더에 사용자 정의 작업 주가 없으며(기본값 사용) | 기본 캘린더(`project.getDefaultCalendar()`)를 사용하거나 프로그래밍 방식으로 작업 주를 생성하세요. |
| 날짜 형식이 이상하게 보임 | `System.out.println`이 기본 `java.util.Date` 형식을 사용함 | 필요에 따라 `SimpleDateFormat`을 적용하여 날짜를 포맷하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용하여 작업 주 정보를 수정할 수 있나요?**  
A: 예. API는 `addWorkWeek()`, `removeWorkWeek()`와 같은 메서드 및 이름, 날짜, 작업 시간을 변경할 수 있는 속성 설정자를 제공합니다.

**Q: Aspose.Tasks가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. Project 98부터 최신 버전까지의 MPP 파일과 Project XML 파일을 모두 지원합니다.

**Q: Aspose.Tasks를 다른 Java 프레임워크와 통합할 수 있나요?**  
A: 예. 라이브러리는 순수 Java이므로 Spring, Jakarta EE 등 어떤 프레임워크와도 함께 사용할 수 있습니다.

**Q: Aspose.Tasks 체험판을 사용할 수 있나요?**  
A: 예, 공식 사이트에서 30일 무료 체험판을 다운로드할 수 있습니다: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks 지원은 어디서 받을 수 있나요?**  
A: Aspose 커뮤니티 포럼이 가장 좋은 곳입니다: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## 결론
이제 Aspose.Tasks를 사용하여 **Workweeks Java를 읽는 방법**을 마스터했습니다. 위 단계들을 따라 하면 어떤 MS Project 캘린더에서도 작업 주 정의를 프로그래밍 방식으로 추출하고, 해당 데이터를 애플리케이션에 통합하며, 일정 관련 워크플로를 자동화할 수 있습니다. 작업 주를 생성하거나 업데이트하는 실험도 자유롭게 해보세요—Aspose.Tasks가 간단하게 도와줍니다.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}