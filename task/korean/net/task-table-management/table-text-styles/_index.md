---
title: Aspose.Tasks의 테이블 텍스트 스타일 가이드 사용자 정의
linktitle: Aspose.Tasks에서 테이블 텍스트 스타일 구성
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 프로젝트 시각화를 향상하세요. 테이블 텍스트 스타일을 단계별로 구성하는 방법을 알아보세요. 효율성과 프레젠테이션을 향상합니다.
type: docs
weight: 14
url: /ko/net/task-table-management/table-text-styles/
---
## 소개
프로젝트 관리의 세계에서는 작업의 효과적인 시각화가 성공에 매우 중요합니다. Aspose.Tasks for .NET은 테이블 텍스트 스타일을 사용자 정의할 수 있는 강력한 솔루션을 제공하여 프로젝트에서 텍스트 항목의 모양을 맞춤화할 수 있습니다. 이 단계별 가이드에서는 Aspose.Tasks for .NET을 사용하여 테이블 텍스트 스타일을 구성하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- .NET용 Aspose.Tasks: 최신 버전의 .NET용 Aspose.Tasks가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/net/).
- 문서 디렉터리: 문서 디렉터리를 설정합니다. 코드의 "문서 디렉토리"를 실제 경로로 바꾸십시오.
-  유효한 Aspose 라이센스: 이 예에는 유효한 Aspose 라이센스가 필요합니다. 정식 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy) 또는 30일 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).
## 네임스페이스 가져오기
코딩을 시작하기 전에 Aspose.Tasks의 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
이제 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 로드 및 프로젝트 속성 설정
```csharp
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.NewTasksAreManual, false);
```
## 2단계: 간트 차트 보기에 액세스
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
## 3단계: 작업 이름 텍스트 스타일 사용자 정의
```csharp
var style1 = new TableTextStyle(1);
style1.Field = Field.TaskName;
style1.Font = new FontDescriptor("Impact", 12F, FontStyles.Bold | FontStyles.Italic);
view.TableTextStyles.Add(style1);
```
## 4단계: 작업 기간 텍스트 스타일 사용자 정의
```csharp
var style2 = new TableTextStyle(2);
style2.Field = Field.TaskDurationText;
style2.Font = new FontDescriptor("Impact", 16F, FontStyles.Underline);
view.TableTextStyles.Add(style2);
```
## 5단계: 사용자 정의 스타일로 프로젝트 저장
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(DataDir + "WorkWithTableTextStyle_out.mpp", options);
```
## 6단계: 라이선스 예외 처리
```csharp
catch (NotSupportedException ex)
{
    Console.WriteLine(
        ex.Message
        + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [Aspose](http://www.aspose.com/purchase/default.aspx).");
}
```
## 결론
Aspose.Tasks for .NET에서 테이블 텍스트 스타일을 사용자 정의하면 프로젝트의 시각적 표현을 향상시키는 유연하고 효율적인 방법을 제공합니다. 몇 가지 간단한 단계를 통해 더욱 맞춤화되고 영향력 있는 프로젝트 관리 환경을 만들 수 있습니다.
## 자주 묻는 질문
### 라이선스 없이 .NET용 Aspose.Tasks를 사용할 수 있나요?
 아니요, 이 기능을 사용하려면 유효한 Aspose 라이선스가 필요합니다. 라이센스를 취득하실 수 있습니다[여기](https://purchase.aspose.com/buy) 또는 30일 임시 라이센스를 받으세요[여기](https://purchase.aspose.com/temporary-license/).
### 다른 작업 속성의 글꼴 스타일을 어떻게 업데이트합니까?
 간단히 추가 생성`TableTextStyle` 원하는 필드와 글꼴 설정을 지정합니다.
### .NET용 Aspose.Tasks에 사용할 수 있는 평가판이 있습니까?
 예, 평가판을 다운로드할 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Tasks에서 제공하는 다른 시각화 옵션이 있습니까?
예, Aspose.Tasks는 다양한 프로젝트 관리 요구 사항을 충족하기 위해 다양한 시각화 기능을 제공합니다.
### 특정 작업 유형에 맞게 스타일을 사용자 정의할 수 있나요?
물론, 그에 따라 필드 및 글꼴 설정을 조정하여 사용자 정의를 다양한 작업 유형으로 확장할 수 있습니다.