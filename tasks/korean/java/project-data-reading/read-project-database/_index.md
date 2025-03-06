---
title: Aspose.Tasks의 MS 프로젝트 데이터베이스에서 프로젝트 데이터 읽기
linktitle: Aspose.Tasks의 Microsoft Project 데이터베이스에서 프로젝트 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project Database에서 프로젝트 데이터를 읽는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
weight: 12
url: /ko/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 MS 프로젝트 데이터베이스에서 프로젝트 데이터 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project Database에서 프로젝트 데이터를 읽는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치할 필요 없이 Microsoft Project 문서를 조작할 수 있는 강력한 Java API입니다. 이 가이드에 설명된 단계를 수행하면 데이터베이스에서 프로젝트 데이터를 효율적으로 추출하고 원하는 형식으로 저장하는 방법을 배울 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 프로그래밍에 대한 기본 지식.
2. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
3. 프로젝트에 다운로드 및 구성된 Java 라이브러리용 Aspose.Tasks입니다.

## 패키지 가져오기
시작하려면 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## 1단계: 데이터베이스 연결 설정
먼저 Microsoft Project 데이터베이스에 대한 연결을 설정해야 합니다. 여기에는 데이터베이스 URL, 서버 이름, 포트 번호, 데이터베이스 이름, 사용자 이름 및 비밀번호 지정이 포함됩니다.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## 2단계: JDBC 드라이버 추가
다음으로 프로젝트에 JDBC 드라이버를 추가해야 합니다. 이 드라이버는 Java 애플리케이션과 Microsoft SQL Server 데이터베이스 간의 통신을 용이하게 합니다.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## 3단계: 프로젝트 데이터 읽기
 이제`Project` 이전에 정의한 설정을 사용하여 데이터베이스에서 개체를 만들고 프로젝트 데이터를 로드합니다.
```java
Project project = new Project(settings);
```
## 4단계: 프로젝트 데이터 저장
마지막으로 프로젝트 데이터를 원하는 형식으로 저장합니다. 이 예에서는 이를 XML 파일로 저장합니다.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
축하해요! Aspose.Tasks for Java를 사용하여 Microsoft Project 데이터베이스에서 프로젝트 데이터를 성공적으로 읽었습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project Database에서 프로젝트 데이터를 읽는 프로세스를 다루었습니다. 설명된 단계를 따르면 프로젝트 정보를 원활하게 추출하고 요구 사항에 따라 조작할 수 있습니다. Aspose.Tasks는 Microsoft Project 문서 처리를 단순화하여 효율적인 데이터 추출 및 조작을 가능하게 합니다.
## FAQ
### Q: Aspose.Tasks를 사용하여 Microsoft Project 이외의 다른 데이터베이스에서 프로젝트 데이터를 읽을 수 있습니까?
A: 예, Aspose.Tasks는 XML 파일, Primavera 및 Microsoft Project 데이터베이스를 포함한 다양한 소스에서 프로젝트 데이터 읽기를 지원합니다.
### Q: Aspose.Tasks는 다른 버전의 Microsoft Project와 호환됩니까?
A: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project와 작동하도록 설계되어 호환성과 원활한 통합을 보장합니다.
### Q: 프로젝트 데이터를 저장하기 전에 조작할 수 있나요?
A: 물론 Aspose.Tasks는 작업 추가, 리소스 업데이트, 프로젝트 속성 설정 등 프로젝트 데이터를 조작하기 위한 다양한 기능을 제공합니다.
### Q: Aspose.Tasks는 여러 출력 형식을 지원합니까?
A: 예, Aspose.Tasks는 XML, PDF, HTML 및 PNG 및 JPEG와 같은 이미지 형식을 포함한 다양한 출력 형식을 지원합니다.
### Q: Aspose.Tasks에 대한 추가 지원은 어디에서 찾을 수 있나요?
 A: 추가 지원이 필요하면 Aspose.Tasks 포럼을 방문하거나 웹사이트에서 제공되는 문서를 탐색하세요.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
