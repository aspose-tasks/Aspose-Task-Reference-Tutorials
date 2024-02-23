---
title: Aspose.Tasks에서 사용량 보기 구성
linktitle: Aspose.Tasks에서 사용량 보기 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks에서 작업 사용량 보기를 구성하는 방법을 알아보세요. 세부 단계를 통해 프로젝트 시각화를 향상합니다. 지금 라이브러리를 다운로드하세요!
type: docs
weight: 17
url: /ko/net/text-view-configuration/usage-views/
---
## 소개
프로젝트 관리 기능을 향상시키려는 .NET 개발자라면 Aspose.Tasks는 Microsoft Project 파일을 손쉽게 조작할 수 있는 강력한 도구입니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks를 사용하여 사용 보기를 구성하는 데 중점을 둘 것입니다. 더 나은 프로젝트 시각화를 위한 세부 정보와 함께 렌더링 작업 사용량 보기에 대한 통찰력을 얻으려면 따라 가십시오.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Aspose.Tasks 라이브러리: Aspose.Tasks 라이브러리가 .NET 프로젝트에 통합되어 있는지 확인하세요. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/net/) 설치 지침을 따르십시오.
- 문서 디렉터리: 프로젝트 문서가 저장되는 디렉터리를 설정합니다. 코드 조각의 "문서 디렉터리"를 문서 디렉터리의 실제 경로로 바꾸세요.
## 네임스페이스 가져오기
제공된 코드 조각에서 특정 네임스페이스의 사용법을 확인할 수 있습니다. 원활한 통합을 위해 프로젝트에 다음을 포함해야 합니다.
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## 1단계: 세부 정보가 포함된 렌더링 작업 사용량 보기
세부 정보가 포함된 작업 사용량 보기를 렌더링하는 것부터 시작해 보겠습니다. 다음과 같이하세요:
## 1.1단계: 프로젝트 로드
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## 1.2단계: 뷰 가져오기
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## 1.3단계: 보기 설정 사용자 정의
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## 1.4단계: 프로젝트를 PDF로 저장
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## 2단계: 세부정보 헤더 열 표시
이 단계에서는 세부 정보 헤더 열을 표시하고 프로젝트를 PDF로 저장하도록 보기 설정을 수정합니다.
## 2.1단계: 세부정보 헤더 열 표시
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## 2.2단계: 모든 행에 세부정보 헤더 반복
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## 2.3단계: 프로젝트를 PDF로 저장
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## 결론
축하해요! Aspose.Tasks에서 사용량 보기를 성공적으로 구성했습니다. 이 튜토리얼은 Aspose.Tasks 라이브러리를 사용하여 효율적인 프로젝트 관리 및 시각화를 위한 기반을 제공합니다.

### FAQ
### Q: Aspose.Tasks 문서는 어디에서 찾을 수 있나요?
 포괄적인 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/tasks/net/).
### Q: .NET용 Aspose.Tasks를 어떻게 다운로드할 수 있나요?
 라이브러리 다운로드[여기](https://releases.aspose.com/tasks/net/).
### Q: Aspose.Tasks는 어디서 구매할 수 있나요?
 Aspose.Tasks를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### Q: 무료 평가판이 제공됩니까?
 예, 무료 평가판을 살펴보세요[여기](https://releases.aspose.com/).
### Q: 지원이 필요하거나 질문이 있나요?
 지원 포럼 방문[여기](https://forum.aspose.com/c/tasks/15).