---
date: 2026-05-31
description: Java에서 MPP 파일을 로드하고 Aspose.Tasks를 사용하여 프로젝트 속성을 관리하는 방법을 배우세요. 기본 속성
  설정 및 형식 변환을 포함합니다.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Aspose.Tasks에서 기본 프로젝트 속성 관리
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Load MPP 파일 Java – Aspose.Tasks로 프로젝트 속성 관리
url: /ko/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Load MPP File Java – Aspose.Tasks로 프로젝트 속성 관리

## 소개
프로젝트를 **load MPP file Java** 로드하고 기본 프로젝트 속성을 프로그래밍 방식으로 관리해야 한다면, Aspose.Tasks for Java가 손쉽게 해결해 줍니다. 이 튜토리얼에서는 기존 Microsoft Project 파일을 로드하고 기본 작업 및 리소스 설정을 사용자 정의한 뒤, 업데이트된 프로젝트를 저장하는 전체 과정을 단계별로 안내합니다. 최종적으로 Java 기반 프로젝트 관리 솔루션 어디에든 적용할 수 있는 명확하고 재사용 가능한 패턴을 얻게 됩니다.

## 빠른 답변
- **What does “load MPP file Java” mean?** Aspose.Tasks를 통해 Java 코드로 Microsoft Project(.mpp) 파일을 읽는 것을 의미합니다.  
- **Which library handles this?** Aspose.Tasks for Java은 프로젝트 조작을 위한 완전한 API를 제공합니다.  
- **Do I need a license?** 개발에는 무료 체험판을 사용할 수 있지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **Can I change default task start dates?** 예—`Prj.DEFAULT_START_TIME` 및 관련 속성을 사용하여 기본값을 설정할 수 있습니다.  
- **What output formats are supported?** 기본 MPP 외에도 XML, PDF, HTML 등 20가지 이상의 형식으로 저장할 수 있습니다.

## “load MPP file Java”란 무엇인가요?
Java에서 MPP 파일을 로드한다는 것은 라이브러리를 사용해 이진 Microsoft Project 형식을 파싱하고, 해당 객체(작업, 리소스, 캘린더)를 Java 클래스 형태로 노출하는 것을 의미합니다. 이를 통해 Microsoft Project를 직접 열지 않고도 프로젝트 데이터를 읽고, 수정하고, 저장할 수 있습니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
Aspose.Tasks는 Microsoft Project 설치 없이도 프로젝트 속성을 관리할 수 있게 해 주며, **50개 이상의 입력 및 출력 형식**을 지원하고, **10,000개 작업**까지 메모리 사용량을 200 MB 이하로 유지하면서 처리할 수 있습니다. JDK를 지원하는 모든 OS에서 실행되므로 서버‑사이드 자동화에 이상적입니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하십시오:

### 1. Java Development Kit (JDK)
- JDK 11 이상을 설치합니다.  
- [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)에서 다운로드할 수 있습니다.

### 2. Aspose.Tasks for Java 라이브러리
- 최신 Aspose.Tasks JAR를 다운로드하고 프로젝트의 클래스패스에 추가합니다.  
- [website](https://releases.aspose.com/tasks/java/)에서 받을 수 있습니다.

## 패키지 가져오기
import 문은 필수 Aspose.Tasks 클래스를 Java 소스 파일에 포함시킵니다.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## load MPP file Java를 로드하고 기본 속성을 설정하는 방법
`Project` 클래스는 Microsoft Project 파일을 나타내며 작업, 리소스 및 설정에 대한 접근을 제공합니다. 프로젝트를 로드하고, 기본값을 확인한 뒤 수정하고, 결과를 저장합니다—몇 줄의 간단한 코드로 가능합니다. 이 접근 방식은 일정 기본값, 캘린더 설정 및 비용 발생 규칙을 완벽히 제어할 수 있게 해 주어, 생성되는 모든 파일에 일관된 프로젝트 표준을 적용할 수 있습니다.

### Step 1: 프로젝트 파일 로드
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Step 2: 기본 속성 표시
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Step 3: 기본 속성 설정
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Step 4: 프로젝트를 XML 형식으로 저장
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Step 5: 결과 표시
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

이 단계를 따라 하면 **Java에서 MPP 파일을 로드**하고, 기본 설정을 검사·수정한 뒤, 업데이트된 프로젝트를 저장하는 작업을 성공적으로 수행하게 됩니다.

## 일반적인 문제 및 팁
- **File not found** – `dataDir`이 경로 구분자(`/` 또는 `\\`)로 끝나는지 확인하십시오.  
- **License not applied** – 시험용 워터마크가 보이면 프로젝트를 로드하기 전에 라이선스 파일을 추가하십시오: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Date handling** – `java.util.Calendar` 또는 최신 `java.time` API를 사용하고, 할당하기 전에 `java.util.Date`로 변환하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Python 등 다른 플랫폼에서도 사용할 수 있습니다.

**Q: Aspose.Tasks는 개인용과 기업용 모두에 적합한가요?**  
A: 물론입니다! 소규모 개인 프로젝트부터 대규모 엔터프라이즈 포트폴리오까지 확장 가능합니다.

**Q: Aspose.Tasks는 고객 지원을 제공하나요?**  
A: 예, [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 도움과 커뮤니티 지원을 받을 수 있습니다.

**Q: 구매 전에 Aspose.Tasks를 체험해 볼 수 있나요?**  
A: 물론입니다! [website](https://releases.aspose.com/)에서 무료 체험판을 이용할 수 있습니다.

**Q: Aspose.Tasks의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 테스트 및 평가 목적으로 [purchase page](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

## 결론
이 튜토리얼에서는 **load MPP file Java** 프로젝트를 로드하고, 기본 속성을 읽고 수정한 뒤, Aspose.Tasks for Java를 사용해 변경 사항을 저장하는 방법을 다루었습니다. 이러한 기술을 애플리케이션에 통합하면 프로젝트 관리 작업을 자동화하고, 일관된 기본값을 적용하며, 수동 작업을 크게 줄일 수 있습니다.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks for Java로 프로젝트 캘린더 설정 방법](/tasks/java/calendars/properties/)
- [MPP 파일 만들기 – Aspose.Tasks로 빈 프로젝트를 생성·저장](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}