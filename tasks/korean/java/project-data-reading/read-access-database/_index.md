---
title: Aspose.Tasks의 MS Access 데이터베이스에서 프로젝트 데이터 읽기
linktitle: Aspose.Tasks를 사용하여 Microsoft Access 데이터베이스에서 프로젝트 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Access 데이터베이스에서 MS Project 데이터를 읽는 방법을 알아보세요. 원활한 통합을 위해 단계별 튜토리얼을 따르세요.
weight: 11
url: /ko/java/project-data-reading/read-access-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 MS Access 데이터베이스에서 프로젝트 데이터 읽기

## 소개
Aspose.Tasks for Java는 개발자가 Java 애플리케이션에서 Microsoft Project 파일을 원활하게 사용할 수 있게 해주는 강력한 API입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 Microsoft Access 데이터베이스에서 MS Project 데이터를 읽는 데 중점을 둘 것입니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
### JDK(Java 개발 키트)가 설치되었습니다.
시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 버전을 다운로드하여 설치할 수 있습니다.
### Java 라이브러리용 Aspose.Tasks
 프로젝트에 Aspose.Tasks for Java 라이브러리를 다운로드하고 포함하세요. Aspose 홈페이지에서 받으실 수 있습니다. 따라가다[다운로드 링크](https://releases.aspose.com/tasks/java/) 도서관을 얻으려면.

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 필요한 패키지를 Java 프로젝트로 가져와야 합니다.
```java
import com.aspose.tasks.MpdSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 데이터 디렉터리 정의
프로젝트 XML 파일을 저장하려는 디렉터리의 경로를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: MpdSettings 정의
Microsoft Access 데이터베이스에 대한 연결 문자열과 프로젝트 식별자를 사용하여 MpdSettings 개체를 초기화합니다.
```java
MpdSettings settings = new MpdSettings(getConnectionString(), 1);
```
## 3단계: 데이터베이스에서 프로젝트 로드
MpdSettings 인스턴스를 전달하여 새 Project 개체를 만듭니다.
```java
Project project = new Project(settings);
```
## 4단계: 프로젝트 데이터 저장
프로젝트 데이터를 XML 파일에 저장합니다.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Access 데이터베이스에서 MS Project 데이터를 읽는 방법을 배웠습니다. 제공된 단계를 따르면 이 기능을 Java 애플리케이션에 효율적으로 통합할 수 있습니다.
## FAQ
### Q: Microsoft Access 이외의 다른 데이터베이스 시스템에서 Aspose.Tasks for Java를 사용할 수 있습니까?
A: 예, Aspose.Tasks는 SQL Server, MySQL, Oracle과 같은 다양한 데이터베이스 시스템을 지원합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java에 대한 기술 지원은 어떻게 받을 수 있나요?
 A: 기술 지원은 다음으로부터 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks for Java를 사용하려면 임시 라이선스가 필요합니까?
 A: 일부 고급 기능을 사용하려면 임시 라이선스가 필요할 수 있습니다. 그것을 얻으십시오[여기](https://purchase.aspose.com/temporary-license/).
### Q: Java용 Aspose.Tasks는 어디에서 구매할 수 있나요?
 A: Java용 Aspose.Tasks를 구입할 수 있습니다.[이 링크](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
