---
title: Aspose.Tasks에서 반복 작업 정보 추출
linktitle: Aspose.Tasks에서 반복 작업 정보 추출
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 반복 작업 정보를 추출하는 방법을 알아보세요. .NET 개발자를 위한 손쉬운 통합.
type: docs
weight: 13
url: /ko/net/rate-recurring-tasks/recurring-task-information/
---
## 소개
Aspose.Tasks for .NET은 개발자가 .NET 애플리케이션에서 Microsoft Project 파일로 작업할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 MS 프로젝트 파일에서 반복 작업 정보를 추출하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. C# 프로그래밍 언어에 대한 기본 이해.
2. 시스템에 Visual Studio가 설치되어 있습니다.
3.  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
## 네임스페이스 가져오기
시작하려면 C# 코드에서 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System;
    
```
이제 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 경로 설정
```csharp
String DataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` MS 프로젝트 파일의 경로와 함께.
## 2단계: MS 프로젝트 파일 로드
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 이 줄은 새로운 것을 초기화합니다`Project` 경로에 지정된 MS 프로젝트 파일을 로드하여 개체를 만듭니다.
## 3단계: 반복되는 작업 정보 읽기
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // 반복 작업 정보에 액세스하고 표시합니다.
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // 필요에 따라 다른 반복 작업 정보를 계속 표시합니다.
}
```
이 루프는 프로젝트의 모든 작업을 반복하고 각 작업에 연관된 반복 정보가 있는지 확인합니다. 그렇다면 시작 날짜, 기간, 종료 날짜 등과 같은 반복 작업의 다양한 속성을 검색하고 표시합니다.
## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 MS 프로젝트 파일에서 반복 작업 정보를 추출하는 방법을 배웠습니다. 이러한 지식을 바탕으로 이제 이 기능을 .NET 애플리케이션에 통합하여 반복 작업을 보다 효율적으로 처리할 수 있습니다.
## FAQ
### Q: Aspose.Tasks for .NET을 사용하여 반복 작업 정보를 수정할 수 있나요?
A: 예, 제공된 API를 사용하여 프로그래밍 방식으로 반복 작업 정보를 수정할 수 있습니다.
### Q: Aspose.Tasks는 MS Project 외에 다른 프로젝트 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 MPP, XML, CSV와 같은 다양한 프로젝트 파일 형식을 지원합니다.
### Q: Aspose.Tasks for .NET에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: .NET용 Aspose.Tasks에 대한 설명서는 어디서 찾을 수 있나요?
 A: 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
### Q: Aspose.Tasks for .NET에 대한 기술 지원은 어떻게 받을 수 있나요?
 A: Aspose.Tasks 포럼에서 기술 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).