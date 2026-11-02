---
date: 2026-10-31
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하고 Microsoft Project 데이터베이스를
  읽는 방법을 배우고, Project Server에 연결하고, 프로젝트를 HTML로 변환하고, XML로 내보내는 방법도 알아보세요.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Aspose.Tasks에서 Microsoft Project 데이터베이스의 프로젝트 데이터 읽기
og_description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하고 Microsoft Project 데이터베이스를
  읽습니다. Project Server에 연결하고, HTML, XML, CSV로 내보내는 방법을 배워보세요.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Aspose.Tasks for Java로 프로젝트를 PDF로 저장하고 Microsoft Project 데이터베이스 읽기
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Aspose.Tasks for Java로 프로젝트를 PDF로 저장하고 Microsoft Project 데이터베이스 읽기
url: /ko/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 PDF로 저장하고 Aspose.Tasks for Java로 Microsoft Project 데이터베이스 읽기

## 소개
이 튜토리얼에서는 **Microsoft Project Server**에서 직접 **Microsoft Project 데이터베이스를 읽고** Aspose.Tasks Java API를 사용하여 **프로젝트를 PDF로 저장**하는 방법을 알아봅니다. 인쇄 가능한 보고서를 생성하거나, 레거시 데이터를 마이그레이션하거나, 프로젝트 정보를 맞춤 포털에 삽입해야 할 때, 이 가이드는 JDBC 연결 구성부터 프로젝트를 PDF, XML, HTML 등으로 내보내는 단계까지 모두 안내합니다. 최종적으로 Microsoft Project를 설치하지 않아도 모든 Java 서버에서 실행 가능한 프로덕션 수준 솔루션을 얻게 됩니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 하나요?** Microsoft Project 파일 및 데이터베이스를 읽고, 쓰고, 조작하기 위한 순수 Java API를 제공합니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 작동합니다.  
- **지원되는 데이터베이스 유형은?** Microsoft SQL Server, Project Server의 백엔드입니다.  
- **다른 형식으로 내보낼 수 있나요?** 예—PDF, XML, HTML, CSV, PNG, JPEG 등 다양한 형식으로 내보낼 수 있습니다.  
- **주요 전제 조건은?** JDK 8 이상, Aspose.Tasks for Java 라이브러리, SQL Server JDBC 드라이버, 그리고 유효한 Project Server 자격 증명.

## “Microsoft Project 데이터베이스 읽기”란 무엇인가요?
Microsoft Project 데이터베이스를 읽는다는 것은 Project Server의 SQL Server 저장소에 연결하여 저장된 프로젝트 데이터를 추출하고, 이를 Aspose.Tasks가 조작할 수 있는 `Project` 객체로 로드하는 것을 의미합니다. 자동화된 보고, 데이터 마이그레이션, 맞춤형 분석에 이상적인 접근 방식입니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
Aspose.Tasks for Java는 데스크톱 애플리케이션 없이 Microsoft Project 데이터를 다룰 수 있게 해 주는 순수 Java 솔루션으로, 모든 플랫폼에서 실행됩니다. 작업, 리소스, 캘린더, 사용자 정의 필드에 대한 포괄적인 객체 모델을 제공하며, 대규모 엔터프라이즈 프로젝트도 효율적으로 처리할 수 있어 자동화된 보고, 마이그레이션, 통합 시나리오에 최적입니다.

- **Microsoft Project 의존성 없음** – 모든 서버 또는 CI 환경에서 실행 가능.  
- **풍부한 객체 모델** – 작업, 리소스, 할당, 캘린더, 사용자 정의 필드에 프로그래밍 방식으로 접근.  
- **다양한 내보내기 옵션** – Aspose.Tasks는 **20개 이상의 파일 형식**(PDF, XML, HTML, CSV, PNG, JPEG 등)으로 내보내기를 지원하며, 단일 API 호출로 처리 가능.  
- **고성능** – 라이브러리는 **10,000개 이상의 작업**을 1분 이내에 처리할 수 있으며, 전체 파일을 메모리에 로드하지 않도록 스트리밍 방식으로 데이터를 처리합니다.

## 전제 조건
시작하기 전에 다음을 확인하세요:

1. Java 개발 환경(JDK 8 이상) 구축.  
2. 프로젝트 클래스패스에 Aspose.Tasks for Java 라이브러리 추가.  
3. Project Server SQL 데이터베이스에 접근할 수 있는 자격 증명(서버 이름, 포트, 데이터베이스 이름, 사용자명, 비밀번호).  
4. Microsoft JDBC Driver for SQL Server(`sqljdbc4.jar` 등) 확보.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 아래 목록에는 Aspose.Tasks 핵심 클래스와 표준 Java 유틸리티가 포함됩니다.

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

## Project Server에 연결하는 방법
신뢰할 수 있는 연결을 구축하는 것이 프로젝트 데이터를 읽는 기반이 됩니다. SQL Server 인스턴스가 Java 호스트에서 접근 가능해야 하며, 사용 중인 로그인에 Project Server 스키마에 대한 **SELECT** 권한이 있어야 합니다. 네트워크 지연 시간을 확인하고, 필요한 경우 SSL 설정을 구성하여 보안 통신을 보장하세요.

## 1단계: 데이터베이스 연결 설정
`MspDbSettings` 클래스는 Microsoft Project Server 데이터베이스에 접근하기 위한 JDBC 연결 세부 정보를 캡슐화합니다. JDBC 연결 문자열을 보유하는 `MspDbSettings` 인스턴스를 생성하고, 자리표시자 값을 실제 서버 정보로 교체합니다.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** 자격 증명을 하드코딩하는 대신 보안 구성 파일이나 환경 변수에 연결 문자열을 저장하세요.

## 2단계: JDBC 드라이버 추가
런타임에 Microsoft SQL Server JDBC 드라이버를 로드하여 JVM이 데이터베이스와 통신할 수 있도록 합니다.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** 드라이버 버전이 SQL Server 버전과 일치하는지 확인하세요. 호환되지 않는 드라이버는 연결 실패를 일으킬 수 있습니다.

## 3단계: 프로젝트 데이터 읽기
`Project` 클래스는 메모리로 로드된 Microsoft Project 파일을 나타내며 작업, 리소스, 할당 정보를 노출합니다. `MspDbSettings`를 전달하여 `Project` 객체를 인스턴스화하면 Aspose.Tasks가 자동으로 데이터베이스에서 프로젝트 데이터를 가져옵니다.

```java
Project project = new Project(settings);
```

이 시점에서 `project` 객체를 탐색하여 작업, 리소스를 나열하거나 필요에 따라 필드를 수정할 수 있습니다.

## 4단계: 프로젝트를 PDF로 저장
`SaveFileFormat` 열거형은 `Project.save` 메서드의 출력 형식을 정의합니다(PDF, XML, HTML 등). 아래 예제는 프로젝트를 **PDF**로 저장하는 방법을 보여주며, 인쇄 가능한 보고서에 적합합니다. `SaveFileFormat` 열거형을 변경하면 **XML**이나 **HTML**로도 내보낼 수 있습니다.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

XML로 저장하려면 `SaveFileFormat.Pdf`를 `SaveFileFormat.Xml`로 교체하면 됩니다. HTML 출력은 `SaveFileFormat.Html`을 사용하세요.

## 일반적인 문제 및 해결책
| 문제 | 일반적인 원인 | 해결 방법 |
|-------|---------------|-----|
| **연결 시간 초과** | 잘못된 서버/포트 또는 방화벽 차단 | 서버 주소를 확인하고 포트 1433을 열며, 간단한 JDBC 테스트 프로그램으로 연결을 테스트합니다. |
| **인증 오류** | 잘못된 사용자명/비밀번호 또는 SQL Server가 SQL 인증으로 설정되지 않음 | 올바른 SQL 로그인 사용 또는 서버에서 혼합 모드 인증을 활성화합니다. |
| **드라이버를 찾을 수 없음** | JDBC JAR가 클래스패스에 없음 | `addJDBCDriver`가 올바른 `.jar` 파일을 가리키는지, 경로에 이중 역슬래시(`\\`)를 사용했는지 확인합니다. |
| **로드 후 프로젝트가 비어 있음** | Project Server 테이블에 대한 권한 부족 | 로그인에 Project Server 데이터베이스 스키마에 대한 SELECT 권한을 부여합니다. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 Microsoft Project 외의 다른 데이터베이스에서 프로젝트 데이터를 읽을 수 있나요?**  
A: 예, Aspose.Tasks는 XML 파일, Primavera 데이터베이스 및 기타 표준 프로젝트 형식에서도 데이터를 읽을 수 있습니다.

**Q: Aspose.Tasks는 다양한 버전의 Microsoft Project와 호환되나요?**  
A: 예, 라이브러리는 Microsoft Project 2007부터 최신 2024 릴리스까지 지원하여 버전 간 원활한 통합을 보장합니다.

**Q: 저장하기 전에 프로젝트 데이터를 조작할 수 있나요?**  
A: 물론입니다. 풍부한 API를 사용해 작업, 리소스, 사용자 정의 필드를 추가, 업데이트, 삭제한 뒤 내보낼 수 있습니다.

**Q: Aspose.Tasks는 여러 출력 형식을 지원하나요?**  
A: 예, PDF, XML, HTML, CSV, PNG, JPEG 등 20개 이상의 형식으로 프로젝트를 저장할 수 있습니다.

**Q: Aspose.Tasks에 대한 추가 지원이나 도움을 어디서 받을 수 있나요?**  
A: 추가 도움이 필요하면 Aspose.Tasks 포럼을 방문하거나 웹사이트에 있는 문서를 확인하세요. [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)

## 결론
이 단계별 가이드를 따라 **Microsoft Project 데이터베이스를 읽고**, **프로젝트를 PDF로 저장**하며, Aspose.Tasks for Java를 사용해 다른 형식으로도 내보내는 방법을 익혔습니다. 이 접근 방식은 Microsoft Project에 대한 의존성을 없애고 자동화된 보고를 간소화하며 강력한 맞춤형 통합을 가능하게 합니다.

---

**마지막 업데이트:** 2026-10-31  
**테스트 환경:** Aspose.Tasks for Java 24.5 (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks로 프로젝트를 PDF로 저장 – 내보내기 가이드](/tasks/java/project-file-operations/save-as-pdf/)
- [Aspose.Tasks for Java로 작업 시트 렌더링 – 프로젝트를 PDF로 저장](/tasks/java/task-properties/render-task-sheet/)
- [Aspose.Tasks에서 프로젝트를 PDF로 내보내고 작업 목록과 바닥글 사이 간격 줄이기](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}