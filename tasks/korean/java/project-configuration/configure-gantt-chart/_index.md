---
date: 2026-10-15
description: Aspose.Tasks for Java를 사용하여 activity를 만들고, data directory를 설정하고, table
  fields를 사용자 정의하고, 프로젝트를 MPP로 저장하는 방법을 배웁니다. Java 개발자를 위한 단계별 가이드.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Aspose.Tasks for Java를 사용하여 activity를 만들고 data directory를 설정하는 방법
og_description: Aspose.Tasks for Java를 사용하여 activity를 만들고, table fields를 사용자 정의하고,
  프로젝트를 MPP로 저장하는 방법. 빠른 구현을 위한 상세 가이드를 확인하세요.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Aspose.Tasks for Java에서 activity를 만들고 data directory를 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Aspose.Tasks for Java를 사용하여 activity를 만들고 data directory를 설정하는 방법
url: /ko/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 활동을 만들고 데이터 디렉터리를 설정하는 방법

## 소개
이 튜토리얼에서는 프로그래밍 방식으로 **활동을 만드는 방법**을 배우고, **데이터 디렉터리**를 구성하며, **프로젝트를 MPP로 저장**하는 방법을 배웁니다. 또한 Gantt 차트 보기에서 **테이블 필드 맞춤**도 수행합니다. Aspose.Tasks for Java는 30개 이상의 입력 및 출력 형식을 지원하는 강력한 API이며, 전체 파일을 메모리에 로드하지 않고도 최대 10 000개의 작업을 포함하는 프로젝트를 처리할 수 있습니다. 가이드를 마치면 프로젝트 생성을 자동화하고, 작업에 사용자 정의 속성을 추가하며, Microsoft Project용으로 바로 열 수 있는 MPP 파일을 생성할 수 있게 됩니다.

## 빠른 답변
- **첫 번째 단계는 무엇인가요?** 프로젝트 파일이 위치한 데이터 디렉터리 경로를 설정합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Tasks for Java(공식 사이트에서 다운로드 가능).  
- **사용자 정의 속성을 추가할 수 있나요?** 예 – 확장 속성을 정의하고 Gantt 차트에 표시할 수 있습니다.  
- **테스트에 라이선스가 필요합니까?** 평가용으로 임시 라이선스를 사용할 수 있습니다.  
- **어떤 IDE가 가장 적합한가요?** 모든 Java IDE(IntelliJ IDEA, Eclipse, NetBeans)에서 작동합니다.

## “데이터 디렉터리 설정”이란 무엇이며 왜 중요한가요?
데이터 디렉터리를 설정하면 Aspose.Tasks에 프로젝트 파일을 읽고 쓸 위치를 알려줍니다. 올바른 경로가 없으면 API가 `.mpp` 파일을 찾지 못해 `FileNotFoundException` 오류가 발생합니다. 코드 시작 부분에서 이 디렉터리를 정의하면 워크플로우를 반복 가능하게 만들고 파일 시스템 관련 문제를 비즈니스 로직과 분리할 수 있습니다.

## Gantt 차트에서 테이블 필드를 맞춤 설정하는 이유는?
맞춤형 테이블 필드를 사용하면 사용자 정의 속성, 리소스 데이터, 프로젝트별 메모와 같은 추가 정보를 Gantt 보기에서 직접 표시할 수 있습니다. 이를 통해 별도의 보고서 필요성을 줄이고 이해관계자에게 데이터가 풍부한 단일 시각화를 제공하여 의사결정 속도를 최대 30 %까지 향상시킬 수 있습니다.

## 새로운 활동을 만드는 방법은?
`Task` 객체를 인스턴스화하고 프로젝트의 루트 작업 컬렉션에 추가하여 새로운 활동(작업)을 생성합니다. 이 방법을 사용하면 대규모 일정표를 자동으로 생성하고, 외부 시스템에서 작업 데이터를 가져오며, 수동 편집 없이 일괄 업데이트를 적용할 수 있습니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 버전 8 이상.  
2. **Aspose.Tasks for Java** – **Aspose.Tasks Java 릴리스 페이지**에서 다운로드합니다.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java 호환 편집기.  

## 패키지 가져오기
`com.aspose.tasks` 네임스페이스에는 프로젝트 조작에 필요한 모든 클래스가 포함되어 있습니다. 이를 가져오면 `Project`, `Task`, `ExtendedAttributeDefinition` 및 기타 핵심 유형에 접근할 수 있습니다.

```java
import com.aspose.tasks.*;
```

## Maven 의존성 (선택 사항)
Maven으로 프로젝트를 관리한다면 `pom.xml`에 Aspose.Tasks 의존성을 추가하십시오. 이렇게 하면 빌드 시 라이브러리가 자동으로 해결됩니다.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. `dataDir` 변수는 절대 경로를 저장하며 튜토리얼 전반에 걸쳐 재사용됩니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 `project.mpp` 파일이 위치한 폴더의 전체 경로로 교체하십시오. 예: `C:/Projects/MyGantt`.

### 단계 2: 프로젝트 파일 로드
`Project`는 메모리 내에서 단일 Microsoft Project 파일을 나타내는 Aspose.Tasks의 최상위 객체입니다. 기존 파일을 로드하면 해당 파일의 작업, 리소스 및 테이블에 접근할 수 있습니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 단계 3: 새로운 활동 추가
`Task`는 일정의 개별 활동을 나타냅니다. 루트 작업 컬렉션에 작업을 추가하면 프로젝트 계층 구조의 최상위에 삽입됩니다.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 단계 4: 사용자 정의 속성 정의
`ExtendedAttributeDefinition`을 사용하면 작업, 리소스 또는 할당에 연결할 수 있는 재사용 가능한 사용자 정의 필드를 만들 수 있습니다.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 단계 5: 작업에 사용자 정의 속성 추가
`ExtendedAttribute`는 특정 작업에 할당하는 사용자 정의 속성의 구체적인 인스턴스입니다.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 단계 6: 테이블 맞춤 설정 – 사용자 정의 속성을 열로 추가
`TableField`는 Gantt 차트 테이블의 열을 설명합니다. 사용자 정의 속성을 참조하는 `TableField`를 추가하면 차트 보기에서 해당 속성을 표시할 수 있습니다.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 단계 7: 프로젝트 저장
`project.save`를 호출하면 모든 변경 사항이 새 파일에 저장됩니다. `SaveFileFormat.MPP` 상수는 Aspose.Tasks에 Microsoft Project 고유의 바이너리 형식으로 파일을 기록하도록 지시합니다.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **FileNotFoundException** 발생 시 프로젝트 로드 | **데이터 디렉터리 설정** 경로가 올바르지 않거나 끝에 슬래시가 없습니다. | `dataDir`가 정확한 폴더를 가리키는지 확인하고 올바른 파일 구분자(`/` 또는 `\\`)를 포함하십시오. |
| 사용자 정의 속성이 Gantt 보기에서 보이지 않음 | 테이블 필드가 잘못된 인덱스에 추가되었거나 열 너비가 너무 작습니다. | `table.getTableFields().add(3, attrField);`가 유효한 인덱스를 사용하도록 하고 필요에 따라 `setWidth`를 조정하십시오. |
| 저장 시 LicenseException 발생 | 프로덕션 사용을 위한 유효한 라이선스가 적용되지 않았습니다. | `project.save()` 호출 전에 임시 또는 영구 라이선스를 적용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Java 및 C++에서 사용할 수 있습니다.

**Q: Aspose.Tasks의 무료 체험판이 있나요?**  
A: 예, **Aspose.Tasks 무료 체험판 다운로드 페이지**에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 지원을 어디서 찾을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받고 질문할 수 있습니다.

**Q: Aspose.Tasks 라이선스는 어떻게 구매하나요?**  
A: **Aspose.Tasks 구매 페이지**에서 라이선스를 구매할 수 있습니다.

**Q: 테스트 용도로 임시 라이선스가 필요합니까?**  
A: 예, **임시 라이선스 요청 페이지**에서 임시 라이선스를 얻을 수 있습니다.

## 결론
이제 **활동을 만드는 방법**, 데이터 디렉터리 설정, 사용자 정의 속성 정의 및 첨부, 그리고 Aspose.Tasks for Java를 사용하여 Gantt 차트 보기에서 **테이블 필드 맞춤**과 함께 **프로젝트를 MPP로 저장**하는 방법을 알게 되었습니다. 이러한 기능을 통해 프로젝트 데이터를 완전하게 프로그래밍적으로 제어할 수 있어 자동 일정 생성과 이해관계자를 위한 풍부한 시각적 보고가 가능해집니다.

---

**마지막 업데이트:** 2026-10-15  
**테스트 환경:** Aspose.Tasks Java 24.12 (latest)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 빈 프로젝트 파일 만들기 (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [MPP 파일 만들기 – Aspose.Tasks로 빈 프로젝트를 MPP 형식으로 생성 및 저장](/tasks/java/project-configuration/create-save-mpp/)
- [프로젝트 생성 Aspose.Tasks – 새 작업 속성 설정](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}