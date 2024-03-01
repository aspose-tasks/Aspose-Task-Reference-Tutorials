---
title: Aspose.Tasks에서 MS 프로젝트 일정 정보 검색
linktitle: Aspose.Tasks에서 캘린더 정보 검색
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 달력 정보를 검색하는 방법을 알아보세요. 프로그래밍 방식으로 캘린더 세부정보에 액세스하기 위한 단계별 가이드입니다.
type: docs
weight: 14
url: /ko/java/project-file-operations/retrieve-calendar-info/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project 파일에서 달력 정보를 검색하는 방법을 살펴보겠습니다. Aspose.Tasks는 근무일 및 시간과 같은 달력 세부 정보에 액세스하는 것을 포함하여 프로젝트 데이터를 조작하는 강력한 기능을 제공합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Tasks for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 Java 코드에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
이제 더 나은 이해를 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 파일 디렉터리 경로를 사용하세요.
## 2단계: 시간 단위 정의
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
이러한 상수는 마이크로초 단위의 시간 단위를 나타냅니다.
## 3단계: 프로젝트 인스턴스 생성
```java
Project project = new Project(dataDir + "project.mpp");
```
 이 줄은`Project` 클래스를 프로젝트 파일의 경로로 초기화합니다(`project.mpp`).
## 4단계: 캘린더 정보 검색
```java
CalendarCollection alCals = project.getCalendars();
```
여기서는 프로젝트 파일에 있는 달력 컬렉션을 검색합니다.
## 5단계: 달력을 통해 반복
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // 캘린더 정보
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // 평일을 통해 반복
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // 시간(밀리초)
            double time = ts / (OneHour); // 시간으로 변환
            if (wd.getDayWorking()) {
                // 근무일 및 시간 표시
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
이 루프는 각 달력을 반복하여 해당 UID, 이름 및 작업일과 각 작업 시간을 인쇄합니다.
## 6단계: 완료 메시지 표시
```java
System.out.println("Process completed Successfully");
```
마지막으로 프로세스 완료를 나타내는 메시지가 표시됩니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 파일에서 달력 정보를 검색하는 방법을 배웠습니다. 다음 단계를 수행하면 Java 애플리케이션에서 프로젝트 데이터에 효율적으로 액세스하고 조작할 수 있습니다.

## FAQ
### Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 .NET, C를 포함한 여러 플랫폼과 프로그래밍 언어를 지원합니다.++, 파이썬, 자바.
### Q: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks의 임시 라이선스를 구매할 수 있나요?
 A: 예, 임시 라이센스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks에 대한 자세한 문서는 어디서 찾을 수 있나요?
 A: 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/tasks/java/).