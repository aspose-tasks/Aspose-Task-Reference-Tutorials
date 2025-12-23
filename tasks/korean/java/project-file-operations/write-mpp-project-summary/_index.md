---
date: 2025-12-23
description: Aspose.Tasks for Java를 사용하여 MPP 요약을 만들고 프로젝트 저자를 업데이트하는 방법을 배워보세요. 프로젝트
  정보를 손쉽게 설정하고 검색하세요.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks로 MPP 요약 만들기 및 프로젝트 작성자 업데이트
url: /ko/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MPP 프로젝트 요약 작성

## 소개
이 튜토리얼에서는 Microsoft Project 파일에 대한 **MPP 요약** 정보를 **생성**하고 Aspose.Tasks for Java 라이브러리를 사용하여 **프로젝트 작성자** 세부 정보를 **업데이트**하는 방법을 배웁니다. 프로젝트 관리 도구를 구축하거나 보고서를 자동화할 때, 요약 속성을 프로그래밍 방식으로 제어하면 시간을 절약하고 프로젝트 전반에 걸쳐 일관성을 유지할 수 있습니다.

## 빠른 답변
- **“MPP 요약 생성”은 무엇을 의미하나요?** Microsoft Project의 프로젝트 요약 정보 대화 상자에 표시되는 고수준 프로젝트 속성(작성자, 개정, 키워드 등)을 설정하는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.Tasks for Java는 이러한 속성을 읽고 쓸 수 있는 유창한 API를 제공합니다.  
- **라이선스가 필요하나요?** 무료 체험판을 사용할 수 있지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **파일을 저장한 후에도 작성자를 변경할 수 있나요?** 예 – `project.set(Prj.AUTHOR, "New Author")` 를 호출한 뒤 파일을 다시 저장하면 **프로젝트 작성자**를 **업데이트**할 수 있습니다.  
- **지원되는 파일 형식은 무엇인가요?** MPP와 XML(SaveFileFormat.Xml) 모두 완전하게 지원됩니다.

## “MPP 요약 생성”이란?
MPP 요약을 생성한다는 것은 프로젝트의 메타데이터(작성자, 개정 번호, 키워드, 코멘트, 생성 날짜, 인쇄 날짜 등)를 채우는 것을 의미합니다. 이 메타데이터는 Project Summary Information 레코드에 저장되며 Microsoft Project의 **파일 → 정보** 섹션에 표시됩니다.

## 왜 프로젝트 작성자를 업데이트해야 할까요?
**프로젝트 작성자** 정보를 정확히 유지하는 것은 감사 추적, 협업 및 보고에 필수적입니다. 여러 팀원이 기여하는 경우 최신 변경 사항을 반영하거나 작업을 올바르게 귀속시키기 위해 **프로젝트 작성자**를 **업데이트**해야 할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음 요구 사항을 확인하세요:
1. 머신에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE가 필요합니다.

## 패키지 가져오기
먼저 Java 클래스에 필요한 패키지를 가져옵니다:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 1단계: 프로젝트 설정 및 요약 정보 정의
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
위 코드에서는 작성자, 개정, 키워드와 같은 **MPP 요약** 필드를 **생성**합니다. 이후 `project.set(Prj.AUTHOR, "New Name")` 를 호출하여 **프로젝트 작성자**를 **업데이트**할 수도 있습니다.

## 2단계: 프로젝트 요약 정보 저장
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
프로젝트를 저장하면 방금 정의한 모든 요약 데이터가 영구적으로 기록됩니다.

## 3단계: 프로젝트 요약 정보 읽기
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
이 스니펫은 **요약 정보를 다시 읽어** **MPP 요약 생성** 작업이 성공했는지 확인하는 방법을 보여줍니다.

## 일반적인 문제 및 해결 방법
- **읽은 후 값이 null인 경우:** 프로젝트가 성공적으로 저장되었는지 확인하고 다시 로드하세요. 파일 경로와 권한을 점검합니다.  
- **날짜 형식 차이:** `project.get(Prj.CREATION_DATE)` 는 `java.util.Date` 를 반환합니다. 사용자 정의 표시 형식이 필요하면 `SimpleDateFormat` 을 사용하세요.  
- **라이선스 미설정:** 유효한 라이선스가 없으면 Aspose.Tasks 가 평가 모드로 실행되어 워터마크가 삽입될 수 있습니다. 코드 초기에 라이선스를 등록하세요.

## 자주 묻는 질문
**Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다른 Java 라이브러리와 원활하게 통합되어 프로젝트 관리 기능을 확장할 수 있습니다.

**Q: Aspose.Tasks for Java의 체험판을 제공하나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java는 얼마나 자주 업데이트되나요?**  
A: 최신 Java 버전 및 Microsoft Project 파일과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.

**Q: 프로젝트 요약 정보를 더 세부적으로 커스터마이즈할 수 있나요?**  
A: 물론입니다. Aspose.Tasks for Java는 특정 요구 사항에 맞게 프로젝트 요약 정보를 광범위하게 커스터마이즈할 수 있는 옵션을 제공합니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼 [여기](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

## 결론
이 튜토리얼에서는 **MPP 요약** 데이터를 **생성**하고, **프로젝트 작성자**를 **업데이트**하며, Aspose.Tasks for Java를 사용해 이러한 변경 사항을 검증하는 방법을 살펴보았습니다. 이러한 단계를 자동화하면 프로젝트 메타데이터를 완벽히 제어할 수 있어 애플리케이션이 더욱 견고해지고 프로젝트 보고서가 보다 정확해집니다.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Tasks for Java 24.10  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}