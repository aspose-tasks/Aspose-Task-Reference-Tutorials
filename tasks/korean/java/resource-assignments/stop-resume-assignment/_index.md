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

# Aspose.Tasks에서 할당 중지 및 리소스 할당 재개 방법

## Introduction
이 튜토리얼에서는 **Aspose.Tasks for Java**를 사용하여 할당을 중지하고 나중에 재개하는 방법을 알아봅니다. Aspose.Tasks는 프로젝트 파일(Java 형식)을 읽고, Microsoft Project 데이터를 조작하며, Microsoft Project를 설치하지 않고도 리소스 할당을 관리할 수 있는 강력한 Java API입니다. 각 단계를 살펴보고, 각 라인이 왜 중요한지 설명하며, 실제 프로젝트에 적용할 수 있는 실용적인 팁을 제공합니다.

## Quick Answers
- **“할당 중지(stop assignment)”는 무엇을 의미합니까?** 특정 중지 날짜부터 리소스 할당을 일시적으로 비활성 상태로 표시합니다.  
- **같은 할당을 나중에 재개할 수 있나요?** 예, 동일한 할당에 재개 날짜를 설정하면 됩니다.  
- **이 API를 사용하려면 Microsoft Project가 필요합니까?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 작동합니다.  
- **필요한 Java 버전은?** Java 8 이상을 권장합니다.  
- **라이브러리를 어디서 다운로드할 수 있나요?** 공식 Aspose.Tasks Java 다운로드 페이지에서.

## What is “how to stop assignment” in the context of Aspose.Tasks?
Aspose.Tasks 컨텍스트에서 “할당 중지 방법”은 할당을 중지하면 스케줄러가 **중지 날짜** 이후부터 **재개 날짜**(있는 경우)까지 리소스에 할당된 작업을 무시하도록 지시하는 것을 의미합니다. 이는 휴가, 장비 가동 중지 등 리소스가 활성 상태가 아니어야 하는 기간을 처리하는 데 유용합니다.

## Why use Aspose.Tasks to manage resource assignments?
- **Microsoft Project가 필요 없음** – .mpp 파일을 직접 작업합니다.  
- **날짜에 대한 완전한 제어** – 프로그래밍 방식으로 중지 날짜, 재개 날짜를 확인하고 조정할 수 있습니다.  
- **크로스 플랫폼** – Java를 지원하는 모든 OS에서 실행됩니다.  
- **풍부한 API** – 사용자 정의 보고를 위해 확장할 수 있는 *리소스 할당 예제*를 제공합니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
- Aspose.Tasks for Java 라이브러리를 다운로드했습니다. [here](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
- Java 프로그래밍에 대한 기본 이해가 필요합니다.  

## Import Packages
First, let's import the necessary packages into our Java project:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

여기서는 **프로젝트 파일 Java** 형식(`.mpp`)을 읽고 `Project` 객체를 생성하여 리소스 할당을 포함한 모든 프로젝트 데이터에 접근합니다.

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

**최소 날짜**를 설정하여 자리 표시자 날짜를 필터링한 뒤 각 할당을 반복합니다. 이는 할당을 검사하거나 수정해야 할 때 일반적으로 사용되는 *리소스 할당 예제* 패턴입니다.

## Step 3: Check Stop and Resume Dates
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

## Common Issues and Solutions
- **Null 날짜** – `ra.get(Asn.STOP)`은 `null`을 반환할 수 있습니다. `.before(minDate)`를 호출하기 전에 null 체크를 추가하여 방어하십시오.  
- **잘못된 파일 경로** – `dataDir`이 OS에 맞는 경로 구분자(`/` 또는 `\\`)로 끝나는지 확인하십시오.  
- **버전 불일치** – 누락된 enum 값을 방지하려면 최신 Aspose.Tasks for Java 버전을 사용하십시오.

## FAQ's
### Can I use Aspose.Tasks without Microsoft Project installed?
예, Aspose.Tasks를 사용하면 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일을 작업할 수 있습니다.

### Where can I find more documentation?
자세한 문서는 [here](https://reference.aspose.com/tasks/java/)에서 확인할 수 있습니다.

### Is there a free trial available?
예, 무료 체험판은 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

### How can I get support if I encounter any issues?
커뮤니티 지원은 [here](https://forum.aspose.com/c/tasks/15)에서 받을 수 있습니다.

### Can I purchase a temporary license?
예, 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.

## Frequently Asked Questions

**Q: How do I programmatically set a stop date for an assignment?**  
A: `ra.set(Asn.STOP, yourDateObject);`을 사용합니다. 여기서 `yourDateObject`는 `java.util.Date` 객체입니다.

**Q: What happens if the resume date is earlier than the stop date?**  
A: API는 연대순을 강제하지 않지만, 스케줄러는 두 날짜 중 더 늦은 시점 이후에만 할당을 활성으로 간주합니다. 따라서 날짜를 직접 검증해야 합니다.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: 예, `prj.getResourceAssignments()`를 반복하면서 `ra.get(Asn.STOP) != null`인지 확인하면 됩니다.

**Q: Is it possible to remove a stop date once set?**  
A: `ra.set(Asn.STOP, null);`을 사용해 중지 날짜를 `null`로 설정한 뒤 프로젝트를 저장하면 됩니다.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: 물론입니다. `Asn` enum은 `Asn.START`, `Asn.FINISH` 등 모든 할당 필드에 대한 상수를 제공합니다.

## Conclusion
이 단계를 따라 하면 **할당 중지 방법**을 알고, 중지/재개 날짜를 검사하며 필요 시 할당을 재개할 수 있습니다. 이 기능을 통해 특히 리소스 휴가나 장비 가동 중지와 같은 상황에서 **리소스 할당을 보다 정밀하게 관리**할 수 있습니다. 예제를 확장하여 날짜를 업데이트하거나 보고서를 생성하고, 자체 스케줄링 로직에 통합해 보세요.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}