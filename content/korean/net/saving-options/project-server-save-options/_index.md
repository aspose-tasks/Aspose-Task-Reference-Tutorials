---
title: Aspose.Tasks에 대한 서버 저장 MS 프로젝트 옵션
linktitle: Aspose.Tasks에 대한 Project Server 저장 옵션
second_title: Aspose.태스크 .NET API
description: Project Server 통합을 사용하여 Aspose.Tasks에 대한 Microsoft Project 옵션을 저장하는 방법을 알아보세요. 프로젝트 관리 워크플로를 강화하세요.
type: docs
weight: 16
url: /ko/net/saving-options/project-server-save-options/
---
## 소개
이 튜토리얼에서는 Project Server를 사용하여 Aspose.Tasks에 대한 Microsoft Project 옵션을 저장하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 작업할 수 있게 해주는 강력한 .NET API입니다. Project Server 기능을 활용하여 Aspose.Tasks를 프로젝트 관리 워크플로에 원활하게 통합할 수 있습니다. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
   
2. Project Server에 대한 액세스: Project Server 인스턴스의 액세스 자격 증명과 URL이 필요합니다. 아직 없는 경우 다음에서 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).
3. Microsoft Project 파일: Aspose.Tasks를 사용하여 저장하려는 Microsoft Project 파일(.mpp)을 준비합니다.

## 네임스페이스 가져오기
먼저 프로젝트에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## 1단계: 프로젝트 및 자격 증명 초기화
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 꼭 교체하세요`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,그리고`Password` 실제 값으로.
## 2단계: 프로젝트 서버 관리자 만들기
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## 3단계: 저장 옵션 정의
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 조정하다`ProjectGuid`, `ProjectName`, `Timeout` ,그리고`PollingInterval` 귀하의 요구 사항에 따라.
## 4단계: 서버에 프로젝트 저장
```csharp
manager.CreateNewProject(project, options);
```
그러면 지정된 옵션을 사용하여 프로젝트가 Project Server에 저장됩니다.

## 결론
이 튜토리얼에서는 Project Server 통합을 사용하여 Aspose.Tasks에 대한 Microsoft Project 옵션을 저장하는 방법을 배웠습니다. 이러한 단계를 따르면 Aspose.Tasks를 프로젝트 관리 워크플로우에 원활하게 통합하여 효율성과 생산성을 향상시킬 수 있습니다.
## FAQ
### Q: 다른 버전의 Microsoft Project에서 Aspose.Tasks를 사용할 수 있나요?
A: 예, Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Q: Aspose.Tasks에 사용할 수 있는 평가판이 있나요?
 A: 예, Aspose.Tasks의 무료 평가판 버전을 다음에서 얻을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks는 멀티스레딩을 지원합니까?
A: 예, Aspose.Tasks는 스레드로부터 안전하도록 설계되어 프로젝트 데이터에 대한 동시 액세스를 허용합니다.
### 질문: Project Server 통합을 사용할 때 저장 옵션을 사용자 정의할 수 있습니까?
A: 예, 프로젝트 이름, 시간 초과, 폴링 간격 등의 저장 옵션을 요구 사항에 맞게 맞춤 설정할 수 있습니다.
### Q: Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 답변: 다음 웹사이트에서 지원과 도움을 받으실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).