---
date: 2025-12-25
description: Aspose Tasks Java 튜토리얼을 탐색하여 MS Project 파일의 프로젝트 버전을 결정하는 방법을 배워보세요.
  단계별 가이드와 코드 예제가 포함되어 있습니다.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose Tasks Java 튜토리얼: MS Project 버전 확인'
url: /ko/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java 튜토리얼: MS Project 버전 확인

## 소개
이 **aspose tasks java tutorial**에서는 Aspose.Tasks Java 라이브러리를 사용하여 Microsoft Project 파일의 버전을 프로그래밍 방식으로 찾는 방법을 알아봅니다. 파일 버전을 알면 호환성 문제를 처리하고, 마이그레이션 정책을 적용하거나, 단순히 어떤 Project 릴리스가 파일을 생성했는지 기록할 수 있습니다. 환경 설정부터 버전 및 마지막 저장 날짜 출력까지 모든 단계를 차례대로 안내하므로 이 검사를 Java 애플리케이션에 자신 있게 통합할 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** Aspose.Tasks for Java를 사용하여 MS Project 파일 버전을 결정합니다.  
- **Microsoft Project를 설치해야 하나요?** 아니요, Aspose.Tasks는 독립적으로 작동합니다.  
- **지원되는 파일 형식은 무엇인가요?** XML 기반 Project 파일(MPP, XML 등).  
- **구현에 얼마나 걸리나요?** 기본 검사는 약 5‑10분 정도 소요됩니다.  
- **라이선스가 필요합니까?** 평가용으로는 무료 체험판으로 충분하지만, 프로덕션에서는 라이선스가 필요합니다.

## Aspose Tasks Java 튜토리얼이란?
**aspose tasks java tutorial**은 Java 프로젝트에서 Aspose.Tasks API를 사용하는 실습 가이드를 제공합니다. Microsoft Project 자체 없이도 Microsoft Project 데이터를 읽고, 수정하고, 분석하는 방법을 보여줍니다.

## 프로젝트 버전을 확인하기 위해 Aspose.Tasks를 사용하는 이유는?
- **Microsoft Project에 대한 의존성 없음** – 서버 측 자동화에 최적입니다.  
- **정확한 버전 메타데이터** – 정확한 SAVE_VERSION 및 LAST_SAVED 필드를 가져옵니다.  
- **크로스 플랫폼** – Java를 지원하는 모든 OS에서 작동합니다.  
- **고성능** – 배치 처리에 적합한 가벼운 파싱을 제공합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Java Development Kit (JDK)** – 최신 JDK(8 이상) 중 하나.  
2. **Aspose.Tasks for Java JAR** – [website](https://releases.aspose.com/tasks/java/)에서 다운로드하고 프로젝트 클래스패스에 추가합니다.  
3. **MS Project 파일** – 검사하려는 XML 기반 Project 파일(예: `input.xml`).  

> **팁:** 경로 처리를 간소화하려면 Project 파일을 전용 `data` 폴더에 보관하십시오.

## 패키지 가져오기
먼저 필수 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: 프로젝트 디렉터리 설정
Project 파일이 들어 있는 폴더를 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 `input.xml`이 위치한 절대 경로나 상대 경로로 교체하십시오.

## Step 2: 프로젝트 로드
`Project` 인스턴스를 XML 파일을 로드하여 생성합니다.

```java
Project project = new Project(dataDir + "input.xml");
```

파일 이름이 다르면 `"input.xml"`을 해당 이름으로 수정하십시오.

## Step 3: 프로젝트 버전 확인 방법
버전 정보와 마지막 저장 타임스탬프를 가져옵니다.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

`Prj.SAVE_VERSION` 속성은 파일을 저장한 Microsoft Project 버전을 나타냅니다(예: Project 2010은 12). `Prj.LAST_SAVED`는 가장 최근 저장 작업의 날짜/시간을 반환합니다.

## Step 4: 결과 표시
버전 확인이 성공적으로 완료되었음을 알립니다.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## 일반적인 문제와 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | 파일을 찾을 수 없거나 경로가 올바르지 않음 | `dataDir`와 파일 이름을 확인하십시오; 테스트 시 절대 경로를 사용하십시오. |
| Unexpected version number (e.g., 0) | Project XML 파일이 아닌 파일을 로드함 | 파일이 유효한 Microsoft Project 파일(MPP/XML)인지 확인하십시오. |
| License exception | 프로덕션 환경에서 유효한 라이선스 없이 체험판을 사용함 | Aspose.Tasks 라이선스를 적용하십시오(`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 자주 묻는 질문

### Q: 다른 프로그래밍 언어와 함께 Aspose.Tasks를 사용할 수 있나요?
A: 예, Aspose.Tasks는 .NET, Java, C++ 등 여러 언어를 지원합니다.

### Q: 대규모 프로젝트에 Aspose.Tasks가 적합한가요?
A: 예, Aspose.Tasks는 어떤 규모의 프로젝트든 쉽게 처리하도록 설계되었습니다.

### Q: Aspose.Tasks를 사용해 프로젝트 데이터를 맞춤화할 수 있나요?
A: 예, Aspose.Tasks를 사용하면 프로젝트 데이터를 조작하고, 작업, 리소스 등을 수정할 수 있습니다.

### Q: Aspose.Tasks에 Microsoft Project 설치가 필요합니까?
A: 아니요, Aspose.Tasks는 독립적으로 작동하며 Microsoft Project 설치가 필요하지 않습니다.

### Q: Aspose.Tasks에 대한 기술 지원이 제공되나요?
A: 예, Aspose.Tasks 포럼에서 기술 지원을 받을 수 있습니다([here](https://forum.aspose.com/c/tasks/15)).

### Additional Q&A

**Q: 다른 프로젝트 속성(예: author, company)을 어떻게 가져오나요?**  
A: 버전 예제와 마찬가지로 `project.get(Prj.AUTHOR)` 또는 `project.get(Prj.COMPANY)`를 사용하십시오.

**Q: MPP 파일(바이너리 형식)의 버전을 확인할 수 있나요?**  
A: 예, Aspose.Tasks는 `.mpp` 파일을 직접 로드할 수 있으며 동일한 `Prj.SAVE_VERSION` 속성이 작동합니다.

**Q: 오래된 프로젝트 파일을 프로그래밍 방식으로 최신 버전으로 업그레이드할 방법이 있나요?**  
A: 오래된 파일을 로드한 뒤 `project.save("newfile.mpp", SaveFileFormat.MPP);` 로 저장하면 됩니다 – Aspose.Tasks는 기본적으로 최신 형식으로 저장합니다.

## 결론
이제 **aspose tasks java tutorial**을 마쳤으며, Aspose.Tasks for Java를 사용해 MS Project 파일의 **프로젝트 버전 확인 방법**을 보여주었습니다. 이 코드를 더 큰 자동화 워크플로, 보고 도구 또는 마이그레이션 유틸리티에 통합하여 다루는 Project 버전을 정확히 알 수 있도록 하십시오.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}