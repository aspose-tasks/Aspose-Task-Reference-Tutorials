---
date: 2025-12-23
description: Aspose.Tasks Java를 사용하여 프로젝트 일정을 업데이트하고, 주 시작 요일을 설정하며, 월별 일수를 변경하고,
  프로젝트 캘린더를 효율적으로 맞춤 설정하는 방법을 배워보세요.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – 요일 속성 관리
url: /ko/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – 평일 속성 관리

## Introduction
Aspose.Tasks for Java (aspose tasks java)는 Microsoft Project를 설치하지 않고도 Java 개발자가 Microsoft Project 파일을 작업할 수 있게 해주는 강력한 API입니다. 이 튜토리얼에서는 **MPP 파일 로드**, **주 시작 요일 설정**, **월당 일수 변경**, 그리고 **프로젝트 캘린더 맞춤화** 방법을 배웁니다—프로젝트 일정 업데이트에 필수적인 단계들입니다. 마지막까지 진행하면 평일 속성을 프로그래밍 방식으로 조정하고 필요한 형식으로 변경 사항을 저장할 수 있게 됩니다.

## Quick Answers
- **프로젝트를 처리하기 위한 주요 클래스는 무엇인가요?** `Project` from the Aspose.Tasks library.  
- **주 시작 요일을 어떻게 변경하나요?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **기존 .mpp 파일을 로드할 수 있나요?** Yes—instantiate `Project` with the file path.  
- **프로젝트를 XML로 저장하는 메서드는 무엇인가요?** `project.save(path, SaveFileFormat.Xml)`.  
- **개발에 라이선스가 필요합니까?** A free trial works for evaluation; a license is required for production.

## Prerequisites
시작하기 전에 다음 항목이 준비되어 있는지 확인하십시오:

- **Java Development Kit (JDK)** – 최신 버전이 설치되어 있어야 합니다.  
- **Aspose.Tasks for Java library** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
- **IDE** – IntelliJ IDEA, Eclipse, NetBeans 등.

## Import Packages
시작하려면 필수 Aspose.Tasks 클래스를 가져오세요:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

이제 평일 속성을 관리하는 각 단계를 살펴보겠습니다.

## Step 1: MPP 파일 로드
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*여기서는 **기존 .mpp 파일을 로드**(`load mpp file`)하여 캘린더 설정을 검사하고 수정할 수 있습니다.*

## Step 2: 현재 평일 속성 표시
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
이 코드는 현재 **주 시작 요일**, **월당 일수**, **일당 분**, **주당 분**을 출력합니다—이는 **프로젝트 캘린더 맞춤화**에 자주 필요한 핵심 요소입니다.

## Step 3: 새로운 평일 속성 설정
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
이 단계에서는 **주 시작 요일**을 Monday로 설정하고, **월당 일수**를 24로 변경하며, 일일 및 주간 분 수를 조정합니다. 이러한 설정은 비표준 근무 캘린더에 맞게 **프로젝트 일정을 업데이트**해야 할 때 일반적입니다.

## Step 4: 업데이트된 프로젝트 저장
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
수정된 프로젝트는 XML 파일로 저장되어 다른 도구와 공유하거나 가져오기 쉽습니다.

## Step 5: 작업 확인
```java
System.out.println("Process completed Successfully");
```
간단한 콘솔 메시지를 통해 작업 흐름이 오류 없이 완료되었음을 알 수 있습니다.

## Common Issues & Tips
- **잘못된 파일 경로** – `dataDir`가 슬래시로 끝나는지 확인하거나 플랫폼에 독립적인 경로를 위해 `Paths.get(...)`를 사용하십시오.  
- **라이선스 미설정** – 운영 환경에서는 `Project`를 생성하기 전에 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`를 호출하십시오.  
- **예상치 못한 주 시작 요일** – 올바른 `DayType` 열거값(예: `DayType.Sunday`)을 사용했는지 확인하십시오.

## Frequently Asked Questions

**Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 손쉽게 처리할 수 있는 포괄적인 지원을 제공합니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일을 지원하여 플랫폼 간 호환성을 보장합니다.

**Q: 기존 Java 애플리케이션에 Aspose.Tasks for Java를 통합할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 원활한 통합 기능을 제공하므로 강력한 프로젝트 관리 기능을 Java 애플리케이션에 쉽게 추가할 수 있습니다.

**Q: Aspose.Tasks for Java가 문서와 지원을 제공하나요?**  
A: 예, Aspose.Tasks for Java에 대한 방대한 문서와 커뮤니티 지원을 [website](https://releases.aspose.com/)에서 확인할 수 있습니다.

**Q: Aspose.Tasks for Java의 무료 체험판이 있나요?**  
A: 예, 구매 전에 기능을 살펴볼 수 있도록 Aspose.Tasks for Java의 무료 체험판을 [website](https://reference.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}