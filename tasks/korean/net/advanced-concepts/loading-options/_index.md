---
date: 2026-03-08
description: Aspose.Tasks for .NET를 사용하여 프로젝트 파일을 가져오는 방법을 배우고, 파일 인코딩을 지정하고 Microsoft
  Project 파일을 효율적으로 로드하는 방법을 포함합니다.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 프로젝트 파일 가져오기 – Aspose.Tasks 로드 옵션
url: /ko/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 파일 가져오기 – Aspose.Tasks 로드 옵션

## 소개

Aspose.Tasks for .NET은 Microsoft Project, Primavera 및 기타 형식의 **프로젝트 파일** 데이터를 쉽게 **가져올** 수 있게 해줍니다. 암호로 보호된 파일을 읽거나, 사용자 지정 인코딩을 설정하거나, 구문 분석 오류를 처리해야 할 경우에도, 라이브러리는 로드 옵션을 통해 세밀한 제어를 제공합니다. 이 튜토리얼에서는 가장 일반적인 시나리오를 단계별로 살펴보며 .NET 애플리케이션에서 **Microsoft Project 파일** 객체를 자신 있게 **로드**할 수 있도록 안내합니다.

## 빠른 답변
- **프로젝트 파일을 가져오는 기본 방법은 무엇인가요?** `Project` 생성자를 `LoadOptions` 인스턴스와 함께 사용합니다.  
- **암호로 보호된 파일을 열 수 있나요?** 예—`LoadOptions`의 `Password` 속성을 설정합니다.  
- **파일 인코딩을 어떻게 지정하나요?** `LoadOptions.Encoding`에 `Encoding` 객체를 할당합니다.  
- **오류 처리를 사용자 정의할 수 있나요?** 물론—`LoadOptions.ErrorHandler`에 대리자를 제공합니다.  
- **이 옵션을 Primavera 파일에도 사용할 수 있나요?** 예, `LoadOptions` 내부의 `PrimaveraReadOptions`를 통해 가능합니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. **Visual Studio** (또는 선호하는 .NET IDE).  
2. **Aspose.Tasks for .NET** – [웹사이트](https://releases.aspose.com/tasks/net/)에서 다운로드하세요.  
3. **C#** 구문 및 프로젝트 구조에 대한 기본 이해.

이제 설정이 완료되었으니, 필요한 네임스페이스를 가져옵시다.

## 네임스페이스 가져오기

C# 프로젝트에 다음 `using` 문을 추가하여 API 클래스를 사용할 수 있게 합니다:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## 로드 옵션으로 프로젝트 파일 가져오기

다음은 가장 흔한 로드 시나리오를 다루는 네 가지 실용적인 예제입니다.

### 단계 1: 암호로 보호된 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### 단계 2: 사용자 지정 옵션으로 Primavera 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### 단계 3: XER 파일 가져오기 시 **파일 인코딩 지정**

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### 단계 4: 사용자 지정 오류 처리로 Primavera 프로젝트 로드

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

이 단계들을 따라 하면 **프로젝트 파일** 데이터를 정확히 가져오고, 로드 프로세스를 필요에 맞게 조정하며, 애플리케이션을 견고하게 유지할 수 있습니다.

## 일반적인 문제 및 팁

- **잘못된 비밀번호** – `Password` 속성이 예외를 발생시킵니다; 로드하기 전에 자격 증명을 확인하세요.  
- **지원되지 않는 인코딩** – 지정한 코드 페이지가 대상 머신에 존재하는지 확인하세요 (`Encoding.GetEncoding(1251)`은 키릴 문자에 사용됩니다).  
- **Primavera 옵션 누락** – 작업 UID를 보존해야 하면 `PreserveUids = true`로 설정하세요; 그렇지 않으면 중복 ID가 나타날 수 있습니다.  
- **오류 처리기가 null 반환** – `null`을 반환하면 파서가 문제 요소를 건너뛰도록 신호를 보냅니다; 필요에 따라 맞춤 설정하세요.

## 자주 묻는 질문

**Q: Aspose.Tasks for .NET이 모든 버전의 Microsoft Project와 호환되나요?**  
A: 예, 다양한 Microsoft Project 버전을 지원하므로 오래된 MPP 파일부터 최신 형식까지 **Microsoft Project 파일**을 **로드**할 수 있습니다.

**Q: Aspose.Tasks for .NET을 다른 서드파티 라이브러리와 통합할 수 있나요?**  
A: 물론입니다. 이 라이브러리는 다른 .NET 패키지와 원활하게 작동하여 보고, UI, 데이터 액세스 프레임워크와 결합할 수 있습니다.

**Q: Aspose.Tasks for .NET이 문서 및 지원 리소스를 제공하나요?**  
A: 예, 포괄적인 [문서](https://reference.aspose.com/tasks/net/)를 참고하고 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 통해 지원을 받을 수 있습니다.

**Q: Aspose.Tasks for .NET에 대한 라이선스 옵션이 있나요?**  
A: 예, 무료 체험 및 임시 라이선스를 포함한 다양한 라이선스 옵션을 [Aspose.Tasks 웹사이트](https://purchase.aspose.com/buy)에서 확인할 수 있습니다.

**Q: Aspose.Tasks for .NET은 얼마나 자주 업데이트 및 새로운 기능이 출시되나요?**  
A: Aspose.Tasks는 정기적으로 업데이트되어 기능을 추가하고 성능을 개선하며 최신 Microsoft Project 릴리스와의 호환성을 유지합니다.

---

**마지막 업데이트:** 2026-03-08  
**테스트 환경:** Aspose.Tasks 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}