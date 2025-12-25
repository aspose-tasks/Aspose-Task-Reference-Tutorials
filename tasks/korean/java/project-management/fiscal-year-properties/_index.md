---
date: 2025-12-25
description: Aspose.Tasks for Java를 사용하여 회계연도 속성을 관리하고 MPP 파일을 효율적으로 로드하는 방법을 배웁니다.
  예제와 함께 단계별 가이드.
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 회계 연도 속성 관리하기
url: /ko/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 회계연도 속성 관리

## 소개
Aspose.Tasks는 강력한 Java 라이브러리로, **회계연도** 설정을 관리하고, MPP 파일을 로드하며, 프로젝트 데이터를 몇 줄의 코드만으로 XML로 변환할 수 있습니다. 이 튜토리얼에서는 회계연도 속성을 설정하고, 회계연도 정보를 표시하며, 결과를 저장하는 방법을 단계별로 보여줍니다. 코드는 깔끔하고 유지보수가 쉬운 형태로 작성됩니다.

## 빠른 답변
- **Aspose.Tasks에서 “회계연도 관리”란 무엇인가요?** 회계연도 시작 월을 정의하고 프로젝트에 회계연도 번호 매기기를 활성화할 수 있습니다.  
- **회계연도 시작 월을 어떻게 설정하나요?** `Prj.FY_START_DATE` 속성에 `Month` 열거형 값(예: `Month.JULY`)을 사용합니다.  
- **MPP 파일을 로드할 수 있나요?** 예, *.mpp* 파일 경로를 지정해 `Project` 인스턴스를 생성하면 됩니다.  
- **MPP를 XML로 변환하려면?** 원하는 속성을 설정한 뒤 `project.save(..., SaveFileFormat.Xml)`을 호출합니다.  
- **라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.

## 프로젝트 파일에서 “회계연도 관리”란?
회계연도 관리는 재무 보고를 위해 프로젝트가 따르는 달력을 구성하는 것을 의미합니다. 여기에는 회계연도 시작 월을 설정하고, 필요에 따라 회계연도 번호 매기기를 활성화하는 작업이 포함되며, 이는 날짜 계산 및 보고서 표시 방식에 영향을 줍니다.

## Aspose.Tasks를 회계연도 처리에 사용하는 이유
- **Microsoft Project가 필요 없음** – Java에서 직접 프로젝트 파일을 다룰 수 있습니다.  
- **전체 제어** – 회계연도 시작을 설정하고, 번호 매기기를 활성화하며, 형식을 프로그래밍 방식으로 변환합니다.  
- **견고한 API** – 대용량 MPP 파일을 안정적으로 처리하고 XML 내보내기를 원활하게 수행합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있어야 합니다:
1. 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java JAR – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하고 프로젝트 클래스패스에 추가합니다.

## 패키지 가져오기
Java 소스 파일에 필요한 클래스를 가져옵니다:
```java
import com.aspose.tasks.*;
```

## MPP 파일을 로드하고 회계연도 정보를 표시하는 방법
아래에서는 과정을 명확한 단계로 나누어 설명합니다.

### 단계 1: 프로젝트 파일 로드
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
여기서는 지정된 디렉터리의 `project.mpp` **MPP 파일을 로드**합니다. 이는 회계연도와 관련된 모든 조작의 첫 번째 단계입니다.

### 단계 2: 회계연도 속성 표시
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE`와 `Prj.FISCAL_YEAR_START` 속성을 사용해 **회계연도** 세부 정보를 표시하고, 현재 회계구성이 어떻게 설정되어 있는지 확인합니다.

### 단계 3: 회계연도 시작 설정 및 번호 매기기 활성화
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
이 단계에서는 **회계연도 설정 방법**을 보여줍니다:
- `Month.JULY`는 회계연도 시작 월을 정의합니다.  
- `NullableBool(true)`는 회계연도 번호 매기기를 켭니다.  
- 마지막으로 `SaveFileFormat.Xml`을 사용해 프로젝트를 **MPP에서 XML로 변환**합니다.

### 단계 4: 작업 확인
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
간단한 콘솔 메시지를 통해 회계연도가 정상적으로 구성되고 파일이 저장되었음을 확인합니다.

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|-------|----------|
| **잘못된 월 값** | `Month` 열거형(예: `Month.JANUARY`)을 사용했는지 확인합니다. |
| **파일을 찾을 수 없음** | `dataDir`이 올바른 폴더를 가리키는지, 파일 이름이 정확한지 확인합니다. |
| **저장 실패** | 대상 디렉터리에 대한 쓰기 권한을 확인하고 `SaveFileFormat`이 지원되는지 점검합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 사용해 다른 프로젝트 속성도 조작할 수 있나요?**  
A: 예, Aspose.Tasks는 회계연도 설정 외에도 다양한 프로젝트 속성을 관리할 수 있는 포괄적인 기능을 제공합니다.

**Q: Aspose.Tasks for Java가 다양한 프로젝트 파일 형식을 지원하나요?**  
A: 예, MPP, XML 등 다양한 형식을 지원합니다.

**Q: Aspose.Tasks for Java 사용 중 문제가 발생하면 어떻게 지원받을 수 있나요?**  
A: [포럼](https://forum.aspose.com/c/tasks/15)에서 커뮤니티에 문의하거나 직접 지원팀에 연락하면 됩니다.

**Q: 무료 체험 버전을 제공하나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험 버전을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java 라이선스는 어디서 구매하나요?**  
A: [여기](https://purchase.aspose.com/buy)에서 Aspose.Tasks for Java 라이선스를 구매할 수 있습니다.

## 결론
Aspose.Tasks for Java에서 회계연도 속성을 관리하는 것은 매우 간단합니다. 위 단계들을 따르면 **회계연도 관리**, **MPP 파일 로드**, **회계연도 상세 정보 표시**, 그리고 **MPP를 XML로 변환**하는 작업을 자신 있게 수행할 수 있습니다. 이러한 기술을 활용해 프로젝트 일정이 조직의 재무 캘린더와 일치하도록 유지하세요.

---

**마지막 업데이트:** 2025-12-25  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}