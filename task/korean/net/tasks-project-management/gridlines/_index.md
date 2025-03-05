---
title: Aspose.Tasks에 대한 MS 프로젝트의 눈금선 사용자 정의
linktitle: Aspose.Tasks의 눈금선
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 눈금선을 사용자 정의하는 방법을 알아보세요. 따라하기 쉬운 단계를 통해 프로젝트 시각화 및 관리를 향상하세요.
type: docs
weight: 23
url: /ko/net/tasks-project-management/gridlines/
---
## 소개

프로젝트 관리에서 시각적 표현은 프로젝트 일정, 종속성 및 진행 상황을 이해하는 데 중요한 역할을 합니다. Aspose.Tasks for .NET은 프로그래밍 방식으로 프로젝트 파일을 조작할 수 있는 강력한 도구를 제공합니다. 그러한 기능 중 하나는 Aspose.Tasks를 사용하여 MS 프로젝트에서 눈금선을 사용자 정의하는 기능입니다.

## 전제조건

.NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 눈금선을 사용자 정의하기 전에 다음 사항이 있는지 확인하세요.

### 1. .NET용 Aspose.Tasks 설치

 시작하려면 개발 환경에 Aspose.Tasks for .NET을 설치해야 합니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[.NET 다운로드 페이지용 Aspose.Tasks](https://releases.aspose.com/tasks/net/).

### 2. C# 및 .NET Framework에 대한 기본 지식

C# 프로그래밍 언어 및 .NET 프레임워크에 익숙하면 제공된 예제를 이해하고 구현하는 데 도움이 됩니다.

## 네임스페이스 가져오기

MS 프로젝트에서 눈금선 사용자 정의를 구현하기 전에 C# 코드에서 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 필수 클래스 및 메서드에 대한 액세스를 제공합니다.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

.NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 눈금선을 사용자 정의하는 방법을 이해하기 위해 제공된 예제를 여러 단계로 분석해 보겠습니다.

## 1단계: 프로젝트 개체 초기화

```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

 이 단계에서는`Project` MS 프로젝트 파일에 대한 경로를 제공하여 개체를 만듭니다.

## 2단계: ImageSaveOptions 정의

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
```

 여기서는`ImageSaveOptions` 출력 이미지를 저장할 형식을 지정하는 객체입니다.

## 3단계: 눈금선 사용자 정의

```csharp
var gridline = new Gridline
{
	// 격자선 유형을 설정합니다.
	GridlineType = GridlineType.GanttRow, 
	// 그리드라인의 LinePattern 설정
	Pattern = LinePattern.Dashed
};
```

 이 단계에서 우리는`Gridline` 개체를 선택하고 해당 유형과 패턴을 사용자 정의합니다. 이 예에서는 격자선 유형을 다음으로 설정합니다.`GanttRow` 그리고 패턴을`Dashed`.

## 4단계: 옵션에 눈금선 추가

```csharp
options.Gridlines = new List<Gridline>();
options.Gridlines.Add(gridline);
```

 여기서는 사용자 정의된 격자선을`ImageSaveOptions`.

## 5단계: 사용자 정의된 그리드라인으로 프로젝트 저장

```csharp
project.Save(DataDir + "PrintProjectPagesToSeparateFiles_out.png", options);
```

마지막으로 사용자 정의된 그리드라인이 포함된 프로젝트를 이미지 파일로 저장합니다.

## 결론

.NET용 Aspose.Tasks를 사용하여 MS 프로젝트에서 눈금선을 사용자 정의하면 프로젝트 데이터 시각화에 유연성이 제공됩니다. 단계별 가이드를 따르면 프로젝트 관리 요구 사항을 효율적으로 충족하도록 눈금선을 쉽게 조정할 수 있습니다.

## FAQ

### Q1: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트의 다양한 보기에 대한 눈금선을 사용자 정의할 수 있습니까?

A: 예, Aspose.Tasks for .NET을 사용하면 간트 차트, 작업 시트 및 리소스 시트를 포함한 다양한 보기에 대한 눈금선을 사용자 정의할 수 있습니다.

### Q2: Aspose.Tasks for .NET은 다른 버전의 MS 프로젝트 파일과 호환됩니까?

A: 예, .NET용 Aspose.Tasks는 MPP 및 XML 형식을 포함하여 다양한 버전의 MS 프로젝트 파일을 지원합니다.

### Q3: .NET용 Aspose.Tasks를 사용하여 눈금선 색상과 두께를 사용자 지정할 수 있나요?

A: 물론입니다. 패턴뿐만 아니라 격자선의 색상과 두께도 원하는 대로 맞춤 설정할 수 있습니다.

### Q4: Aspose.Tasks for .NET은 다른 프로젝트 관리 도구와의 통합을 지원합니까?

A: 예, Aspose.Tasks for .NET은 널리 사용되는 프로젝트 관리 도구 및 플랫폼과의 통합을 위한 광범위한 문서와 지원을 제공합니다.

### Q5: Aspose.Tasks for .NET에 사용할 수 있는 평가판이 있습니까?

 A: 예, 무료 평가판을 다운로드할 수 있습니다.[.NET용 Aspose.Tasks](https://forum.aspose.com/c/tasks/15). 구매하기 전에 기능을 살펴보세요.