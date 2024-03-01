---
title: Aspose.Tasks에 다양한 형식으로 MS 프로젝트 파일 저장
linktitle: Aspose.Tasks에 다양한 형식으로 파일 저장
second_title: Aspose.태스크 .NET API
description: .NET용 Aspose.Tasks를 사용하여 MS 프로젝트 파일을 다양한 형식으로 저장하는 방법을 알아보세요. 효율적인 프로젝트 관리를 위한 쉬운 단계.
type: docs
weight: 17
url: /ko/net/rate-recurring-tasks/save-file-formats/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일을 다양한 형식으로 저장하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 프로그래밍 방식으로 프로젝트 파일을 조작하고 관리할 수 있는 강력한 API입니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  .NET용 Aspose.Tasks: 다음에서 .NET용 Aspose.Tasks를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/net/).
2. 개발 환경: Visual Studio와 같은 .NET 개발 환경을 설정합니다.
3. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기
C# 파일 시작 부분에서 필요한 네임스페이스를 가져와야 합니다.
```csharp

using Aspose.Tasks.Saving;
```
## 1단계: 프로젝트 객체 생성
먼저 Project 개체를 만들고 Microsoft Project 파일을 로드합니다.
```csharp
// 문서 디렉터리의 경로입니다.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## 2단계: 프로젝트를 CSV 형식으로 저장
이제 프로젝트를 CSV 형식으로 저장해 보겠습니다. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## 3단계: 다른 형식 탐색
 Aspose.Tasks는 XML, PDF, XLSX 등과 같은 프로젝트 파일 저장을 위한 다양한 형식을 지원합니다. 간단히 변경하여 이러한 형식을 탐색할 수 있습니다.`SaveFileFormat` 매개변수`Save` 방법.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
다음 단계를 따르면 Aspose.Tasks for .NET을 사용하여 Microsoft Project 파일을 다양한 형식으로 쉽게 저장할 수 있습니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for .NET을 사용하여 MS 프로젝트 파일을 다양한 형식으로 저장하는 방법을 배웠습니다. Aspose.Tasks는 프로젝트 파일을 프로그래밍 방식으로 조작하는 프로세스를 단순화하여 개발자에게 유연성과 효율성을 제공합니다.
## FAQ
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 Microsoft Project 2003 XML, Microsoft Project 2007 MPP 및 Microsoft Project 2010 MPP 형식을 지원합니다.
### Q: 구매하기 전에 Aspose.Tasks를 사용해 볼 수 있나요?
 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어떻게 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks에 임시 라이선스를 사용할 수 있나요?
 A: 예, 평가 목적으로 임시 라이선스를 사용할 수 있습니다. 하나를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks의 가격은 얼마입니까?
 A: 가격 정보는 Aspose.Tasks 구매 페이지에서 확인할 수 있습니다.[여기](https://purchase.aspose.com/buy).