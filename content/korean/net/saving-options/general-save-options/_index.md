---
title: Aspose.Tasks에 대한 MS 프로젝트 저장 옵션 마스터하기
linktitle: Aspose.Tasks의 일반 저장 옵션
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일을 효율적으로 저장하는 방법을 알아보세요. 프로젝트에 맞게 출력 옵션을 손쉽게 사용자 정의하세요.
type: docs
weight: 17
url: /ko/net/saving-options/general-save-options/
---
## 소개
Aspose.Tasks for .NET은 Microsoft Project 파일을 프로그래밍 방식으로 조작하기 위한 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks에서 제공하는 다양한 옵션을 사용하여 MS 프로젝트 파일을 저장하는 복잡한 과정을 살펴보겠습니다. 특히 Aspose.Tasks에 사용할 수 있는 일반 저장 옵션에 중점을 두어 특정 요구 사항에 맞게 출력을 조정할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Tasks 설치: 다음에서 .NET용 Aspose.Tasks를 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/net/).
2. .NET Framework에 대한 기본 이해: .NET 프로그래밍 개념에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
코드를 살펴보기 전에 필요한 네임스페이스를 가져와야 합니다.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## 1단계: 프로젝트 파일 로드
먼저 Aspose.Tasks를 사용하여 MS 프로젝트 파일을 로드해야 합니다.
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## 2단계: 저장 옵션 정의
 요구 사항에 따라 저장 옵션을 정의합니다. 이 예에서는`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 3단계: 보기 열 사용자 정의
간트 차트, 자원 보기, 배정 보기 등 보기 열을 사용자 정의할 수 있습니다. 각각에 열을 추가하는 방법은 다음과 같습니다.
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## 4단계: 옵션과 함께 프로젝트 저장
마지막으로 지정된 옵션을 사용하여 프로젝트를 저장합니다.
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 결론
.NET용 Aspose.Tasks를 사용하여 일반 MS 프로젝트 저장 옵션을 마스터하면 프로젝트 요구 사항에 따라 출력 형식을 효율적으로 사용자 정의할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 다른 버전의 MS 프로젝트 파일과 호환됩니까?
A: 예, Aspose.Tasks는 다양한 버전의 MS 프로젝트 파일을 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Q: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 예, 무료 평가판을 통해 Aspose.Tasks를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 문서는 어디서 찾을 수 있나요?
A: 자세한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/tasks/net/), Aspose.Tasks 기능 사용에 대한 포괄적인 지침을 제공합니다.
### Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 평가 목적으로 임시 라이센스를 사용할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks 관련 쿼리에 대한 지원은 어디서 구할 수 있나요?
 A: Aspose.Tasks 커뮤니티 포럼에 가입할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15) 전문가와 동료 개발자의 도움을 받으세요.