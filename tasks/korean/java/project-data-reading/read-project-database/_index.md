---
date: 2025-12-13
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 데이터베이스를 읽는 방법을 배웁니다. 코드
  예제와 모범 사례가 포함된 단계별 가이드.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java로 Microsoft Project 데이터베이스 읽기
url: /ko/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 Microsoft Project 데이터베이스 읽기

## 소개
이 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 Microsoft Project Server에서 **Microsoft Project 데이터베이스를 직접 읽는 방법**을 알아봅니다. 보고서를 생성하거나, 데이터를 마이그레이션하거나, 프로젝트 정보를 자체 애플리케이션에 통합해야 할 경우, 이 가이드는 데이터베이스 연결 설정부터 프로젝트를 XML로 내보내는 단계까지 모든 과정을 안내합니다. 마지막까지 진행하면 호스트 머신에 Microsoft Project를 설치하지 않아도 작동하는 견고하고 프로덕션 준비된 솔루션을 얻게 됩니다.

## 빠른 답변
- **Aspose.Tasks는 무엇을 하나요?** 순수 Java API를 제공하여 Microsoft Project 파일 및 데이터베이스를 읽고, 쓰고, 조작할 수 있습니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 Microsoft Project와 독립적으로 작동합니다.  
- **지원되는 데이터베이스 유형은 무엇인가요?** Microsoft SQL Server (Project Server의 백엔드).  
- **다른 형식으로 내보낼 수 있나요?** 예, XML 외에도 PDF, HTML, CSV 등으로 저장할 수 있습니다.  
- **주요 사전 요구 사항은 무엇인가요?** JDK, Aspose.Tasks for Java 라이브러리, 그리고 SQL Server JDBC 드라이버.

## “Microsoft Project 데이터베이스 읽기”란 무엇인가요?
Microsoft Project 데이터베이스를 읽는다는 것은 Project Server의 SQL Server 저장소에 연결하여 저장된 프로젝트 데이터를 추출하고, Aspose.Tasks가 조작할 수 있는 `Project` 객체에 로드하는 것을 의미합니다. 이 방법은 자동 보고, 데이터 마이그레이션, 맞춤형 분석에 이상적입니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
- **Microsoft Project 의존성 없음** – 모든 서버나 CI 환경에서 실행할 수 있습니다.  
- **풍부한 객체 모델** – 작업, 리소스, 할당, 캘린더 및 사용자 정의 필드에 프로그래밍 방식으로 접근할 수 있습니다.  
- **다중 내보내기 옵션** – 단일 API 호출로 XML, PDF, HTML, PNG 등으로 내보낼 수 있습니다.  
- **고성능** – 대규모 엔터프라이즈 프로젝트에 최적화되었습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오. 정상적인 Java 개발 환경 (JDK 8 이상).  
2. 프로젝트 클래스패스에 Aspose.Tasks for Java 라이브러리를 추가했습니다.  
3. Project Server SQL 데이터베이스에 대한 접근 자격 증명(서버 이름, 포트, 데이터베이스 이름, 사용자명, 비밀번호).  
4. Microsoft JDBC Driver for SQL Server (예: `sqljdbc4.jar`).

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 목록에는 Aspose.Tasks 핵심 클래스와 표준 Java 유틸리티가 포함됩니다.

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

## 단계 1: 데이터베이스 연결 설정
`MspDbSettings` 인스턴스를 생성하여 JDBC 연결 문자열을 보관합니다. 자리표시자 값을 실제 서버 세부 정보로 교체하십시오.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **전문가 팁:** 연결 문자열을 하드코딩하는 대신 보안 구성 파일이나 환경 변수에 저장하십시오.

## 단계 2: JDBC 드라이버 추가
런타임에 Microsoft SQL Server JDBC 드라이버를 로드하여 JVM이 데이터베이스와 통신할 수 있도록 합니다.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **경고:** 드라이버 버전이 SQL Server 버전과 일치하는지 확인하십시오. 호환되지 않는 드라이버를 사용하면 연결 실패가 발생할 수 있습니다.

## 단계 3: 프로젝트 데이터 읽기
`MspDbSettings`를 전달하여 `Project` 객체를 인스턴스화합니다. Aspose.Tasks가 데이터베이스에서 프로젝트 데이터를 자동으로 가져옵니다.

```java
Project project = new Project(settings);
```

이 시점에서 `project` 객체를 탐색할 수 있습니다—작업, 리소스를 나열하거나 필요에 따라 필드를 수정하십시오.

## 단계 4: 프로젝트 데이터 저장
로드된 프로젝트를 원하는 파일 형식으로 내보냅니다. 아래 예제는 프로젝트를 XML로 저장하며, 이후 Microsoft Project에 가져오거나 추가로 처리할 수 있습니다.

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

보고서 요구 사항에 따라 `SaveFileFormat.Xml`을 `Pdf`, `Html`, `Csv` 등으로 교체할 수 있습니다.

## 일반적인 문제 및 해결책

| Issue | Typical Cause | Fix |
|-------|---------------|-----|
| **연결 시간 초과** | 잘못된 서버/포트 또는 방화벽 차단 | 서버 주소를 확인하고 포트 1433을 열며, 간단한 JDBC 테스트 프로그램으로 연결을 테스트하십시오. |
| **인증 오류** | 잘못된 사용자명/비밀번호 또는 SQL Server가 SQL 인증으로 설정되지 않음 | 유효한 SQL 로그인 사용하거나 서버에서 혼합 모드 인증을 활성화하십시오. |
| **드라이버를 찾을 수 없음** | JDBC jar가 클래스패스에 없음 | `addJDBCDriver`가 올바른 `.jar` 파일을 가리키고 경로에 이중 백슬래시(`\\`)를 사용하고 있는지 확인하십시오. |
| **로드 후 프로젝트가 비어 있음** | Project Server 테이블을 읽을 권한 부족 | 로그인에 Project Server 데이터베이스 스키마에 대한 SELECT 권 부여하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks를 Microsoft Project 외의 다른 데이터베이스에서 프로젝트 데이터를 읽는 데 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 XML 파일, Primavera, Microsoft Project 데이터베이스 등 다양한 소스에서 프로젝트 데이터를 읽는 것을 지원합니다.

**Q: Aspose.Tasks가 다양한 버전의 Microsoft Project와 호환되나요?**  
A: 예, Aspose.Tasks는 여러 Microsoft Project 버전과 작동하도록 설계되어 원활한 통합을 보장합니다.

**Q: 저장하기 전에 프로젝트 데이터를 조작할 수 있나요?**  
A: 물론입니다. Aspose.Tasks는 내보내기 전에 작업을 추가하고, 리소스를 업데이트하며, 프로젝트 속성을 설정할 수 있는 풍부한 API를 제공합니다.

**Q: Aspose.Tasks가 다중 출력 형식을 지원하나요?**  
A: 예, 프로젝트를 XML, PDF, HTML, CSV, PNG, JPEG 등으로 저장할 수 있습니다.

**Q: Aspose.Tasks에 대한 추가 지원이나 도움을 어디서 찾을 수 있나요?**  
A: 추가 도움이 필요하면 Aspose.Tasks 포럼을 방문하거나 웹사이트에 있는 문서를 확인하십시오. [여기](https://forum.aspose.com/c/tasks/15)

## 결론
이 단계별 가이드를 따라 하면 Aspose.Tasks for Java를 사용하여 **Microsoft Project 데이터베이스를 읽는** 방법을 알게 되고, 데이터를 프로그래밍 방식으로 조작하며, 필요한 형식으로 내보낼 수 있습니다. 이 접근 방식은 Microsoft Project에 대한 의존성을 없애고, 자동 보고를 간소화하며, 강력한 맞춤형 통합의 문을 엽니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-13  
**테스트 환경:** Aspose.Tasks for Java 24.5 (작성 시 최신 버전)  
**작성자:** Aspose