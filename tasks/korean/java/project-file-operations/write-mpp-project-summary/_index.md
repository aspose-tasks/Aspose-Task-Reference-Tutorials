---
title: Aspose.Tasks에 MPP 프로젝트 요약 작성
linktitle: Aspose.Tasks에 MPP 프로젝트 요약 작성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java로 MPP 프로젝트 요약을 작성하는 방법을 알아보세요. 프로젝트 정보를 쉽게 설정하고 검색할 수 있습니다.
weight: 27
url: /ko/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 MPP 프로젝트 요약 작성

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 활용하여 MPP 프로젝트 요약을 작성하는 방법을 알아봅니다. Aspose.Tasks는 Microsoft Project 파일 작업을 위한 강력한 Java 라이브러리입니다. 아래 설명된 단계를 따르면 이 라이브러리를 사용하여 프로젝트에 대한 다양한 요약 정보를 설정하고 검색할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. IDE(통합 개발 환경): IntelliJ IDEA, Eclipse, NetBeans 등 Java 개발을 위해 선호하는 IDE를 선택하세요.

## 패키지 가져오기
먼저 필요한 패키지를 Java 클래스로 가져옵니다.
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## 1단계: 프로젝트 설정 및 요약 정보 정의
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
//프로젝트 파일의 경로를 사용하여 새 프로젝트 개체를 초기화합니다.
Project project = new Project(dataDir + "project.mpp");
// 프로젝트에 대한 요약 정보 설정
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// 프로젝트 생성 날짜 설정
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// 프로젝트에 대한 키워드 설정
project.set(Prj.KEYWORDS, "MPP Aspose");
// 프로젝트의 마지막 인쇄 날짜 설정
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## 2단계: 프로젝트 요약 정보 저장
```java
// 프로젝트를 MPP 형식으로 다시 저장
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// 성공 메시지 표시
System.out.println("Process completed Successfully");
```
## 3단계: 프로젝트 요약 정보 읽기
```java
// 프로젝트 요약 정보 읽기
project = new Project(dataDir + "MppAspose.xml");
// 프로젝트의 인쇄 작성자
System.out.println("Author: " + project.get(Prj.AUTHOR));
// 프로젝트의 마지막 작성자 인쇄
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// 프로젝트 개정 번호 인쇄
System.out.println("Revision: " + project.get(Prj.REVISION));
// 프로젝트의 키워드 인쇄
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// 프로젝트 코멘트 인쇄
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// 프로젝트 생성 날짜 인쇄
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// 프로젝트의 키워드 인쇄 (다시)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// 프로젝트의 마지막 인쇄 날짜를 인쇄합니다.
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 프로젝트 요약을 작성하는 방법을 다루었습니다. 다음 단계를 수행하면 프로젝트 파일에 대한 다양한 요약 정보를 효율적으로 설정하고 검색할 수 있습니다. Aspose.Tasks는 Java 애플리케이션에서 Microsoft Project 파일 작업 프로세스를 단순화하여 강력한 기능과 사용 편의성을 제공합니다.
## FAQ
### Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 다른 Java 라이브러리와 원활하게 통합되어 프로젝트 관리 기능을 향상시킬 수 있습니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 평가판이 있습니까?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java는 얼마나 자주 업데이트되나요?
A: Aspose.Tasks for Java는 최신 버전의 Java 및 Microsoft Project 파일과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### Q: 프로젝트 요약 정보를 추가로 사용자 정의할 수 있나요?
A: 물론, Aspose.Tasks for Java는 특정 요구 사항에 따라 프로젝트 요약 정보를 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
