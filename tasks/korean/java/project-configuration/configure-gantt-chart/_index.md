---
date: 2026-02-13
description: Aspose.Tasks Java에서 새 활동을 만들고, 데이터 디렉터리를 설정하며, 프로젝트를 MPP 형식으로 저장하는 방법을
  배웁니다. 이 단계별 가이드는 테이블 필드 사용자 정의도 다룹니다.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 새 활동을 만들고 데이터 디렉터리를 설정하는 방법
url: /ko/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 새 활동 만들기 및 데이터 디렉터리 설정 Aspose.Tasks

## 소개
이 튜토리얼에서는 **데이터 디렉터리 설정 방법**, **새 활동 만들기**, 그리고 Gantt MS Project 차트 뷰를 구성하면서 **프로젝트를 MPP 형식으로 저장**하는 방법을 배웁니다. Aspose.Tasks는 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 Java API입니다. 이 가이드를 마치면 **테이블 필드 사용자 정의**, 데이터 디렉터리 조정, 그리고 프로젝트를 원하는 대로 시각화하는 방법을 익히게 됩니다.

## 빠른 답변
- **첫 번째 단계는?** 프로젝트 파일이 위치한 데이터 디렉터리 경로를 설정합니다.  
- **필요한 라이브러리는?** 공식 사이트에서 다운로드할 수 있는 Aspose.Tasks for Java.  
- **사용자 정의 속성을 추가할 수 있나요?** 예 – 확장 속성을 정의하고 Gantt 차트에 표시할 수 있습니다.  
- **테스트용 라이선스가 필요한가요?** 평가용 임시 라이선스를 사용할 수 있습니다.  
- **어떤 IDE가 가장 좋나요?** Java IDE라면 IntelliJ IDEA, Eclipse, NetBeans 모두 사용 가능합니다.

## “데이터 디렉터리 설정”이란 무엇이며 왜 중요한가?
데이터 디렉터리를 설정하면 Aspose.Tasks가 프로젝트 파일을 읽고 쓸 위치를 알게 됩니다. 올바른 경로가 없으면 API가 `.mpp` 파일을 찾지 못해 **FileNotFound** 오류가 발생합니다. 코드 초반에 이 디렉터리를 정의하면 이후 워크플로가 깔끔하고 재현 가능해집니다.

## Gantt 차트에서 테이블 필드를 사용자 정의하는 이유
사용자 정의 테이블 필드를 통해 추가 정보(예: 사용자 정의 속성, 리소스 데이터, 프로젝트별 메모 등)를 Gantt 뷰에 직접 표시할 수 있습니다. 이는 이해관계자에게 차트를 더 유용하게 만들고 여러 보고서를 오가며 보는 번거로움을 줄여줍니다.

## 새 활동을 만드는 방법
새 활동(작업)을 만드는 것은 프로젝트 일정 구축·업데이트 시 핵심 작업 중 하나입니다. 작업을 프로그래밍 방식으로 추가하면 복잡한 프로젝트 계획을 자동으로 생성하고, 다른 시스템의 데이터를 통합하거나, 수동 편집 없이 대량 변경을 적용할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – 최신 버전(8 이상).  
2. **Aspose.Tasks Library** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java 호환 편집기.

## 패키지 가져오기
먼저 Aspose.Tasks 네임스페이스를 가져와 클래스들을 사용할 수 있게 합니다:

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. 이것이 튜토리얼이 중점적으로 다루는 **데이터 디렉터리 설정** 단계입니다.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 `project.mpp` 파일이 저장된 절대 경로로 교체하세요.

### 단계 2: 프로젝트 파일 로드
기존 Microsoft Project 파일을 로드하여 `Project` 인스턴스를 생성합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 단계 3: 새 활동 추가
프로젝트 루트에 새 작업(활동)을 삽입합니다. 이는 **프로그램matically 새 활동을 만드는 방법**을 보여줍니다.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 단계 4: 사용자 정의 속성 정의
나중에 작업에 연결할 수 있는 사용자 정의 속성 정의를 생성합니다.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 단계 5: 작업에 사용자 정의 속성 추가
앞서 정의한 속성을 만든 작업에 할당합니다.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 단계 6: 테이블 사용자 정의 – **customize table fields**
사용자 정의 속성을 Gantt 차트 테이블의 열로 추가하고, 너비, 제목, 정렬을 지정합니다.

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
변경 내용을 새 파일에 저장하여 Microsoft Project에서 열 수 있게 합니다. 이 단계는 **프로젝트를 MPP 형식으로 저장**합니다.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 일반적인 문제와 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **FileNotFoundException** 발생 시 | **데이터 디렉터리** 경로가 잘못되었거나 끝에 슬래시가 없음 | `dataDir`이 정확한 폴더를 가리키는지 확인하고 올바른 파일 구분자(`/` 또는 `\\`)를 포함 |
| 사용자 정의 속성이 Gantt 뷰에 표시되지 않음 | 테이블 필드가 잘못된 인덱스에 추가되었거나 열 너비가 너무 작음 | `table.getTableFields().add(3, attrField);`에서 유효한 인덱스를 사용하고 `setWidth`를 적절히 조정 |
| 저장 시 LicenseException 발생 | 프로덕션용 유효한 라이선스가 적용되지 않음 | `project.save()` 호출 전에 임시 또는 영구 라이선스를 적용 |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Java, C++ 등 여러 언어에서 사용할 수 있습니다.

**Q: Aspose.Tasks 무료 체험판이 있나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받고 질문할 수 있습니다.

**Q: Aspose.Tasks 라이선스는 어떻게 구매하나요?**  
A: [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 테스트용 임시 라이선스가 필요한가요?**  
A: 예, [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

## 결론
이제 **데이터 디렉터리 설정**, **새 활동 만들기**, 사용자 정의 속성 정의 및 할당, 그리고 **프로젝트를 MPP 형식으로 저장**하면서 **테이블 필드 사용자 정의**를 수행하는 방법을 익혔습니다. 이러한 단계들을 통해 프로젝트 데이터 표시 방식을 완전히 제어할 수 있어 Gantt 차트를 이해관계자에게 보다 유용하고 맞춤화된 형태로 제공할 수 있습니다.

---

**마지막 업데이트:** 2026-02-13  
**테스트 환경:** Aspose.Tasks Java 24.12 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}