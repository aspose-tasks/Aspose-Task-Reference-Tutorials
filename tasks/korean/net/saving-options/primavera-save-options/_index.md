---
title: Aspose.Tasks를 사용하여 MS 프로젝트 옵션 Primavera 저장
linktitle: Aspose.Tasks에 대한 Primavera 저장 옵션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Primavera용 MS 프로젝트 옵션을 원활하게 저장하는 방법을 알아보세요. 단계별 튜토리얼을 따라해보세요.
type: docs
weight: 14
url: /ko/net/saving-options/primavera-save-options/
---
## 소개
Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일을 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 이 앱이 제공하는 주요 기능 중 하나는 인기 있는 프로젝트 관리 소프트웨어인 Primavera용 MS 프로젝트 옵션을 저장하는 기능입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 이를 달성하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- C# 및 .NET 프레임워크에 대한 기본 이해.
-  개발 환경에 설치된 .NET용 Aspose.Tasks. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
- 실험용 샘플 MS 프로젝트 파일입니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 C# 코드로 가져옵니다.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 1단계: MS 프로젝트 파일 로드
 작업하려는 MS 프로젝트 파일을 C# 애플리케이션에 로드하는 것부터 시작하세요. 다음을 사용하여 이 작업을 수행할 수 있습니다.`Project` Aspose.Tasks에서 제공하는 클래스입니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 2단계: Primavera 저장 옵션 정의
다음으로 Primavera 저장 옵션을 생성하고 요구 사항에 따라 사용자 정의합니다. 이 단계에는 활동 ID 접두사, 접미사, 증분, 활동 ID 번호 다시 매기기 여부 등의 매개변수 지정이 포함됩니다.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## 3단계: Primavera용 MS 프로젝트 옵션 저장
 이제 프로젝트 파일을 로드하고 Primavera 저장 옵션을 정의했으므로 Primavera에 대한 옵션을 저장할 차례입니다. 사용`Save` 에서 제공하는 방법`Project` 클래스, 원하는 출력 파일 경로 및 Primavera 저장 옵션을 전달합니다.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## 결론
결론적으로, .NET용 Aspose.Tasks를 활용하면 개발자는 Primavera용 저장 옵션을 포함하여 MS 프로젝트 파일을 원활하게 조작할 수 있습니다. 이 자습서에 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 효율적으로 통합할 수 있습니다.
## FAQ
### Q: Primavera용 MS 프로젝트 옵션을 저장할 때 활동 ID 외에 다른 매개변수를 사용자 정의할 수 있습니까?
A: 예, Aspose.Tasks는 리소스 할당 및 작업 예약을 포함하여 사용자 정의를 위한 광범위한 옵션을 제공합니다.
### Q: Aspose.Tasks는 Primavera 외에 다른 프로젝트 관리 소프트웨어도 지원합니까?
A: 예, Aspose.Tasks는 Oracle Primavera, Microsoft Project Server 등과 같은 널리 사용되는 프로젝트 관리 도구와 호환되는 다양한 형식을 지원합니다.
### Q: Aspose.Tasks는 소규모 및 기업 수준 프로젝트 모두에 적합합니까?
A: 물론 Aspose.Tasks는 모든 규모의 프로젝트에서 작업하는 개발자의 요구 사항을 충족하고 확장성과 강력한 성능을 제공하도록 설계되었습니다.
### Q: 구매하기 전에 Aspose.Tasks를 무료로 사용해 볼 수 있나요?
 A: 예, Aspose.Tasks의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/) 기능과 기능을 살펴보겠습니다.
### Q: Aspose.Tasks를 사용하는 동안 문제가 발생하거나 질문이 있는 경우 어디서 지원을 받을 수 있나요?
 A: Aspose.Tasks 커뮤니티 및 지원팀에서 도움을 요청할 수 있습니다.[법정](https://forum.aspose.com/c/tasks/15).