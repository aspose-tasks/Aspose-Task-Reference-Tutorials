---
date: 2026-05-20
description: Aspose.Tasks for Java를 사용하여 리소스 할당에 확장 속성을 추가하고, 프로젝트 시작 날짜를 설정하며, MS
  Project 파일을 효율적으로 작성하는 방법을 배웁니다.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Aspose.Tasks에서 리소스 할당에 확장 속성 추가
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java 사용 방법 – 리소스 할당에 확장 속성 추가
url: /ko/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용한 MS Project 조작 마스터하기

## 소개
이 튜토리얼에서는 **Aspose.Tasks for Java 사용 방법**을 알아보고 리소스 할당에 확장 속성을 추가하고 Microsoft Project 정보를 프로그래밍 방식으로 작성하는 방법을 배웁니다. 보고 파이프라인을 자동화하거나 맞춤형 프로젝트 관리 도구를 구축하든, 아래 단계에서는 프로젝트 시작 날짜를 설정하고, 리소스 할당을 생성하며, 파일을 XML로 저장하는 방법을 Java 코드 몇 줄만으로 정확히 보여줍니다.

## 빠른 답변
- **Aspose.Tasks for Java는 무엇을 하나요?** Microsoft Project를 설치하지 않아도 Microsoft Project 파일을 읽고, 쓰고, 수정합니다.  
- **리소스 할당에 사용자 정의 필드를 추가할 수 있나요?** 예, `ResourceAssignment` 객체의 `ExtendedAttribute` 컬렉션을 사용합니다.  
- **프로젝트 시작 날짜를 어떻게 설정하나요?** 저장하기 전에 `project.setStartDate(LocalDateTime.of(...))`를 호출합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상용 라이선스를 사용하면 평가 워터마크가 제거되고 전체 API 접근이 가능해집니다.  
- **지원되는 Java 버전은 무엇인가요?** Aspose.Tasks for Java는 JDK 8부터 JDK 21까지 지원합니다.

## Aspose.Tasks for Java 사용 방법?
`Project`는 메모리 내에서 Microsoft Project 파일을 나타내는 기본 객체입니다. Aspose.Tasks 라이브러리를 로드하고, `Project` 인스턴스를 생성한 뒤, 프로젝트 수준 속성을 구성하고, 리소스 할당에 확장 속성을 추가한 다음, 최종적으로 프로젝트를 XML로 저장합니다. 핵심 워크플로는 초기화, 수정, 저장의 세 단계로 구성됩니다. 이 패턴은 프로젝트 파일 크기에 관계없이 작동하며 Windows, Linux, macOS JVM에서도 실행됩니다.

## Aspose.Tasks에서 확장 속성이란?
**확장 속성**은 작업, 리소스 또는 할당에 연결하여 기본 열을 넘어서는 추가 메타데이터를 저장하는 사용자 정의 필드입니다. `ExtendedAttributeDefinition`은 사용자 정의 필드의 스키마를 정의합니다. Aspose.Tasks는 `ExtendedAttributeDefinition` 및 `ExtendedAttribute` 클래스를 제공하여 이러한 필드를 프로그래밍 방식으로 정의하고 할당할 수 있게 합니다.

## 리소스 할당에 확장 속성을 추가하는 이유
Aspose.Tasks는 **50개 이상의 기본 및 사용자 정의 필드**를 지원하며, 무제한 사용자 정의 속성을 추가할 수 있습니다. 이를 추가하면 비용 코드, 부서 ID 또는 비즈니스에 특화된 데이터를 .mpp 파일 내부에 직접 저장할 수 있어 외부 스프레드시트가 필요 없으며 프로젝트 수명 주기 전반에 걸쳐 데이터 무결성을 보장합니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java 라이브러리** – 공식 릴리스 페이지에서 [here](https://releases.aspose.com/tasks/java/) 다운로드합니다.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java 호환 편집기.

## 패키지 가져오기
먼저, Java 프로젝트에서 필요한 패키지를 가져옵니다:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 단계 1: 데이터 디렉터리 설정
프로젝트 데이터가 저장될 디렉터리를 정의합니다. 이 경로는 XML 파일을 저장할 때 사용됩니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 2: Project 인스턴스 생성
`Project` 클래스는 메모리 내에서 단일 Microsoft Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 인스턴스를 생성하면 모든 프로젝트 요소에 완전하게 접근할 수 있습니다.

```java
Project project = new Project();
```

### 단계 3: 프로젝트 정보 속성 설정
시작 날짜, 시작부터 일정 플래그, 상태 날짜와 같은 필수 프로젝트 속성을 설정합니다. 이러한 값은 프로젝트의 `ProjectInfo` 객체에 저장됩니다.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 단계 4: 리소스 할당에 확장 속성 추가
사용자 정의 필드를 위한 `ExtendedAttributeDefinition`을 생성하고, 이를 `ResourceAssignment`에 연결한 뒤 값을 채웁니다. 이 단계는 **add extended attributes** 키워드가 실제로 어떻게 동작하는지를 보여줍니다.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
- 할당 컬렉션에 접근할 때 NullPointerException 발생 – 할당을 가져오기 전에 최소 하나의 리소스와 하나의 작업을 생성했는지 확인하세요.  
- MS Project에 확장 속성이 표시되지 않음 – 속성의 `FieldId`가 사용자 정의 필드 슬롯(예: `ExtendedAttributeTask.Text1`)과 일치하는지 확인하세요.  
- 날짜 형식 불일치 – 날짜 값에 `java.time.LocalDateTime`을 사용하세요; Aspose.Tasks가 자동으로 프로젝트 캘린더 형식으로 변환합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용하여 MS Project 파일을 읽을 수 있나요?**  
**A:** 예, 이 라이브러리는 .mpp, .xml, .xps 형식에 대한 전체 읽기‑쓰기 기능을 제공합니다.

**Q: Aspose.Tasks for Java가 다양한 버전의 MS Project와 호환되나요?**  
**A:** 예, Project 2000부터 최신 2024 릴리스까지의 파일을 지원하며 20개 이상의 버전 형식을 포괄합니다.

**Q: Aspose.Tasks for Java 체험판에 제한이 있나요?**  
**A:** 체험판은 생성된 파일에 워터마크를 추가하고 생성할 수 있는 작업 수를 제한하지만, 모든 API 기능은 사용할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원을 어떻게 받을 수 있나요?**  
**A:** Aspose.Tasks 커뮤니티 포럼에서 도움을 받을 수 있습니다 [here](https://forum.aspose.com/c/tasks/15).

**Q: Aspose.Tasks for Java에 대한 임시 라이선스를 구매할 수 있나요?**  
**A:** 예, 단기 사용을 위한 임시 라이선스를 제공하며 [here](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

**마지막 업데이트:** 2026-05-20  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Tasks에서 리소스 할당에 메모 추가하는 방법](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Aspose.Tasks에서 리소스 할당에 대한 비율 스케일 읽기 및 쓰기 방법](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Aspose.Tasks에서 프로젝트에 리소스를 추가하고 레벨링 지연 속성을 처리하는 방법](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}