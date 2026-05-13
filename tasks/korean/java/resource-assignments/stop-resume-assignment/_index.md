---
date: 2026-01-10
description: 이 단계별 튜토리얼을 통해 할당 중단 방법, 리소스 할당 관리 방법, 그리고 Aspose.Tasks for Java에서 리소스
  할당 예제를 확인하는 방법을 배워보세요.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 할당 중지 및 리소스 할당 재개 방법
url: /ko/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 시작 및 재개 방법

## 소개
이 튜토리얼에서는 **Aspose.Tasks for Java**를 사용하여 이를 중지하고 나중에 다시 시작하는 방법을 알아봅니다. Aspose.Tasks는 프로젝트 파일(Java 형식)을 이해하고, Microsoft Project 데이터를 조작하며, Microsoft Project를 설치하지 않으면 서버를 관리할 수 있는 강력한 Java API입니다. 각 단계를 살펴보고, 각 라인이 왜 중요한지 설명하며, 실제 프로젝트에 적용할 수 있는 실용적인 팁을 제공합니다.

## 빠른 답변
- **“할당 종료(정지 할당)”는 무엇을 의미합니까?** 특정 종료 날짜부터 릴레이션에 참여하여 비활성 상태로 표시됩니다.
- **같은 사건을 나중에 다시 시작할 수 있을까요?** 예, 같은 시리즈에 다시 날짜를 설정하면 됩니다.
- **이 API를 사용하려면 Microsoft Project가 필요합니까?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 작동합니다.
- **Java 버전이 필요합니까?** Java8 이상을 추천합니다.
- **라이브러리를 거부할 수 있나요?** 공식 Aspose.Tasks Java 다운로드 페이지에서.

## Aspose.Tasks의 맥락에서 "할당을 중지하는 방법"은 무엇입니까?
Aspose.Tasks 확장에서 "할당 종료 방법"은 해당 작업을 종료하면 던지는 **중지 날짜** 이후부터 **재개 데이트**(있는 경우)까지 연결된 작업을 무시하는 것을 의미합니다. 휴가, 장비 가동 중단 등이 유효한 상태가 아니어야 하는 기간을 처리하는 데 유용합니다.

## 리소스 할당을 관리하기 위해 Aspose.Tasks를 사용하는 이유는 무엇입니까?
- **Microsoft Project가 필요하지 않습니다** – .mpp 파일을 직접 작업합니다.
- **날짜에 대한 완전한 제어** – 프로그래밍 방식으로 종료, 재개 날짜를 확인하고 참여할 수 있습니다.
- **크로스 플랫폼** – Java를 지원하는 모든 OS에서 실행됩니다.
- **풍부한 API** – 사용자 정의 보고를 위해 확장할 수 있는 *리소스에 관한 샘플*을 제공합니다.

## 전제 조건
시작하기 전에 다음 준비가 되어 있는지 확인하십시오:

- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Aspose.Tasks for Java 라이브러리를 다운로드했습니다. [여기](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.
- Java 프로그래밍에 대한 기본적인 이해가 필요합니다.

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

## 1단계: 프로젝트 파일 불러오기
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

여기서는 **프로젝트 파일 Java** 형식(`.mpp`)을 읽고 `Project` 객체를 생성하여 리소스 할당을 포함한 모든 프로젝트 데이터에 접근합니다.

## 2단계: 리소스 할당 검토
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

**최소 날짜**를 설정하여 자리 표시자 날짜를 필터링한 뒤 각 할당을 반복합니다. 이는 할당을 검사하거나 수정해야 할 때 일반적으로 사용되는 *리소스 할당 예제* 패턴입니다.

## 3단계: 종료 및 재개 날짜 확인
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

이 블록에서는 각 할당에 대해 **중지 날짜**와 **재개 날짜**를 확인합니다. 날짜가 `minDate` 이전이면 설정되지 않은 것으로 간주(`"NA"`); 그렇지 않으면 실제 날짜를 출력합니다. 이 로직은 **리소스 할당을 올바르게 관리**하는 데 필수적입니다.

## 일반적인 문제 및 해결 방법
- **Null 날짜** – `ra.get(Asn.STOP)`은 `null`을 반환할 수 있습니다. `.before(minDate)`를 호출하기 전에 null 체크를 추가해 주시기 바랍니다.
- **잘못된 파일** – `dataDir`이 OS에 맞는 잘못된 오류(`/` 또는 `\\`)로 표시되도록 확인하세요.
- **서비스 제공** – 참고할 수 있는 열거형 값을 방지하려면 최신 Aspose.Tasks for Java 버전을 사용하세요.

## 자주 묻는 질문

**Q: 과제 종료 날짜를 프로그래밍 방식으로 설정하려면 어떻게 해야 하나요?**
A: `ra.set(Asn.STOP, yourDateObject);`를 사용합니다. 여기 `yourDateObject`는 `java.util.Date`를 받는 것입니다.

**Q: 재개 날짜가 중지 날짜보다 빠르면 어떻게 되나요?**
A: API는 연대를 위해 힘쓰지 않고, 덤프러는 두 날짜 중 더 많은 날짜 이후부터 처음으로 활발하게 활동합니다. 따라서 데이트를 직접 확인해야 합니다.

**Q: 중지 날짜가 설정된 할당으로만 할당을 필터링할 수 있나요?**
A: 예, `prj.getResourceAssignments()`를 반복하면서 `ra.get(Asn.STOP) != null`인지 확인하면 됩니다.

**Q: 일단 설정된 중지 날짜를 제거할 수 있습니까?**
A: `ra.set(Asn.STOP, null);`을 실행 종료 날짜를 `null`로 설정한 후 프로젝트를 생성하면 됩니다.

**Q: Aspose.Tasks는 시작, 종료 또는 실제 시작과 같은 다른 날짜 관련 필드를 지원합니까?**
A: 물론입니다. `Asn` 열거형은 `Asn.START`, `Asn.FINISH` 등 모든 필드에 대한 도움을 제공합니다.

## 결론
이 단계에 따라 **할당 중지 방법**을 알고, 종료/재개 날짜를 검사해야 하며 시을 재개할 수 있습니다. 이 특별한 이벤트를 통해 장비 가동 중단과 같은 상황에서 기능을 제공할 수 있습니다. **리 소스를 좀 더 정밀하게 관리**할 수 있습니다. 예제를 확장하여 날짜 업데이트 보고서를 생성하고, 자체 기능을 제공하거나 통합해 보세요.

---

**최종 업데이트:** 2026-01-10
**테스트 대상:** Java 24.12용 Aspose.Tasks
**저자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}