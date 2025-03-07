---
title: Aspose.Tasks에서 MS Project Server 자격 증명 관리
linktitle: Aspose.Tasks에서 Project Server 자격 증명 관리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS Project Server 자격 증명을 원활하게 관리하는 방법을 알아보세요. 프로젝트 관리 효율성을 향상시킵니다.
weight: 22
url: /ko/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 MS Project Server 자격 증명 관리

## 소개
프로젝트 관리 영역에서는 효과적인 조정과 원활한 의사소통이 성공적인 프로젝트 실행의 핵심입니다. Aspose.Tasks for .NET은 Microsoft Project Server 자격 증명을 관리하기 위한 포괄적인 솔루션을 제공하여 사용자가 프로젝트 데이터에 안전하게 액세스하고 조작할 수 있도록 합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS Project Server 자격 증명을 관리하는 프로세스를 자세히 살펴보고 사용자에게 원활한 경험을 보장하기 위한 각 단계를 안내합니다.
## 전제조건
.NET용 Aspose.Tasks를 사용하여 MS Project Server 자격 증명을 관리하는 과정을 시작하기 전에 다음 전제 조건이 충족되는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
 시작하려면 제공된 Aspose.Tasks for .NET을 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/). 설치 지침에 따라 라이브러리를 .NET 환경에 원활하게 통합하세요.
### 2. 액세스 자격 증명
MS Project Server에 액세스하는 데 필요한 자격 증명을 수집합니다. 여기에는 Project Server와 관련된 SharePoint 도메인 주소, 사용자 이름 및 비밀번호가 포함됩니다.

## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Tasks for .NET이 제공하는 기능을 효율적으로 활용하려면 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## 1단계: 문서 디렉터리 경로 정의
```csharp
String DataDir = "Your Document Directory";
```
## 2단계: SharePoint 도메인 주소, 사용자 이름 및 비밀번호 설정
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## 3단계: Project Server 자격 증명 만들기
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 4단계: 프로젝트 파일 로드
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## 5단계: 프로젝트 서버 관리자 초기화
```csharp
var manager = new ProjectServerManager(credentials);
```
## 6단계: 새 프로젝트 만들기
```csharp
manager.CreateNewProject(newProject);
```
## 7단계: 프로젝트 목록 검색
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## 8단계: 프로젝트 목록 반복
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## 결론
효율적인 프로젝트 관리를 위해서는 MS Project Server 자격 증명을 효과적으로 관리하는 것이 무엇보다 중요합니다. .NET용 Aspose.Tasks는 강력한 기능 세트를 제공하여 이 프로세스를 단순화합니다. 이 튜토리얼에 설명된 단계별 가이드를 따르면 사용자는 .NET용 Aspose.Tasks를 프로젝트에 원활하게 통합하여 프로젝트 데이터에 대한 안전한 액세스 및 조작을 보장할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project Server와 호환됩니까?
A: Aspose.Tasks for .NET은 다양한 버전의 Microsoft Project Server와 호환되도록 설계되어 사용자에게 다양성과 유연성을 보장합니다.
### Q: Aspose.Tasks for .NET을 기존 .NET 프로젝트에 통합할 수 있나요?
A: 예, Aspose.Tasks for .NET은 기존 .NET 프로젝트에 원활하게 통합되어 효율적인 프로젝트 관리 기능을 촉진할 수 있습니다.
### Q: Aspose.Tasks for .NET은 프로젝트 리소스 액세스를 지원합니까?
A: 물론입니다. Aspose.Tasks for .NET은 프로젝트 리소스 액세스 및 조작에 대한 포괄적인 지원을 제공하여 프로젝트 관리 효율성을 향상시킵니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 라이선스 옵션이 있습니까?
A: 예, Aspose.Tasks for .NET은 평가판 목적을 위한 임시 라이선스와 상업적 사용을 위한 전체 라이선스를 포함하여 유연한 라이선스 옵션을 제공합니다.
### Q: Aspose.Tasks for .NET에 대한 도움은 어디서 구할 수 있나요?
 A: Aspose.Tasks for .NET에 관한 질문이나 도움이 필요한 경우 다음 지원 포럼을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).## 완전한 소스 코드
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
