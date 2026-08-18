---
date: 2026-02-18
description: Aspose.Tasks for Java를 사용하여 프로젝트를 PDF로 저장하고 Microsoft Project 데이터베이스를
  읽는 방법을 배우고, Project Server에 연결하고, 프로젝트를 HTML로 변환하며, 프로젝트를 XML로 내보내는 방법을 알아보세요.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트를 PDF로 저장하고 Java용 Aspose.Tasks로 프로젝트 DB 읽기
url: /ko/java/project-data-reading/read-project-database/
weight: 12
---

 final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 PDF로 저장하고 Aspose.Tasks for Java로 Microsoft Project 데이터베이스 읽기

## 소개
이 튜토리얼에서는 **Microsoft Project Server**에서 **Microsoft Project 데이터베이스**를 직접 읽고, Aspose.Tasks Java API를 사용해 **프로젝트를 PDF로 저장**하는 방법을 알아봅니다. 보고서를 생성하거나, 데이터를 마이그레이션하거나, 프로젝트 정보를 자체 애플리케이션에 통합해야 할 때, 데이터베이스 연결 설정부터 프로젝트를 PDF, XML, HTML 등으로 내보내는 전체 과정을 단계별로 안내합니다. 최종적으로 Microsoft Project를 호스트 머신에 설치하지 않아도 동작하는 실무 수준의 솔루션을 갖추게 됩니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 하나요?** Microsoft Project 파일 및 데이터베이스를 읽고, 쓰고, 조작할 수 있는 순수 Java API를 제공합니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 동작합니다.  
- **지원되는 데이터베이스 유형은?** Microsoft SQL Server (Project Server의 백엔드).  
- **다른 형식으로 내보낼 수 있나요?** 네, PDF 외에도 XML, HTML, CSV 등 다양한 형식으로 저장할 수 있습니다.  
- **주요 사전 요구 사항은?** JDK, Aspose.Tasks for Java 라이브러리, SQL Server JDBC 드라이버, 그리고 **Project Server에 연결**할 수 있는 인증 정보.

## “Microsoft Project 데이터베이스 읽기”란?
Microsoft Project 데이터베이스를 읽는다는 것은 Project Server의 SQL Server 저장소에 연결해 저장된 프로젝트 데이터를 추출하고, 이를 Aspose.Tasks가 조작할 수 있는 `Project` 객체로 로드하는 것을 의미합니다. 자동 보고서 작성, 데이터 마이그레이션, 맞춤형 분석 등에 이상적인 접근 방식입니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
- **Microsoft Project 의존성 없음** – 모든 서버 또는 CI 환경에서 실행 가능.  
- **풍부한 객체 모델** – 작업, 리소스, 할당, 캘린더, 사용자 정의 필드 등을 프로그래밍 방식으로 접근.  
- **다중 내보내기 옵션** – 단일 API 호출로 PDF, XML, HTML, PNG 등 다양한 형식 지원.  
- **고성능** – 대규모 엔터프라이즈 프로젝트에 최적화.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

1. Java 개발 환경 (JDK 8 이상).  
2. 프로젝트 클래스패스에 추가된 Aspose.Tasks for Java 라이브러리.  
3. Project Server SQL 데이터베이스에 접근할 수 있는 인증 정보(서버 이름, 포트, 데이터베이스 이름, 사용자명, 비밀번호) **Project Server에 연결**하기 위한 정보.  
4. Microsoft JDBC Driver for SQL Server (예: `sqljdbc4.jar`).  

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
신뢰할 수 있는 연결을 설정하는 것이 프로젝트 데이터를 읽는 기반이 됩니다. SQL Server 인스턴스가 Java 호스트에서 접근 가능하고, 사용 중인 로그인에 Project Server 스키마에 대한 **SELECT** 권한이 있는지 확인하세요.

## 단계 1: 데이터베이스 연결 설정
JDBC 연결 문자열을 보관하는 `MspDbSettings` 인스턴스를 생성합니다. 자리표시자 값을 실제 서버 정보로 교체하세요.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** 연결 문자열을 하드코딩하지 말고, 보안 설정 파일이나 환경 변수에 저장하세요.

## 단계 2: JDBC 드라이버 추가
런타임에 Microsoft SQL Server JDBC 드라이버를 로드하여 JVM이 데이터베이스와 통신할 수 있게 합니다.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** 드라이버 버전이 사용 중인 SQL Server 버전과 일치하는지 확인하세요. 호환되지 않는 드라이버는 연결 실패를 일으킬 수 있습니다.

## 단계 3: 프로젝트 데이터 읽기
`MspDbSettings`를 전달해 `Project` 객체를 인스턴스화합니다. Aspose.Tasks가 자동으로 데이터베이스에서 프로젝트 데이터를 가져옵니다.

```java
Project project = new Project(settings);
```

이제 `project` 객체를 탐색하면서 작업, 리소스 목록을 확인하거나 필요한 필드를 수정할 수 있습니다.

## 단계 4: 프로젝트를 PDF로 저장
로드한 프로젝트를 원하는 형식으로 내보냅니다. 아래 예시는 **PDF**로 저장하는 방법을 보여주며, 인쇄 가능한 보고서에 적합합니다. `SaveFileFormat` 열거형을 변경하면 **XML**이나 **HTML** 등으로도 내보낼 수 있습니다.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

XML로 저장하려면 `SaveFileFormat.Pdf`를 `SaveFileFormat.Xml`로 바꾸면 됩니다. HTML 출력은 `SaveFileFormat.Html`을 사용하세요.

## 일반적인 문제 및 해결책
| 문제 | 일반적인 원인 | 해결 방법 |
|------|--------------|----------|
| **연결 시간 초과** | 서버/포트 오류 또는 방화벽 차단 | 서버 주소 확인, 포트 1433 열기, 간단한 JDBC 테스트 프로그램으로 연결 테스트 |
| **인증 오류** | 사용자명/비밀번호 오류 또는 SQL Server가 SQL 인증을 사용하지 않음 | 올바른 SQL 로그인 사용 또는 서버에서 혼합 모드 인증 활성화 |
| **드라이버를 찾을 수 없음** | JDBC jar가 클래스패스에 없음 | `addJDBCDriver`가 올바른 `.jar` 파일을 가리키는지, 경로에 이중 역슬래시(`\\`) 사용 여부 확인 |
| **로드 후 프로젝트가 비어 있음** | Project Server 테이블에 대한 권한 부족 | 로그인에 Project Server 데이터베이스 스키마에 대한 SELECT 권한 부여 |

## 자주 묻는 질문

**Q: Aspose.Tasks를 사용해 Microsoft Project 외의 다른 데이터베이스에서 프로젝트 데이터를 읽을 수 있나요?**  
A: 네, Aspose.Tasks는 XML 파일, Primavera, Microsoft Project 데이터베이스 등 다양한 소스에서 프로젝트 데이터를 읽을 수 있습니다.

**Q: Aspose.Tasks는 다양한 버전의 Microsoft Project와 호환되나요?**  
A: 네, Aspose.Tasks는 여러 Microsoft Project 버전을 지원하도록 설계되어 원활한 통합을 보장합니다.

**Q: 저장하기 전에 프로젝트 데이터를 조작할 수 있나요?**  
A: 물론입니다. Aspose.Tasks는 작업 추가, 리소스 업데이트, 프로젝트 속성 설정 등 풍부한 API를 제공하여 내보내기 전에 자유롭게 수정할 수 있습니다.

**Q: Aspose.Tasks가 지원하는 출력 형식이 여러 개인가요?**  
A: 네, PDF, XML, HTML, CSV, PNG, JPEG 등 다양한 형식으로 프로젝트를 저장할 수 있습니다.

**Q: Aspose.Tasks에 대한 추가 지원이나 도움이 필요하면 어디서 찾을 수 있나요?**  
A: 추가 도움이 필요하면 Aspose.Tasks 포럼을 방문하거나 웹사이트의 문서를 확인하세요. [여기](https://forum.aspose.com/c/tasks/15)에서 확인할 수 있습니다.

## 결론
이 단계별 가이드를 따라 **Microsoft Project 데이터베이스를 읽고**, **프로젝트를 PDF로 저장**하며, Aspose.Tasks for Java를 활용해 다른 형식으로도 내보내는 방법을 익혔습니다. 이 접근 방식은 Microsoft Project에 대한 의존성을 없애고 자동화된 보고서를 간소화하며, 강력한 맞춤형 통합의 문을 열어줍니다.

---

**마지막 업데이트:** 2026-02-18  
**테스트 환경:** Aspose.Tasks for Java 24.5 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}