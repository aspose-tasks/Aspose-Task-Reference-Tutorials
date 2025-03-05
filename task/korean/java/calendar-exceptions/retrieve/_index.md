---
title: Aspose.Tasks를 사용하여 달력 예외 검색
linktitle: Aspose.Tasks를 사용하여 달력 예외 검색
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 달력 예외를 검색하는 방법을 알아보세요. 원활한 통합을 위한 단계별 튜토리얼입니다.
type: docs
weight: 13
url: /ko/java/calendar-exceptions/retrieve/
---
## 소개
이 튜토리얼에서는 Java용 Aspose.Tasks 라이브러리를 사용하여 MS 프로젝트에서 달력 예외를 검색하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 도구입니다. 이해하기 쉽도록 각 예를 여러 단계로 나누어 프로세스를 단계별로 안내해 드립니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 등 원하는 IDE를 사용할 수 있습니다.

## 패키지 가져오기
먼저 Aspose.Tasks를 사용하는 데 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.tasks.*;
```
## 1단계: 데이터 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
```
 반드시 교체하세요`"Your Data Directory"` MS 프로젝트 파일이 포함된 디렉터리 경로를 사용하세요.
## 2단계: MS 프로젝트 파일 로드
```java
Project project = new Project(dataDir + "project.mpp");
```
 이 줄은 새로운 것을 초기화합니다`Project` 경로에 지정된 MS 프로젝트 파일을 로드하여 개체를 만듭니다.
## 3단계: 달력 예외 검색
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
여기에서는 프로젝트의 각 달력을 반복한 다음 해당 달력 내의 각 달력 예외를 반복합니다. 각 예외의 시작 날짜와 종료 날짜를 인쇄합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트에서 달력 예외를 검색하는 방법을 배웠습니다. 이러한 간단한 단계를 따르면 이 기능을 Java 애플리케이션에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일을 처리할 수 있나요?
예, Aspose.Tasks는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 MS 프로젝트 파일을 지원합니다.
### Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 예, 다음에서 Aspose.Tasks 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?
 문서를 참고하시면 됩니다[여기](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks에 대한 임시 라이선스 옵션이 있나요?
 예, 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).