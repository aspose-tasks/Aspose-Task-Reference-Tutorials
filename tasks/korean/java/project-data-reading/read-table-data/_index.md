---
title: Aspose.Tasks의 파일에서 테이블 데이터 읽기
linktitle: Aspose.Tasks의 파일에서 테이블 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks의 강력한 기능을 활용해 보세요. 이 포괄적인 튜토리얼을 통해 파일에서 테이블 데이터를 추출하는 방법을 알아보세요.
weight: 17
url: /ko/java/project-data-reading/read-table-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 파일에서 테이블 데이터 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 파일에서 테이블 데이터를 읽는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 문서를 프로그래밍 방식으로 작업할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 다운로드하여 설치할 수 있습니다.
2.  Aspose.Tasks for Java JAR 파일: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/) 그리고 이를 Java 프로젝트에 포함시킵니다.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks를 사용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## 1단계: 데이터 디렉터리 설정
프로젝트 파일이 있는 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 데이터 디렉터리의 실제 경로를 사용합니다.
## 2단계: 프로젝트 파일 로드
Aspose.Tasks를 사용하여 프로젝트 파일을 로드합니다.
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 꼭 교체하세요`"Project2003.mpp"` 프로젝트 파일 이름으로.
## 3단계: 테이블 정보 검색
프로젝트에서 테이블을 가져와 해당 필드를 반복합니다.
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
이 코드 조각은 너비, 제목, 정렬 등 테이블 필드에 대한 정보를 검색합니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 파일에서 테이블 데이터를 읽는 방법을 배웠습니다. 다음 단계를 수행하면 Java 애플리케이션의 Microsoft Project 문서에서 데이터를 효율적으로 추출하고 조작할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 Project 2003, 2007, 2010, 2013 및 2016을 포함하여 다양한 버전의 Microsoft Project를 지원합니다.
### Q: 테이블 데이터를 수정하고 프로젝트 파일에 다시 저장할 수 있나요?
A: 예, Aspose.Tasks를 사용하여 프로그래밍 방식으로 테이블 데이터를 수정하고 변경 사항을 원본 프로젝트 파일에 저장할 수 있습니다.
### Q: Aspose.Tasks를 상업적으로 사용하려면 별도의 라이선스가 필요합니까?
 A: 예, Aspose.Tasks를 상업용 환경에서 사용하려면 라이선스를 구매해야 합니다. 에서 라이센스를 취득하실 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, Aspose.Tasks의 무료 평가판 버전을 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 도움말과 지원은 어디서 찾을 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)커뮤니티와 Aspose 팀의 도움과 지원을 받으십시오.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
