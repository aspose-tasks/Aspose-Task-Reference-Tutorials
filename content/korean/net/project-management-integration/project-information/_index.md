---
title: Aspose.Tasks에서 MS 프로젝트 정보 추출
linktitle: Aspose.Tasks에서 프로젝트 정보 추출
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 정보를 손쉽게 추출하는 방법을 알아보세요. 포괄적인 튜토리얼을 살펴보세요.
type: docs
weight: 20
url: /ko/net/project-management-integration/project-information/
---
## 소개
.NET용 Aspose.Tasks를 사용하여 Microsoft Project 파일에서 효율적으로 정보를 추출하고 싶으십니까? 이 튜토리얼에서는 프로세스를 단계별로 안내합니다. 하지만 구현 세부 사항을 자세히 알아보기 전에 먼저 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
### 1. .NET용 Aspose.Tasks
 .NET 라이브러리용 Aspose.Tasks를 설치했는지 확인하세요. 아직 다운로드하지 않으셨다면, 다음에서 다운로드하실 수 있습니다.[.NET 웹사이트용 Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. SharePoint용 자격 증명
MS 프로젝트 파일이 저장된 SharePoint에 액세스하려면 자격 증명이 필요합니다. 다음 정보가 있는지 확인하세요.
- SharePoint 도메인 주소
- 사용자 이름
- 비밀번호
## 네임스페이스 가져오기
전제조건을 정리하고 나면 이제 필요한 네임스페이스를 프로젝트로 가져올 차례입니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
이제 MS 프로젝트 정보를 추출하는 과정을 여러 단계로 나누어 보겠습니다.
## 1단계: 자격 증명 제공
먼저 Project Server에 액세스하려면 SharePoint 자격 증명을 제공해야 합니다.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## 2단계: 프로젝트 서버 관리자 초기화
 다음으로,`ProjectServerManager` 제공된 자격 증명을 사용하여 인스턴스를 생성합니다.
```csharp
var reader = new ProjectServerManager(credentials);
```
## 3단계: 프로젝트 목록 검색
이제 Project Server에서 프로젝트 목록을 검색할 수 있습니다.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## 4단계: 프로젝트 정보 인쇄
마지막으로 프로젝트 목록을 반복하고 해당 정보를 인쇄합니다.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## 결론
축하해요! .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 정보를 추출하는 방법을 성공적으로 배웠습니다. 이러한 지식을 바탕으로 이제 이 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### Q1: 모든 버전의 Microsoft Project에서 Aspose.Tasks for .NET을 사용할 수 있습니까?
A: 예, .NET용 Aspose.Tasks는 2003, 2007, 2010, 2013, 2016 및 2019를 포함한 다양한 버전의 Microsoft Project를 지원합니다.
### Q2: Aspose.Tasks for .NET은 Windows 및 Linux 플랫폼 모두와 호환됩니까?
A: 예, Aspose.Tasks for .NET은 Windows 및 Linux 플랫폼 모두와 호환되므로 다양한 개발 환경에 다용도로 사용할 수 있습니다.
### Q3: Aspose.Tasks for .NET을 사용하여 작업 종속성을 추출할 수 있나요?
답: 물론이죠! Aspose.Tasks for .NET은 기본 프로젝트 정보뿐만 아니라 작업 종속성 및 기타 복잡한 세부 정보도 추출할 수 있는 강력한 기능을 제공합니다.
### Q4: Aspose.Tasks for .NET은 기술 지원을 제공합니까?
 A: 예. Aspose.Tasks for .NET에 대한 기술 지원은 다음을 통해 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 질문을 하고 전문가에게 도움을 구할 수 있습니다.
### Q5: 구매하기 전에 .NET용 Aspose.Tasks를 사용해 볼 수 있나요?
 답: 물론이죠! Aspose.Tasks for .NET의 무료 평가판을 다음 사이트에서 이용할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/), 구매 결정을 내리기 전에 기능을 탐색할 수 있습니다.