---
date: 2026-04-01
description: Aspose.Tasks for Java를 사용하여 XML을 저장하고 회계 연도를 설정하며 MPP를 XML로 변환하는 방법을
  배웁니다. 코드 예제가 포함된 단계별 가이드.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Aspose.Tasks에서 XML 저장 및 회계 연도 관리 방법
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 XML 저장 및 회계연도 관리 방법
url: /ko/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XML 저장 및 Aspose.Tasks에서 회계연도 관리 방법

## 소개
Microsoft Project 데이터에서 생성된 **how to save xml** 파일이 필요하다면, Aspose.Tasks for Java는 깔끔하고 라이선스‑무료인 방법을 제공합니다. 이 튜토리얼에서는 MPP 파일을 로드하고, 회계연도 정보를 표시하며, 회계연도 속성을 설정하고, 마지막으로 **how to save xml** 출력을 수행하는 과정을 단계별로 안내합니다. 또한 Microsoft Project를 열지 않고도 **how to set fiscal** 세부 정보를 확인하고 **how to convert mpp** 파일을 변환하는 방법도 보여드립니다.

## 빠른 답변
- **What does “manage fiscal year” mean in Aspose.Tasks?** 프로젝트의 회계연도 시작 월을 정의하고 회계연도 번호 매기기를 활성화할 수 있게 해줍니다.  
- **How to set fiscal year start month?** `Prj.FY_START_DATE` 속성을 `Month` 열거형 값(예: `Month.JULY`)과 함께 사용합니다.  
- **Can I load an MPP file?** 예, *.mpp* 파일 경로를 사용하여 `Project` 인스턴스를 생성하면 됩니다.  
- **How to convert MPP to XML?** `project.save(..., SaveFileFormat.Xml)`를 호출하여 원하는 속성을 설정한 후 MPP를 XML로 변환합니다.  
- **Do I need a license?** 무료 체험판을 사용할 수 있으며, 실제 운영에서는 상용 라이선스가 필요합니다.  

## 프로젝트 파일에서 “manage fiscal year”란 무엇인가요?
회계연도 관리는 재무 보고를 위해 프로젝트가 따르는 달력을 구성하는 것을 의미합니다. 여기에는 회계연도 시작 월을 설정하고 선택적으로 회계연도 번호 매기기를 활성화하는 것이 포함되며, 이는 보고서에서 날짜가 계산되고 표시되는 방식에 영향을 줍니다.

## 회계연도 처리를 위해 Aspose.Tasks를 사용하는 이유는?
- **No Microsoft Project required** – Java에서 직접 프로젝트 파일을 작업합니다.  
- **Full control** – 회계연도 시작을 설정하고 번호 매기기를 활성화하며 형식을 프로그래밍 방식으로 변환합니다.  
- **Robust API** – 대용량 MPP 파일을 안정적으로 처리하고 원활한 XML 내보내기를 지원합니다.  

## 전제 조건
시작하기 전에 다음이 설치되어 있는지 확인하십시오:
1. 시스템에 Java Development Kit (JDK) 설치.  
2. Aspose.Tasks for Java JAR – [here](https://releases.aspose.com/tasks/java/)에서 다운로드하고 프로젝트의 클래스패스에 추가합니다.

## 패키지 가져오기
시작하려면 Java 소스 파일에 필요한 클래스를 가져옵니다:
```java
import com.aspose.tasks.*;
```

## MPP 파일 로드 및 회계연도 정보 표시 방법
아래에서는 과정을 명확한 번호 단계로 나눕니다.

### 1단계: 프로젝트 파일 로드
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
여기서는 지정된 디렉터리에서 **load an MPP file** (`project.mpp`)을 로드합니다. 이는 회계연도와 관련된 모든 조작의 첫 번째 단계입니다.

### 2단계: 회계연도 속성 표시
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` 및 `Prj.FISCAL_YEAR_START` 속성을 사용하면 **display fiscal year** 세부 정보를 표시할 수 있어 “현재 회계구성은 무엇인가?”라는 질문에 답할 수 있습니다.

### 3단계: 회계연도 시작 설정 및 번호 매기기 활성화
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
이 단계에서는 **how to set fiscal** 설정을 수행합니다:
- `Month.JULY`는 회계연도 시작 월을 정의합니다.  
- `NullableBool(true)`는 회계연도 번호 매기기를 활성화합니다.  
- 마지막으로 `SaveFileFormat.Xml`을 사용하여 프로젝트를 **converted MPP to XML** 합니다.

### 4단계: 작업 확인
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
간단한 콘솔 메시지를 통해 회계연도가 구성되고 파일이 저장되었음을 확인할 수 있습니다.

## 왜 중요한가
프로젝트를 XML로 저장하면 휴대 가능하고 텍스트 기반의 표현을 얻을 수 있어 쉽게 파싱하고 버전 관리하거나 다른 시스템과 통합할 수 있습니다. 회계연도 설정이 올바르면 하위 재무 보고서와 대시보드가 조직의 회계 기간과 일치합니다.

## 일반적인 사용 사례
- **Financial reporting** – 프로젝트 일정을 회계 캘린더와 맞춘 후 BI 도구로 내보냅니다.  
- **Data migration** – 레거시 *.mpp* 파일을 XML로 변환하여 클라우드 기반 프로젝트 관리 플랫폼에 가져옵니다.  
- **Automated audits** – 모든 프로젝트가 올바른 회계 시작 월을 사용하는지 프로그래밍 방식으로 검증합니다.

## 문제 해결 팁 및 일반적인 함정
| 문제 | 해결책 |
|-------|----------|
| **Incorrect month value** | `Month` 열거형을 사용했는지 확인하십시오 (예: `Month.JANUARY`). |
| **File not found** | `dataDir`이 올바른 폴더를 가리키고 파일 이름이 일치하는지 확인하십시오. |
| **Saving fails** | 대상 디렉터리에 대한 쓰기 권한과 `SaveFileFormat`이 지원되는지 확인하십시오. |
| **Fiscal year not reflected in XML** | 저장 후 XML을 열어 `<FiscalYearStart>` 및 `<FiscalYearNumbering>` 노드에 예상 값이 포함되어 있는지 확인하십시오. |

## 자주 묻는 질문

**Q: Java용 Aspose.Tasks를 사용하여 다른 프로젝트 속성을 조작할 수 있나요?**  
A: 예, Aspose.Tasks는 회계연도 설정을 넘어 다양한 프로젝트 속성을 관리할 수 있는 포괄적인 기능을 제공합니다.

**Q: Java용 Aspose.Tasks는 다양한 프로젝트 파일 형식과 호환되나요?**  
A: 예, MPP, XML 등을 포함한 다양한 형식을 지원합니다.

**Q: Aspose.Tasks for Java 사용 중 문제가 발생하면 어떻게 지원을 받을 수 있나요?**  
A: [forum](https://forum.aspose.com/c/tasks/15)에서 Aspose.Tasks 커뮤니티에 도움을 요청하거나 직접 지원팀에 연락할 수 있습니다.

**Q: Aspose.Tasks에서 무료 체험 버전을 제공하나요?**  
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks 무료 체험 버전을 이용할 수 있습니다.

**Q: Java용 Aspose.Tasks 라이선스는 어디서 구매할 수 있나요?**  
A: [here](https://purchase.aspose.com/buy)에서 Java용 Aspose.Tasks 라이선스를 구매할 수 있습니다.

## 결론
Aspose.Tasks for Java에서 회계연도 속성을 관리하는 것은 간단합니다. 위 단계들을 따르면 **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year**, **convert mpp to xml**을 자신 있게 수행할 수 있습니다. 이러한 기술을 사용하여 프로젝트 일정이 조직의 재무 캘린더와 일치하도록 유지하고, 하위 처리용으로 휴대 가능한 XML 표현을 생성하십시오.

---

**마지막 업데이트:** 2026-04-01  
**테스트 대상:** Aspose.Tasks for Java 24.12 (작성 시 최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}