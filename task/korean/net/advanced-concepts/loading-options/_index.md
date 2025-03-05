---
title: Aspose.Tasks의 로딩 옵션
linktitle: Aspose.Tasks의 로딩 옵션
second_title: Aspose.태스크 .NET API
description: 단계별 지침을 통해 Aspose.Tasks for .NET의 강력한 기능을 활용하여 Microsoft Project 문서를 효율적으로 관리하는 방법을 알아보세요.
type: docs
weight: 16
url: /ko/net/advanced-concepts/loading-options/
---
## 소개

Aspose.Tasks for .NET은 개발자가 Microsoft Project 문서를 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 프로젝트 파일을 생성, 읽기, 쓰기 또는 변환해야 하는 경우 Aspose.Tasks는 작업을 간소화할 수 있는 광범위한 기능을 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Tasks 사용의 필수 사항을 자세히 살펴보고 주요 프로세스를 간단하고 실행 가능한 단계로 분류합니다.

## 전제조건

.NET용 Aspose.Tasks를 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.

1. Visual Studio: Visual Studio 또는 원하는 다른 IDE를 설치합니다.
2.  .NET용 Aspose.Tasks: 다음에서 Aspose.Tasks for .NET 라이브러리를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/tasks/net/).
3. C#의 기본 이해: C# 프로그래밍 언어 기본 사항을 숙지하세요.

이제 전제 조건을 다루었으므로 필수 네임스페이스를 살펴보고 단계별 가이드를 살펴보겠습니다.

## 네임스페이스 가져오기

C# 프로젝트에서 Aspose.Tasks 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

1. Aspose.Tasks: 이 네임스페이스는 프로젝트 문서 작업을 위한 핵심 클래스와 인터페이스를 제공합니다.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

이제 다양한 작업을 단계별 가이드로 나누어 보겠습니다.

## 1단계: 비밀번호로 보호된 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // FileStream을 초기화하여 프로젝트 파일 로드
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // LoadOptions 인스턴스 생성
        var options = new LoadOptions
        {
            Password = "password" // 비밀번호를 설정하세요
        };

        // 지정된 옵션으로 프로젝트 로드
        var project = new Project(stream, options);

        // 프로젝트 이름 표시
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## 2단계: 사용자 정의 옵션을 사용하여 Primavera 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // LoadOptions 인스턴스 생성
    var loadOptions = new LoadOptions();

    // Primavera 읽기 옵션 구성
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // 프로젝트 UID 설정
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Primavera 읽기 옵션 설정
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // 지정된 옵션을 사용하여 Primavera 프로젝트 로드
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // 프로젝트 이름 표시
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // 로드된 프로젝트로 추가 작업 수행
}
```

## 3단계: 파일 인코딩 지정

```csharp
public void SpecifyFileEncoding()
{
    // LoadOptions 인스턴스 생성
    LoadOptions lo = new LoadOptions();

    // Primavera XER 파일에서 프로젝트를 열 때 인코딩 지정
    lo.Encoding = Encoding.GetEncoding(1251);

    // 지정된 인코딩으로 프로젝트 로드
    var project = new Project("encoding1251.xer", lo);

    // 로드된 프로젝트로 추가 작업 수행
}
```

## 4단계: 오류 처리를 통해 Primavera 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // LoadOptions 인스턴스 생성
    var loadOptions = new LoadOptions();

    // Primavera 읽기 옵션 구성
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // 프로젝트 UID 설정
    };

    // Primavera 읽기 옵션 설정
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //사용자 정의 오류 처리 설정
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // 지정된 옵션과 오류 처리를 사용하여 Primavera 프로젝트 로드
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // 로드된 프로젝트로 추가 작업 수행
}

// 사용자 정의 오류 처리기 방법
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // 사용자 정의 오류 처리 논리 구현
}
```

다음 단계를 수행하면 Aspose.Tasks for .NET의 로딩 옵션을 효과적으로 활용하여 요구 사항에 따라 프로젝트 문서를 조작할 수 있습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Tasks의 로딩 옵션 작업에 대한 기본 사항을 살펴보았습니다. 암호로 보호된 프로젝트 로드부터 사용자 지정 오류 처리 지정까지 이러한 기술을 익히면 .NET 애플리케이션 내에서 프로젝트 파일을 효율적으로 관리할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks for .NET은 모든 버전의 Microsoft Project와 호환됩니까?

A1: 예, Aspose.Tasks for .NET은 다양한 버전의 Microsoft Project를 지원하여 다양한 환경에서의 호환성을 보장합니다.

### Q2: Aspose.Tasks for .NET을 다른 타사 라이브러리와 통합할 수 있나요?

A2: 물론입니다. Aspose.Tasks for .NET은 다른 .NET 라이브러리와 원활하게 통합되어 향상된 기능과 유연성을 제공합니다.

### Q3: .NET용 Aspose.Tasks는 문서와 지원 리소스를 제공합니까?

 A3: 그렇습니다, 당신은 포괄적인 내용을 참조할 수 있습니다[선적 서류 비치](https://reference.aspose.com/tasks/net/) 다음을 통해 지원을 받을 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15).

### Q4: Aspose.Tasks for .NET에 사용할 수 있는 라이선스 옵션이 있습니까?

 A4: 예. 무료 평가판 및 임시 라이센스를 포함한 다양한 라이센스 옵션을 탐색할 수 있습니다.[Aspose.Tasks 웹사이트](https://purchase.aspose.com/buy).

### Q5: Aspose.Tasks for .NET의 업데이트와 새로운 기능은 얼마나 자주 출시됩니까?

A5: .NET용 Aspose.Tasks는 진화하는 기술과 최적의 성능 및 호환성을 보장하기 위해 정기적인 업데이트와 기능 향상을 받습니다.