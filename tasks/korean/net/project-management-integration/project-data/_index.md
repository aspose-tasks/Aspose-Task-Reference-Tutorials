---
title: Aspose.Tasks로 프로젝트 데이터 마스터링
linktitle: Aspose.Tasks에서 프로젝트 데이터 작업
second_title: Aspose.태스크 .NET API
description: .NET에서 Aspose.Tasks를 사용하여 Microsoft Project 데이터를 조작하는 방법을 알아보세요. 쉽게 작업을 생성하고, 리소스를 추가하고, 프로젝트를 저장하세요.
weight: 16
url: /ko/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks로 프로젝트 데이터 마스터링

## 소개
이 튜토리얼에서는 .NET용 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 데이터로 작업하는 방법을 살펴보겠습니다. Aspose.Tasks는 작업 생성, 리소스 추가, 속성 설정, 다양한 형식으로 프로젝트 저장 등 프로젝트 파일을 조작하는 강력한 기능을 제공합니다.
## 전제조건
시작하기 전에 다음 사항을 확인하세요.
1.  Aspose.Tasks 라이브러리 설치: 다음에서 Aspose.Tasks 라이브러리를 다운로드하여 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: .NET 개발 환경이 설정되어 있는지 확인하세요.
3. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
Aspose.Tasks로 작업하기 전에 필요한 네임스페이스를 프로젝트로 가져옵니다.
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1단계: 프로젝트 개체 초기화
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project();
```
 이 줄은`Project` Microsoft Project 파일을 나타내는 클래스입니다.
## 2단계: 프로젝트 속성 설정
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
이 줄은 작업 형식 및 작업 생성 모드와 같은 프로젝트 속성을 설정하는 방법을 보여줍니다.
## 3단계: 작업 추가
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
여기에서는 "Task 1"이라는 새 작업이 프로젝트의 루트 작업에 추가됩니다.
## 4단계: 작업 속성 설정
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
이 줄은 "작업 1"의 시작 날짜, 기간 및 완료 날짜를 설정합니다.
## 5단계: 리소스 추가
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
이 부분에서는 프로젝트에 작업 리소스를 추가하는 방법을 보여줍니다.
## 6단계: 작업에 자원 할당
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
이 줄은 특정 시작, 작업 및 완료 날짜를 사용하여 이전에 추가된 작업 자원을 "작업 1"에 할당하는 방법을 보여줍니다.
## 7단계: 프로젝트 저장
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
마지막으로 프로젝트는 Microsoft Project XML 파일 형식으로 저장됩니다.

## 결론
이 튜토리얼에서는 .NET의 Aspose.Tasks 라이브러리를 사용하여 Microsoft Project 데이터로 작업하는 방법을 배웠습니다. 단계별 가이드에 따라 프로젝트 파일을 조작하고, 작업과 리소스를 추가하고, 작업에 리소스를 할당하고, 프로젝트를 다양한 형식으로 저장할 수 있습니다.
## FAQ
### Q: Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks는 복잡한 프로젝트 구조에 대한 포괄적인 지원을 제공하여 작업, 자원 및 할당을 효율적으로 관리할 수 있도록 해줍니다.
### Q: Aspose.Tasks는 다른 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 다양한 Microsoft Project 버전을 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Q: Aspose.Tasks를 다른 .NET 라이브러리와 통합할 수 있나요?
A: 물론 Aspose.Tasks는 다른 .NET 라이브러리와 원활하게 통합되어 개발 프로젝트에 유연성을 제공합니다.
### Q: Aspose.Tasks는 프로젝트 일정 알고리즘을 지원합니까?
A: 예, Aspose.Tasks에는 프로젝트 타임라인과 리소스 활용도를 최적화하는 데 도움이 되는 고급 일정 알고리즘이 포함되어 있습니다.
### Q: Aspose.Tasks 사용자를 위한 커뮤니티 포럼이 있나요?
 A: 예, 유용한 리소스를 찾고 다른 Aspose.Tasks 사용자와 교류할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
