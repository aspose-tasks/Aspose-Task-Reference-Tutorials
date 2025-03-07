---
title: Aspose.Tasks에서 자원 할당 중지 및 재개
linktitle: Aspose.Tasks에서 자원 할당 중지 및 재개
second_title: Aspose.Tasks 자바 API
description: 이 단계별 튜토리얼을 통해 Java용 Aspose.Tasks에서 리소스 할당을 효과적으로 관리하는 방법을 알아보세요.
weight: 23
url: /ko/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 자원 할당 중지 및 재개

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 리소스 할당을 중지하고 재개하는 방법을 알아봅니다. Aspose.Tasks는 개발자가 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있는 강력한 Java API입니다. 쉽게 따라할 수 있도록 프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Tasks가 다운로드되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
- Java 프로그래밍에 대한 기본 이해.
## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## 1단계: 프로젝트 파일 로드
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
// 프로젝트 파일 로드
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 이 단계에서는 프로젝트 파일을`Project` 파일 경로를 사용하는 개체입니다.
## 2단계: 자원 할당 반복
```java
// 최소 날짜 정의
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// 자원 할당을 통해 반복
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
여기서는 최소 날짜를 정의하고 프로젝트의 각 자원 할당을 반복하기 시작합니다.
## 3단계: 중지 및 재개 날짜 확인
```java
    // 중지 날짜 확인
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // 재개 날짜 확인
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
이 단계에서는 각 자원 할당의 중지 및 재개 날짜가 최소 날짜 이전인지 확인합니다. 그렇다면 "NA"를 인쇄하고, 그렇지 않으면 해당 날짜를 인쇄합니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java에서 리소스 할당을 중지하고 재개하는 방법을 배웠습니다. 제공된 단계를 따르면 Java 프로젝트에서 이 기능을 쉽게 구현할 수 있습니다.

## FAQ
### Microsoft Project를 설치하지 않고도 Aspose.Tasks를 사용할 수 있나요?
예, Aspose.Tasks를 사용하면 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있습니다.
### 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/tasks/java/).
### 무료 평가판이 제공되나요?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).
### 문제가 발생하면 어떻게 지원을 받을 수 있나요?
커뮤니티로부터 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### 임시 라이센스를 구매할 수 있나요?
 예, 임시 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
