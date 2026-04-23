---
date: 2026-03-14
description: Aspose.Tasks를 사용하여 Microsoft Project 데이터베이스의 데이터베이스 스키마를 지정하는 방법과 프로젝트
  데이터를 .NET 애플리케이션으로 가져오는 방법을 배웁니다.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks를 사용한 Project DB의 데이터베이스 스키마 지정
url: /ko/net/advanced-concepts/msp-database-settings/
weight: 19
---

 placeholders, variable names.

Make sure bold formatting preserved.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Microsoft Project 데이터베이스에 대한 Aspose.Tasks 설정

## 소개

Aspose.Tasks를 사용하여 .NET 애플리케이션에서 Microsoft Project 데이터베이스를 다루고 있다면, **데이터베이스 스키마 지정** 및 **프로젝트 가져오기**를 원활하게 수행하기 위한 필수 설정을 구성해야 합니다. 이 튜토리얼에서는 **연결 구성** 방법, **.NET 연결 문자열 생성**, 그리고 최종적으로 **MPP로 프로젝트 저장**하는 과정을 단계별로 안내합니다.

## 빠른 답변
- **주된 목표는 무엇인가요?** 데이터베이스 스키마를 지정하고 Project 데이터베이스를 .NET 앱으로 가져오는 것입니다.  
- **필요한 라이브러리는?** Aspose.Tasks for .NET.  
- **Project Server에 어떻게 연결하나요?** 적절한 SQL 연결 문자열을 만든 뒤 `MspDbSettings`를 사용합니다.  
- **생성되는 파일 형식은?** `SaveFileFormat.Mpp`로 저장되는 MPP 파일입니다.  
- **스키마 이름을 변경할 수 있나요?** 예, `MspDbSettings`의 `Schema` 속성을 설정하면 됩니다.

## Project DB에 대한 데이터베이스 스키마 지정 방법

**데이터베이스 스키마 지정**이 필요한 이유를 이해하는 것이 중요합니다. 많은 기업 환경에서 Project Server 데이터베이스는 사용자 정의 스키마(예: `dbo`, `psdata`) 아래에 존재합니다. 스키마를 명시적으로 설정하면 Aspose.Tasks가 올바른 테이블을 조회하게 되어 런타임 오류를 방지하고 정확한 데이터 가져오기를 보장합니다.

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. Aspose.Tasks for .NET: Aspose.Tasks 라이브러리를 [here](https://releases.aspose.com/tasks/net/)에서 다운로드하고 설치합니다.  
2. Microsoft Project 데이터베이스에 대한 액세스: 가져올 데이터를 포함한 Microsoft Project 데이터베이스에 접근할 수 있어야 합니다.  

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 가져와야 합니다:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 단계 1: 연결 문자열 만들기

Microsoft Project 데이터베이스에 대한 연결 문자열을 구성합니다. 여기서 **.NET 연결 문자열 생성**과 **Project Server에 연결하는 방법**을 정의합니다.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro tip:** `DataSource`와 `InitialCatalog` 값을 다시 확인하세요; 해당 값은 서버 주소와 게시된 데이터베이스 이름과 일치해야 합니다.

## 단계 2: MspDbSettings 구성

`MspDbSettings` 인스턴스를 생성하고 연결 문자열을 전달한 뒤 `Schema` 속성을 설정하여 **데이터베이스 스키마 지정**을 수행합니다. 이렇게 하면 Aspose.Tasks가 어느 스키마를 조회할지 알 수 있습니다.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

여기서는 로드하려는 특정 프로젝트를 식별하는 프로젝트 GUID도 제공합니다.

## 단계 3: 프로젝트 데이터 로드

구성된 설정을 사용하여 `Project` 객체를 인스턴스화합니다. 이 단계는 데이터베이스에서 .NET 객체로 **프로젝트 가져오기**를 실제로 수행합니다.

```csharp
var project = new Project(settings);
```

## 단계 4: 프로젝트 데이터 저장

마지막으로 로드된 프로젝트를 디스크에 MPP 파일로 저장합니다. 이는 Aspose.Tasks API를 사용하여 **MPP로 프로젝트 저장**을 보여줍니다.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

코드를 실행한 후, `ImportProjectDataFromDatabase_out.mpp` 파일이 출력 디렉터리에 생성되어 Microsoft Project에서 열 수 있습니다.

## 결론

이 튜토리얼을 통해 Microsoft Project 데이터베이스에 대한 **데이터베이스 스키마 지정**, **연결 구성**, **프로젝트 가져오기**, 그리고 Aspose.Tasks for .NET을 사용한 **MPP로 프로젝트 저장** 방법을 배웠습니다. 이러한 단계는 Project Server 데이터를 맞춤형 애플리케이션에 원활히 통합하여 견고한 프로젝트 관리 솔루션을 구축하는 데 도움이 됩니다.

## 자주 묻는 질문

### Q1: Aspose.Tasks를 다양한 버전의 Microsoft Project 데이터베이스와 함께 사용할 수 있나요?
A1: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project 데이터베이스를 지원하므로 통합에 유연성을 제공합니다.

### Q2: 데이터베이스 연결 문제를 어떻게 해결할 수 있나요?
A2: 연결 문자열이 적절한 자격 증명 및 데이터베이스 세부 정보와 함께 올바르게 구성되어 있는지 확인하십시오. 또한 문서를 참고하거나 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 지원을 받을 수 있습니다.

### Q3: Aspose.Tasks의 체험판 버전이 있나요?
A3: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 이용할 수 있습니다.

### Q4: 데이터베이스 상호 작용을 위한 스키마를 사용자 정의할 수 있나요?
A4: 예, `MspDbSettings` 객체의 스키마를 데이터베이스 구조에 맞게 지정할 수 있습니다.

### Q5: Aspose.Tasks 사용에 대한 자세한 문서는 어디에서 찾을 수 있나요?
A5: Aspose.Tasks 기능에 대한 자세한 정보를 제공하는 포괄적인 문서는 [here](https://reference.aspose.com/tasks/net/)에서 확인할 수 있습니다.

**Q: 이 방법이 Azure SQL 데이터베이스에서도 작동하나요?**  
A: 물론입니다. `DataSource`를 Azure 서버 이름으로 조정하고 TLS/SSL 설정이 활성화되어 있는지 확인하면 됩니다.

**Q: 대용량 Project 데이터베이스를 타임아웃 없이 처리하려면 어떻게 해야 하나요?**  
A: 연결 문자열에서 `ConnectTimeout` 값을 늘리고 필요에 따라 프로젝트를 배치로 로드하는 방식을 고려하십시오.

---

**마지막 업데이트:** 2026-03-14  
**테스트 환경:** Aspose.Tasks 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}