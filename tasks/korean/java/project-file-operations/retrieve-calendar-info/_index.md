---
date: 2026-03-27
description: Java를 사용하여 Microsoft Project 파일에서 프로젝트 캘린더 세부 정보를 추출하기 위해 Aspose와 Aspose.Tasks를
  활용하는 방법을 배웁니다. 코드 예제가 포함된 단계별 가이드.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project 캘린더 정보를 가져오는 방법
url: /ko/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS Project 캘린더 정보 검색하는 방법

## 소개
이 튜토리얼에서는 **Aspose.Tasks를 사용하는 방법**을 알아보고 Microsoft Project 파일에서 프로그래밍 방식으로 캘린더 정보를 검색하는 방법을 배웁니다. 작업일, 근무시간, 예외와 같은 캘린더 데이터를 액세스하는 것은 **프로젝트 캘린더** 세부 정보를 보고, 통합하거나 사용자 지정 일정 로직을 구현해야 할 때 필수적입니다. 단계별로 과정을 진행하면서 **Aspose를 사용하는 방법**을 통해 *.mpp* 파일에서 해당 데이터를 추출하는 방법을 정확히 확인해 보세요.

## 빠른 답변
- **이 튜토리얼에서 사용하는 라이브러리는 무엇인가요?** Aspose.Tasks for Java.  
- **다루는 주요 키워드는 무엇인가요?** *how to use aspose*.  
- **무엇을 추출할 수 있나요?** 작업일 및 시간을 포함한 프로젝트 캘린더.  
- **라이선스가 필요합니까?** 무료 체험판을 사용할 수 있으며, 프로덕션에서는 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.

## Aspose.Tasks란 무엇이며 왜 사용하나요?
Aspose.Tasks는 Microsoft Project 자체 없이도 개발자가 Microsoft Project 파일을 읽고, 쓰고, 조작할 수 있게 해 주는 강력한 Java API입니다. Aspose.Tasks를 사용하면 **how to extract calendar** 정보를 추출하고, 일정 계산을 자동화하며, 프로젝트 데이터를 다른 엔터프라이즈 시스템과 통합할 수 있습니다—모두 순수 Java 코드만으로 가능합니다.

## 프로젝트 캘린더 정보를 추출하는 이유는?
프로젝트 캘린더는 작업 날짜, 리소스 할당 및 전체 타임라인 계산을 주도합니다. 이 데이터를 추출하면 다음을 수행할 수 있습니다.
- 실제 작업 일정이 반영된 맞춤형 보고서를 생성합니다.  
- Microsoft Project 타임라인을 외부 시스템(ERP, BI 등)과 동기화합니다.  
- 캘린더 설정을 프로그래밍 방식으로 변경하여 가상 시나리오 분석을 수행합니다.  
- **Extract MS Project calendar** 데이터를 다른 계획 도구로 마이그레이션합니다.

## 전제 조건
시작하기 전에 다음을 확인하세요:

- Java 프로그래밍에 대한 기본 지식.  
- 시스템에 Java Development Kit (JDK) 설치.  
- Aspose.Tasks for Java 라이브러리. [여기](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
먼저, Java 프로젝트에 필요한 Aspose.Tasks 클래스를 가져옵니다.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## 단계 1: 데이터 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 **project.mpp** 파일이 위치한 폴더의 절대 경로로 교체하세요.

## 단계 2: 시간 단위 정의
내부 시간 표현을 사람이 읽을 수 있는 시간(시간)으로 변환하는 데 도움이 되는 상수를 생성합니다.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

이 값들은 마이크로초 단위이며, Aspose.Tasks가 내부적으로 시간을 저장하는 방식입니다.

## 단계 3: Project 인스턴스 생성
Microsoft Project 파일을 `Project` 객체에 로드합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` 생성자는 *.mpp* 파일을 파싱하고 캘린더를 포함한 모든 프로젝트 데이터를 API를 통해 접근 가능하게 합니다.

## 단계 4: 캘린더 정보 가져오기
프로젝트에 정의된 캘린더 컬렉션을 가져옵니다.

```java
CalendarCollection alCals = project.getCalendars();
```

프로젝트에는 표준, 리소스 및 사용자 정의 캘린더와 같이 여러 캘린더가 포함될 수 있습니다. 이 컬렉션을 통해 각각에 접근할 수 있습니다.

## 단계 5: 캘린더 순회
각 캘린더를 순회하면서 UID, 이름 및 작업일과 해당 근무 시간을 표시합니다.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

내부 루프는 각 `WeekDay` 객체를 검사합니다. 해당 요일이 작업일로 표시되면 요일 유형(월요일, 화요일 등)과 계산된 작업 시간을 출력합니다.

## 단계 6: 완료 메시지 표시
추출 프로세스가 완료되었음을 알립니다.

```java
System.out.println("Process completed Successfully");
```

## 일반적인 문제 및 해결책
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **No calendars returned** | 프로젝트 파일에 사용자 정의 캘린더가 없을 수 있습니다. | *.mpp* 파일에 실제로 캘린더가 정의되어 있는지 확인하거나 Microsoft Project에서 열어 확인하세요. |
| **Incorrect working hours** | 다른 Project 버전에서 시간 변환 상수가 맞지 않을 수 있습니다. | 내부 시간 단위가 변경된 최신 Aspose.Tasks 버전을 사용하는 경우 `OneSec`, `OneMin`, `OneHour` 값을 조정하세요. |
| **`NullPointerException` on `cal.getName()`** | 일부 캘린더 객체가 null일 수 있습니다. | 속성에 접근하기 전에 null 검사를 추가하세요(이미 예시에서 보여줌). |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 네, Aspose.Tasks는 .NET, C++, Python, Java 등 여러 플랫폼과 프로그래밍 언어를 지원합니다.

**Q: Aspose.Tasks의 무료 체험판을 이용할 수 있나요?**  
A: 네, [여기](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다. [여기](https://forum.aspose.com/c/tasks/15)에서 확인하세요.

**Q: Aspose.Tasks의 임시 라이선스를 구매할 수 있나요?**  
A: 네, 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.

**Q: Aspose.Tasks에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [여기](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

## 결론
이 단계를 따라 하면 **Java를 사용하여 MS Project 파일에서 프로젝트 캘린더를 추출하는 방법**을 이제 알게 됩니다. 이 로직을 더 큰 애플리케이션에 통합하거나 보고서를 자동화하고, 다른 엔터프라이즈 시스템과 일정을 동기화할 수 있습니다. **how to use aspose**를 숙달하면 다양한 고급 프로젝트 관리 자동화 시나리오의 문을 열 수 있습니다.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}