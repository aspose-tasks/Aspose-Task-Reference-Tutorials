---
title: Aspose.Tasks에서 MS 프로젝트 자원 할당 처리
linktitle: Aspose.Tasks에서 자원 할당 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 리소스 할당을 효율적으로 처리하는 방법을 알아보세요. 이 포괄적인 문서는 개발자를 위한 단계별 지침을 제공합니다.
type: docs
weight: 11
url: /ko/net/resource-risk-analysis/resource-assignments/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 리소스 할당을 효율적으로 처리하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 API입니다. 다음 단계를 수행하면 .NET 애플리케이션 내에서 리소스 할당을 효과적으로 관리하는 방법을 배우게 됩니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

## 네임스페이스 가져오기
먼저, .NET 프로젝트에서 Aspose.Tasks 기능을 활용하려면 필요한 네임스페이스를 가져와야 합니다. 여기에는 다음이 포함됩니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
이제 Aspose.Tasks를 사용하여 MS 프로젝트 리소스 할당을 처리하는 방법을 포괄적으로 이해하기 위해 제공된 예제를 여러 단계로 분석해 보겠습니다.
## 1단계: 프로젝트 및 달력 설정 지정
시작하려면 새 프로젝트 인스턴스를 만들고 프로젝트의 달력 설정을 구성하세요.
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## 2단계: 프로젝트에 작업 추가
다음으로, 프로젝트의 루트 작업에 새 작업을 추가합니다.
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## 3단계: 자원 할당 생성 및 시간대별 데이터 생성
이제 작업에 대한 새 자원 할당을 생성하고 시간대별 데이터를 생성합니다.
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## 4단계: 작업 분할
시작 날짜와 완료 날짜를 제공하여 작업을 여러 부분으로 분할합니다.
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## 5단계: 작업 윤곽 설정
과제에 대한 작업 윤곽 유형을 설정합니다.
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## 6단계: 프로젝트 저장
마지막으로 변경 사항을 적용하여 프로젝트 파일을 저장합니다.
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## 결론
결론적으로 Aspose.Tasks for .NET을 사용하여 Microsoft Project 리소스 할당을 처리하는 것은 간단한 프로세스입니다. 이 자습서에 설명된 단계를 따르면 .NET 애플리케이션 내에서 리소스 할당을 효율적으로 관리할 수 있습니다.
## FAQ
### Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?
예, Aspose.Tasks는 복잡한 프로젝트 구조를 효율적으로 처리할 수 있는 포괄적인 기능을 제공합니다.
### Aspose.Tasks는 다른 버전의 Microsoft Project와 호환됩니까?
예, Aspose.Tasks는 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.
### 특정 요구 사항에 따라 리소스 할당을 사용자 정의할 수 있나요?
물론 Aspose.Tasks는 특정 프로젝트 요구 사항을 충족하기 위해 리소스 할당을 위한 광범위한 사용자 정의 옵션을 제공합니다.
### Aspose.Tasks는 프로젝트 데이터를 다른 형식으로 내보내는 것을 지원합니까?
예, Aspose.Tasks를 사용하면 프로젝트 데이터를 XML, PDF, HTML 등 다양한 형식으로 내보낼 수 있습니다.
### Aspose.Tasks 사용자에게 기술 지원이 제공됩니까?
예, Aspose는 사용자의 질문이나 문제를 돕기 위해 포럼 및 기타 채널을 통해 전담 기술 지원을 제공합니다.