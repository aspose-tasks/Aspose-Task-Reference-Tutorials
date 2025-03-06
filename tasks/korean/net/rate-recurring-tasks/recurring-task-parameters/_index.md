---
title: Aspose.Tasks에서 반복 작업 매개변수 설정
linktitle: Aspose.Tasks에서 반복 작업 매개변수 설정
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 Microsoft Project에서 반복 작업 매개변수를 설정하는 방법을 알아보세요. 단계별 가이드가 포함된 종합 튜토리얼입니다.
weight: 14
url: /ko/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 반복 작업 매개변수 설정

## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project 반복 작업 매개변수를 설정하는 과정을 안내합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. C# 프로그래밍 언어에 대한 기본 이해.
2. Visual Studio 또는 기타 C# IDE를 설치했습니다.
3. .NET 라이브러리용 Aspose.Tasks가 프로젝트에 설치되고 참조됩니다.

## 네임스페이스 가져오기
먼저 C# 코드에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
using Aspose.Tasks;
using System;

```
## 1단계: 문서 디렉터리 정의
```csharp
String DataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 문서 디렉토리 경로와 함께.
## 2단계: 프로젝트 파일 로드
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 이 코드 줄은 Microsoft Project 파일을`project` 변하기 쉬운.
## 3단계: 반복 작업 매개변수 정의
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
여기에서는 작업 이름, 기간, 반복 패턴, 반복 범위, 리소스 달력 무시 여부 등 반복 작업에 대한 매개 변수를 정의합니다.
## 4단계: 반복 작업을 위한 달력 설정
```csharp
parameters.SetCalendar(project, "Standard");
```
이 단계에서는 반복 작업의 달력을 설정합니다. 이 예에서는 달력을 "표준"으로 설정합니다.
## 5단계: 프로젝트에 매개변수 추가
```csharp
project.RootTask.Children.Add(parameters);
```
마지막으로 프로젝트의 루트 작업에 매개변수를 추가합니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 Microsoft Project 반복 작업 매개변수를 설정하는 방법을 보여주었습니다. 다음 단계를 따르면 프로젝트에서 반복되는 작업을 효율적으로 관리할 수 있습니다.
## 자주 묻는 질문
### 반복 패턴을 추가로 사용자 정의할 수 있나요?
예, Aspose.Tasks는 프로젝트 요구 사항에 따라 사용자 정의할 수 있는 다양한 반복 패턴과 옵션을 제공합니다.
### 구매하기 전에 체험판을 사용할 수 있나요?
 예, Aspose.Tasks에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://purchase.aspose.com/buy) 도서관의 기능을 평가합니다.
### Aspose.Tasks는 다른 프로젝트 파일 형식을 지원합니까?
예, Aspose.Tasks는 MPP, XML, XLSX 등을 포함한 다양한 프로젝트 파일 형식을 지원합니다.
### 구현 중에 문제가 발생하면 지원을 받을 수 있나요?
예, Aspose.Tasks 포럼을 방문하여 커뮤니티의 도움을 받거나 지원팀에 문의하여 직접적인 도움을 받을 수 있습니다.
### Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[웹사이트](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
