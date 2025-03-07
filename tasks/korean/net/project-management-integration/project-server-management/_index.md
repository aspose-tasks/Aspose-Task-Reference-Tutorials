---
title: Aspose.Tasks를 사용하여 MS Project Server 관리
linktitle: Aspose.Tasks를 사용하여 Project Server 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 원활한 MS Project Server 관리를 잠금 해제하세요. 프로젝트 작업을 손쉽게 자동화하세요.
weight: 23
url: /ko/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MS Project Server 관리

## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS Project Server를 관리하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있도록 지원하는 강력한 라이브러리로, 프로젝트 데이터를 원활하게 통합하고 조작할 수 있습니다.
## 전제조건
Aspose.Tasks를 사용하여 MS Project Server를 관리하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. Microsoft Project Server: 관리 권한이 있거나 최소한 프로젝트를 만들고 관리할 수 있는 권한이 있는 Microsoft Project Server 인스턴스에 액세스해야 합니다.
2.  .NET 라이브러리용 Aspose.Tasks: .NET 라이브러리용 Aspose.Tasks를 다운로드하여 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/tasks/net/).
3. 자격 증명: MS Project Server 인스턴스를 인증하는 데 필요한 자격 증명을 얻습니다. 여기에는 일반적으로 사용자 이름과 비밀번호가 포함됩니다.
## 네임스페이스 가져오기
시작하기 전에 C# 코드에서 필수 네임스페이스를 가져왔는지 확인하세요.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## 1단계: 인증 자격 증명 설정
먼저 MS Project Server 인스턴스에 연결하려면 인증 자격 증명을 설정해야 합니다. 여기에는 도메인 주소, 사용자 이름 및 비밀번호가 포함됩니다.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## 2단계: 프로젝트 로드
다음으로 Aspose.Tasks를 사용하여 관리하려는 MS 프로젝트 파일을 로드합니다.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## 3단계: 프로젝트 서버 관리자 만들기
 인스턴스화`ProjectServerManager` 이전에 정의된 자격 증명을 사용하는 개체입니다.
```csharp
var manager = new ProjectServerManager(credentials);
```
## 4단계: 저장 옵션 정의
프로젝트에 대한 특정 저장 옵션을 정의합니다. 예를 들어 작업에 대한 시간 초과를 설정할 수 있습니다.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## 5단계: 프로젝트 생성 또는 업데이트
마지막으로 MS Project Server에서 프로젝트를 생성하거나 업데이트합니다.
```csharp
manager.CreateNewProject(project, options);
```
축하해요! .NET용 Aspose.Tasks를 사용하여 MS Project Server를 성공적으로 관리했습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 프로그래밍 방식으로 MS Project Server를 관리하는 방법을 살펴보았습니다. 제공된 단계를 사용하면 Aspose.Tasks를 .NET 애플리케이션에 원활하게 통합하여 MS Project Server에서 프로젝트 관리 작업을 자동화할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project Server와 호환됩니까?
A: Aspose.Tasks는 다양한 버전의 Microsoft Project Server와의 통합을 지원하여 다양한 환경 간의 호환성을 보장합니다.
### Q: Aspose.Tasks를 사용하여 프로젝트에서 대량 작업을 수행할 수 있나요?
A: 예, Aspose.Tasks를 사용하면 MS Project Server에서 프로젝트 생성, 업데이트, 삭제와 같은 대량 작업을 수행할 수 있습니다.
### Q: Aspose.Tasks는 프로젝트 일정 및 리소스 관리를 지원합니까?
A: 물론 Aspose.Tasks는 프로젝트 일정 관리, 리소스 할당 및 작업 관리 기능에 대한 포괄적인 지원을 제공합니다.
### Q: Aspose.Tasks를 사용하여 보고 작업을 자동화할 수 있습니까?
A: 예, Aspose.Tasks를 사용하면 프로젝트 데이터를 기반으로 사용자 정의 보고서 생성을 자동화하여 효율적인 프로젝트 모니터링 및 분석을 촉진할 수 있습니다.
### Q: Aspose.Tasks를 구매하기 전에 사용해 볼 수 있나요?
 A: 예, 다음에서 무료 평가판에 액세스하여 Aspose.Tasks의 기능을 탐색할 수 있습니다.[웹사이트](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
