---
title: Aspose.Tasks의 데이터베이스 설정
linktitle: Aspose.Tasks의 데이터베이스 설정
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Primavera 데이터베이스에서 프로젝트를 가져오는 방법을 알아보세요. 이 포괄적인 튜토리얼에서 단계별 지침을 얻으세요.
type: docs
weight: 29
url: /ko/net/calendar-scheduling/database-settings/
---
## 소개

Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일로 작업할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 Primavera 데이터베이스에서 프로젝트를 가져오는 데 중점을 둘 것입니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
- 필요한 권한과 함께 Primavera 데이터베이스에 액세스합니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 C# 프로젝트로 가져와야 합니다. 이러한 네임스페이스는 .NET용 Aspose.Tasks를 사용하는 데 필요한 클래스와 메서드에 대한 액세스를 제공합니다.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: 연결 문자열 정의

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 이 단계에서는 Primavera 데이터베이스에 연결하기 위한 연결 문자열을 정의합니다. 교체했는지 확인하세요.`DataDir` 데이터베이스 파일이 있는 디렉터리로 변경하세요.

## 2단계: 데이터베이스 설정 생성

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 여기서는 인스턴스를 생성합니다.`PrimaveraDbSettings` 클래스를 사용하여 연결 문자열과 프로젝트 ID를 매개변수로 전달합니다. 요구 사항에 따라 프로젝트 ID를 조정합니다.

## 3단계: 공급자 고정 이름 설정

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

공급자 고정 이름을 지정합니다. 이 예에서는 SQLite를 사용하고 있지만 데이터베이스 공급자에 따라 변경할 수 있습니다.

## 4단계: 프로젝트 로드

```csharp
var project = new Project(settings);
```

 새로 만들기`Project` 개체를 사용하여 데이터베이스 설정을 매개변수로 전달합니다.

## 5단계: 프로젝트 저장

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

마지막으로 프로젝트를 지정된 파일 형식으로 원하는 위치에 저장합니다.

## 결론

이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Primavera 데이터베이스에서 프로젝트를 가져오는 방법을 배웠습니다. 제공된 단계를 따르면 프로젝트 가져오기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks for .NET을 사용하여 다른 데이터베이스 공급자로부터 프로젝트를 가져올 수 있나요?

A1: 예, 연결 문자열과 공급자 고정 이름을 적절하게 조정하여 다양한 데이터베이스 공급자로부터 프로젝트를 가져올 수 있습니다.

### Q2: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있습니까?

 A2: 예, 다음 사이트에서 Aspose.Tasks for .NET 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: .NET용 Aspose.Tasks에 대한 설명서는 어디에서 찾을 수 있습니까?

 A3: 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).

### Q4: .NET용 Aspose.Tasks에 대한 지원을 어떻게 받을 수 있나요?

 A4: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).

### Q5: Aspose.Tasks for .NET을 사용하려면 임시 라이선스가 필요합니까?

 A5: 라이브러리의 전체 기능을 평가하려면 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).