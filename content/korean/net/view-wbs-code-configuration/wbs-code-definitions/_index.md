---
title: Aspose.Tasks에서 WBS 코드 정의 정의
linktitle: Aspose.Tasks에서 WBS 코드 정의 정의
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks는 효율적인 프로젝트 관리를 지원합니다. 포괄적인 튜토리얼을 통해 WBS 코드를 쉽게 마스터하세요. 오늘 워크플로를 간소화하세요!
type: docs
weight: 13
url: /ko/net/view-wbs-code-configuration/wbs-code-definitions/
---
## 소개
프로젝트 관리가 발전함에 따라 프로세스를 간소화하는 강력한 도구의 필요성도 커지고 있습니다. .NET 개발 영역에서 Aspose.Tasks는 프로젝트 관리 작업을 처리하기 위한 강력한 라이브러리로 돋보입니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 WBS(작업 분할 구조) 코드를 정의하는 프로세스를 자세히 살펴보겠습니다. WBS 코드는 프로젝트 계층 구조에 질서를 부여하여 효율적인 추적 및 구성을 가능하게 합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- .NET 개발에 대한 실무 지식.
-  .NET 라이브러리용 Aspose.Tasks가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- 코드 편집기(Visual Studio 권장)
## 네임스페이스 가져오기
.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
    
    using Aspose.Tasks.Saving;
```
이제 WBS 코드를 정의하는 과정을 관리 가능한 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 설정
```csharp
String DataDir = "Your Document Directory";
```
"Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.
## 2단계: 프로젝트 초기화
```csharp
var project = new Project();
```
Aspose.Tasks를 사용하여 새 프로젝트 인스턴스를 만듭니다.
## 3단계: WBS 코드 정의 구성
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
코드 생성, 고유성 확인, 코드 접두어 등 WBS 코드 정의 매개변수를 설정합니다.
## 4단계: WBS 코드 마스크 정의
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
길이, 구분 기호 및 순서를 기반으로 구조 코드에 WBS 코드 마스크를 지정합니다.
## 5단계: 작업 생성 및 다시 계산
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
project.Recalculate();
```
프로젝트 계층 구조에 작업을 추가하고 다시 계산하여 WBS 코드를 업데이트합니다.
## 6단계: 프로젝트 저장
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
새로 정의된 WBS 코드로 프로젝트를 저장합니다.
## 결론
이 튜토리얼에서는 WBS 코드 정의에 있어 .NET용 Aspose.Tasks의 강력한 기능을 살펴보았습니다. 다음 단계를 수행하면 프로젝트 관리 기능을 향상시켜 워크플로우에 구조와 효율성을 더할 수 있습니다.
## 자주 묻는 질문
### Aspose.Tasks는 모든 .NET 버전과 호환됩니까?
예, Aspose.Tasks는 다양한 .NET 버전을 지원하여 다양한 개발 환경과의 호환성을 보장합니다.
### WBS 코드 형식을 추가로 사용자 정의할 수 있나요?
전적으로. Aspose.Tasks는 광범위한 유연성을 제공하므로 특정 프로젝트 요구 사항에 맞게 WBS 코드를 맞춤화할 수 있습니다.
### 정의할 수 있는 WBS 코드 수에 제한이 있습니까?
Aspose.Tasks는 확장성을 제공하며 프로젝트 복잡성에 따라 상당한 수의 WBS 코드를 정의할 수 있습니다.
### 내 프로젝트에서 WBS 코드 관련 문제를 해결하려면 어떻게 해야 합니까?
 Aspose.Tasks 포럼(링크[지원하다](https://forum.aspose.com/c/tasks/15))은 도움을 구하고 문의 사항을 해결하는 데 유용한 리소스입니다.
### Aspose.Tasks를 구매하기 전에 사용할 수 있는 평가판이 있나요?
 예, Aspose.Tasks에 액세스하여 기능과 기능을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 버전.