---
title: Aspose.Tasks의 Microsoft Project 데이터베이스 설정
linktitle: Aspose.Tasks의 Microsoft Project 데이터베이스 설정
second_title: Aspose.태스크 .NET API
description: .NET 애플리케이션과의 원활한 통합을 위해 Aspose.Tasks를 사용하여 Microsoft Project 데이터베이스 설정을 구성하는 방법을 알아보세요.
type: docs
weight: 19
url: /ko/net/advanced-concepts/msp-database-settings/
---
## 소개

Aspose.Tasks를 사용하여 .NET 애플리케이션에서 Microsoft Project 데이터베이스로 작업하는 경우 프로젝트 데이터를 원활하게 가져오는 데 필요한 설정을 구성해야 합니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Tasks: 다음에서 Aspose.Tasks 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 데이터베이스에 대한 액세스: 데이터를 가져오려면 Microsoft Project 데이터베이스에 대한 액세스 권한이 있어야 합니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 프로젝트로 가져와야 합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## 1단계: 연결 문자열 만들기

Microsoft Project 데이터베이스에 대한 연결 문자열을 구성합니다. 예는 다음과 같습니다.

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

자리 표시자 값을 실제 데이터베이스 자격 증명으로 바꿔야 합니다.

## 2단계: MspDbSettings 구성

 인스턴스 만들기`MspDbSettings` 프로젝트 GUID와 함께 연결 문자열을 지정합니다.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## 3단계: 프로젝트 데이터 로드

 인스턴스화`Project` 구성된 설정을 사용하는 개체:

```csharp
var project = new Project(settings);
```

## 4단계: 프로젝트 데이터 저장

로드된 프로젝트 데이터를 파일에 저장합니다.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project 데이터베이스에 액세스하기 위한 설정을 구성하는 방법을 배웠습니다. 다음 단계를 따르면 프로젝트 데이터를 애플리케이션으로 원활하게 가져와 효율적인 프로젝트 관리를 촉진할 수 있습니다.

## FAQ

### Q1: 다른 버전의 Microsoft Project 데이터베이스에서 Aspose.Tasks를 사용할 수 있습니까?

A1: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project 데이터베이스를 지원하므로 통합 유연성이 가능합니다.

### Q2: 데이터베이스 연결 문제를 해결하려면 어떻게 해야 합니까?

A2: 연결 문자열이 적절한 자격 증명 및 데이터베이스 세부 정보로 올바르게 구성되었는지 확인하세요. 문서를 참조하거나 지원을 요청할 수도 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

### Q3: Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?

 A3: 예, 다음에서 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: 데이터베이스 상호 작용을 위해 스키마를 사용자 지정할 수 있습니까?

 A4: 예, 다음에 대한 스키마를 지정할 수 있습니다.`MspDbSettings` 데이터베이스 구조에 따른 개체입니다.

### Q5: Aspose.Tasks 사용에 대한 자세한 문서는 어디서 찾을 수 있나요?

 A5: 포괄적인 문서를 탐색할 수 있습니다.[여기](https://reference.aspose.com/tasks/net/) Aspose.Tasks 기능에 대한 자세한 통찰력을 얻으려면.