---
date: 2025-12-09
description: Java를 사용하여 Aspose.Tasks에서 데이터 디렉터리를 설정하고 간트 차트 보기를 구성하는 방법을 배웁니다. 이 가이드는
  또한 테이블 필드를 사용자 정의하고 간트 차트 Java 프로젝트를 단계별로 구성하는 방법을 보여줍니다.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 간트 차트 보기용 데이터 디렉터리 설정
url: /ko/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 Gantt 차트 보기용 데이터 디렉터리 설정

## 소개
이 튜토리얼에서는 **데이터 디렉터리 설정 방법**을 배우고 Java를 사용하여 Aspose.Tasks 프로젝트에서 Gantt MS Project 차트 보기를 구성하는 방법을 배웁니다. Aspose.Tasks는 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 Java API입니다. 이 가이드를 마치면 **테이블 필드 사용자 정의**, 데이터 디렉터리 조정, 프로젝트를 원하는 대로 시각화할 수 있게 됩니다.

## 빠른 답변
- **첫 번째 단계는 무엇인가요?** 프로젝트 파일이 있는 데이터 디렉터리 경로를 설정합니다.  
- **필요한 라이브러리는?** 공식 사이트에서 다운로드할 수 있는 Aspose.Tasks for Java.  
- **사용자 정의 속성을 추가할 수 있나요?** 예 – 확장 속성을 정의하고 Gantt 차트에 표시할 수 있습니다.  
- **테스트에 라이선스가 필요합니까?** 평가용으로 임시 라이선스를 사용할 수 있습니다.  
- **어떤 IDE가 가장 좋나요?** IntelliJ IDEA, Eclipse, NetBeans 등 모든 Java IDE에서 작동합니다.

## “데이터 디렉터리 설정”이란 무엇이며 왜 중요한가요?
데이터 디렉터리를 설정하면 Aspose.Tasks에 프로젝트 파일을 읽고 쓸 위치를 알려줍니다. 올바른 경로가 없으면 API가 `.mpp` 파일을 찾지 못해 FileNotFound 오류가 발생합니다. 코드 시작 부분에서 이 디렉터리를 정의하면 이후 워크플로우가 깔끔하고 재현 가능해집니다.

## Gantt 차트에서 테이블 필드를 사용자 정의하는 이유는?
사용자 정의 테이블 필드를 사용하면 사용자 정의 속성, 리소스 데이터, 프로젝트별 메모와 같은 추가 정보를 Gantt 보기에서 직접 표시할 수 있습니다. 이를 통해 차트가 이해관계자에게 더 유용해지고 여러 보고서를 전환할 필요가 줄어듭니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 최신 버전(8 이상) 중 하나.  
2. **Aspose.Tasks Library** – [here](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java 호환 편집기.

## 패키지 가져오기
먼저 Aspose.Tasks 네임스페이스를 가져와 해당 클래스를 사용할 수 있게 합니다:

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 단계 1: 데이터 디렉터리 설정
프로젝트 파일이 들어 있는 폴더를 정의합니다. 이것이 튜토리얼에서 중점적으로 다루는 **데이터 디렉터리 설정** 단계입니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 2: 프로젝트 파일 로드
기존 Microsoft Project 파일을 로드하여 `Project` 인스턴스를 생성합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 단계 3: 새 작업 추가
프로젝트 루트에 새 작업(액티비티)을 삽입합니다.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 단계 4: 사용자 정의 속성 정의
작업에 나중에 연결할 수 있는 사용자 정의 속성 정의를 생성합니다.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 단계 5: 작업에 사용자 정의 속성 추가
새로 정의한 속성을 생성한 작업에 할당합니다.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 단계 6: 테이블 사용자 정의 – **테이블 필드 사용자 정의**
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
변경 사항을 Microsoft Project에서 열 수 있는 새 파일에 저장합니다.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 일반적인 문제 및 해결책

| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **FileNotFoundException** when loading the project | **데이터 디렉터리** 경로가 올바르지 않거나 끝에 슬래시가 없습니다. | `dataDir`이 정확한 폴더를 가리키는지 확인하고 올바른 파일 구분자(`/` 또는 `\\`)를 포함하십시오. |
| Gantt 보기에서 사용자 정의 속성이 보이지 않음 | 테이블 필드가 잘못된 인덱스에 추가되었거나 열 너비가 너무 작습니다. | `table.getTableFields().add(3, attrField);`가 유효한 인덱스를 사용하도록 하고 필요에 따라 `setWidth`를 조정하십시오. |
| 저장 시 LicenseException | 프로덕션 사용을 위한 유효한 라이선스가 적용되지 않았습니다. | `project.save()`를 호출하기 전에 임시 또는 영구 라이선스를 적용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 .NET, Java, C++ 등 여러 프로그래밍 언어에서 사용할 수 있습니다.

**Q: Aspose.Tasks의 무료 체험판이 있나요?**  
A: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks 지원을 어디서 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받고 질문할 수 있습니다.

**Q: Aspose.Tasks 라이선스를 어떻게 구매하나요?**  
A: [here](https://purchase.aspose.com/buy)에서 라이선스를 구매할 수 있습니다.

**Q: 테스트 목적으로 임시 라이선스가 필요합니까?**  
A: 예, [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 얻을 수 있습니다.

## 결론
이제 Aspose.Tasks for Java를 사용하여 **데이터 디렉터리 설정**, 새 작업 추가, 사용자 정의 속성 정의 및 연결, 그리고 Gantt 차트 보기에서 **테이블 필드 사용자 정의** 방법을 배웠습니다. 이러한 단계로 프로젝트 데이터 표시를 완전히 제어할 수 있어 Gantt 차트를 보다 유용하고 이해관계자 요구에 맞게 맞춤화할 수 있습니다.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}