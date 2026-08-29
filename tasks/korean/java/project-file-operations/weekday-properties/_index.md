---
date: 2026-03-29
description: Aspose.Tasks for Java에서 월별 일수를 변경하고 다른 요일 속성을 관리하는 방법을 배우세요. 주 시작 날짜를
  사용자 지정하고, 프로젝트 캘린더를 수정하며, 프로젝트를 XML로 저장합니다.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks 요일 속성을 사용하여 월별 일수 변경
url: /ko/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 요일 속성으로 월별 일수 변경

## 소개
Aspose.Tasks for Java를 사용하면 **change days per month**를 수행하고 Microsoft Project를 설치하지 않아도 다른 요일 설정을 미세 조정할 수 있습니다. 프로젝트 캘린더를 비표준 회계 월에 맞추거나 단순히 주 시작 요일을 조정해야 할 때, 이 튜토리얼에서는 현재 주 시작 요일을 가져오고, 주 시작 날짜를 사용자 지정하고, 프로젝트 캘린더를 수정하고, 프로젝트를 XML로 저장하는 가장 일반적인 시나리오를 단계별로 안내합니다.

## 빠른 답변
- **월당 일 수를 변경할 수 있나요?** 예, `Project` 객체에서 `Prj.DAYS_PER_MONTH`를 사용하십시오.  
- **주 시작 날짜를 어떻게 사용자 지정합니까?** `Prj.WEEK_START_DAY`를 `DayType` 값(예: `DayType.Monday`)으로 설정합니다.  
- **프로젝트를 내보낼 때 어떤 형식을 사용할 수 있나요?** 예제에서는 `SaveFileFormat.Xml`을 사용하여 파일을 XML로 저장합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 비평가 버전이 아닌 배포에는 유효한 Aspose.Tasks 라이선스가 필요합니다.  
- **지원되는 IDE는 무엇인가요?** IntelliJ IDEA, Eclipse, NetBeans 등 모든 Java IDE에서 작동합니다.

## Aspose.Tasks에서 “change days per month”란 무엇인가요?
월당 일 수를 변경한다는 것은 `Project` 인스턴스의 `Prj.DAYS_PER_MONTH` 속성을 업데이트하는 것을 의미합니다. 이 속성은 엔진이 각 월에 몇 개의 작업일을 고려해야 하는지를 지정하며, 작업 일정 및 비용 계산에 직접적인 영향을 미칩니다.

## 프로젝트 캘린더 속성을 수정하는 이유
프로젝트 캘린더를 사용자 지정하면(예: 다른 주 시작 요일 설정 또는 일일/주당 분 수 조정) 다음과 같은 이점을 얻을 수 있습니다:

- 지역 작업 주에 일정 맞추기.  
- 비표준 작업 패턴 모델링(예: 4일 근무 주).  
- 맞춤형 캘린더를 사용하는 계약에 대한 정확한 보고 보장.

## 전제 조건
- **Java Development Kit (JDK)** – Oracle에서 최신 JDK를 설치합니다.  
- **Aspose.Tasks for Java library** – 공식 사이트 [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
- **선택한 IDE** – IntelliJ IDEA, Eclipse 또는 NetBeans.

## 패키지 가져오기
먼저 필수 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 단계 1: 프로젝트 파일 로드
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
이 코드는 지정한 폴더에서 기존 Microsoft Project 파일(`project.mpp`)을 로드합니다.

## 단계 2: 요일 속성 표시
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
여기서는 현재 요일 설정을 가져와서 **주 시작 요일**과 **월당 일 수**를 출력합니다.

## 단계 3: 요일 속성 설정
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
이 단계에서는 **change days per month**를 24로 설정하고, 주 시작 요일을 월요일로 지정하며, 일/주당 분 수를 조정합니다. 이를 통해 **프로젝트 캘린더** 값을 프로그래밍 방식으로 수정하는 방법을 보여줍니다.

## 단계 4: 프로젝트 저장
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
수정된 프로젝트는 **XML 형식으로 프로젝트 저장**을 사용하여 저장되며, 이는 다른 도구와의 통합이나 버전 관리 저장소에 유용합니다.

## 단계 5: 결과 표시
```java
System.out.println("Process completed Successfully");
```
작업이 오류 없이 완료되었음을 간단히 확인합니다.

## 주 시작 날짜 사용자 지정 방법
조직에서 일요일을 첫 번째 요일로 사용하는 경우 `DayType.Monday`를 `DayType.Sunday`로 교체하면 됩니다. 동일한 속성(`Prj.WEEK_START_DAY`)을 사용하므로 변경이 간단합니다.

## 주 시작 요일 가져오는 방법
`project.get(Prj.WEEK_START_DAY)`를 언제든 호출하면 **주 시작 요일** 정보를 가져올 수 있으며, 이는 단계 2에서 보여준 바와 같습니다.

## 프로젝트 캘린더 수정 방법
주 시작 요일 외에도 `Prj.MINUTES_PER_DAY`와 `Prj.MINUTES_PER_WEEK`를 조정하여 맞춤형 근무 시간이나 교대 패턴을 반영할 수 있습니다.

## 일반적인 문제 및 해결책
- **잘못된 DayType 값** – `DayType` 열거형(예: `DayType.Monday`)을 사용했는지 확인하십시오.  
- **파일 경로 오류** – `dataDir`이 적절한 파일 구분자(`/` 또는 `\`)로 끝나는지 확인하십시오.  
- **라이선스 미설정** – 라이선스 경고가 표시되면 `Project` 객체를 생성하기 전에 Aspose.Tasks 라이선스를 등록하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 손쉽게 처리할 수 있는 포괄적인 지원을 제공합니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일과 호환되나요?**  
A: 물론입니다. Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일을 지원하여 플랫폼 간 호환성을 보장합니다.

**Q: 기존 Java 애플리케이션에 Aspose.Tasks for Java를 통합할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 원활한 통합 기능을 제공하므로 강력한 프로젝트 관리 기능을 Java 애플리케이션에 쉽게 추가할 수 있습니다.

**Q: Aspose.Tasks for Java가 문서와 지원을 제공하나요?**  
A: 예, Aspose.Tasks for Java에 대한 방대한 문서와 커뮤니티 지원을 [website](https://releases.aspose.com/)에서 확인할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 무료 체험판이 있나요?**  
A: 예, 구매 전에 기능을 살펴볼 수 있도록 [website](https://reference.aspose.com/tasks/java/)에서 Aspose.Tasks for Java 무료 체험판을 다운로드할 수 있습니다.

---

**마지막 업데이트:** 2026-03-29  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}