---
title: Aspose.Tasks의 MS 프로젝트 개요 코드 처리 정의
linktitle: Aspose.Tasks에서 개요 코드 정의 처리
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 코드 정의를 처리하고 프로젝트 관리 애플리케이션을 강화하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/net/outline-code-page-settings/outline-code-definitions/
---
## 소개
Microsoft Project는 프로젝트 관리를 위한 강력한 도구이며 Aspose.Tasks for .NET은 프로젝트 파일을 프로그래밍 방식으로 조작하기 위한 포괄적인 지원을 제공합니다. 프로젝트 관리의 필수 측면 중 하나는 개요 코드를 사용하여 작업을 구성하는 것입니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 코드 정의를 처리하는 방법을 살펴보겠습니다.
## 전제조건
구현을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Tasks 설치
 개발 환경에 .NET용 Aspose.Tasks를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/).
### 2. C#과 .NET Framework의 기본 이해
이 튜토리얼에는 중급 수준의 C# 지식이 필요하므로 C# 프로그래밍 언어 및 .NET 프레임워크에 익숙해지세요.
### 3. 통합 개발 환경(IDE)
코딩 및 디버깅을 위해 시스템에 Visual Studio와 같은 IDE를 설치하십시오.
## 네임스페이스 가져오기
코딩을 시작하기 전에 Aspose.Tasks for .NET을 사용하는 데 필요한 네임스페이스를 가져와 보겠습니다.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
이제 명확한 이해를 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
먼저 MS 프로젝트 파일을 애플리케이션에 로드해야 합니다.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 2단계: 개요 코드 정의 생성
이제 새로운 개요 코드 정의를 만들어 보겠습니다.
```csharp
var outline = new OutlineCodeDefinition();
```
## 3단계: 필드 번호 및 이름 설정
개요 코드의 필드 번호와 이름을 설정합니다.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## 4단계: GUID 및 기타 속성 설정
개요 코드의 GUID 및 기타 속성을 설정합니다.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## 5단계: 윤곽선 마스크 추가
개요 코드에 개요 마스크를 추가합니다.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## 6단계: 기타 속성 설정
개요 코드의 추가 속성을 설정합니다.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## 7단계: 개요 값 추가
마지막으로 개요 코드에 개요 값을 추가해 보겠습니다.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## 결론
이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 개요 코드 정의를 처리하는 방법을 배웠습니다. 단계별 가이드를 따르면 프로젝트 파일의 개요 코드를 프로그래밍 방식으로 효율적으로 조작할 수 있습니다.
## FAQ
### Q1: 다른 버전의 MS 프로젝트 파일과 함께 Aspose.Tasks for .NET을 사용할 수 있습니까?
A: 예, .NET용 Aspose.Tasks는 MPP 및 XML 형식을 포함하여 다양한 버전의 MS 프로젝트 파일을 지원합니다.
### Q2: .NET용 Aspose.Tasks는 .NET Core와 호환됩니까?
A: 예, .NET용 Aspose.Tasks는 .NET Core와 호환되므로 크로스 플랫폼 애플리케이션을 개발할 수 있습니다.
### Q3: Aspose.Tasks for .NET을 사용하여 리소스 할당을 조작할 수 있습니까?
A: 예, Aspose.Tasks for .NET은 할당 추가, 업데이트 및 제거를 포함하여 리소스 할당을 조작하기 위한 광범위한 기능을 제공합니다.
### Q4: .NET용 Aspose.Tasks는 MS 프로젝트 파일에서 사용자 정의 필드 읽기를 지원합니까?
A: 물론 .NET용 Aspose.Tasks는 MS 프로젝트 파일에서 개요 코드를 포함한 사용자 정의 필드 읽기 및 쓰기를 지원합니다.
### Q5: Aspose.Tasks for .NET에 대한 커뮤니티 포럼이 있습니까?
 A: 예, Aspose.Tasks for .NET 커뮤니티 포럼에 가입할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15) 질문하고, 지식을 공유하고, 다른 개발자와 협력할 수 있습니다.