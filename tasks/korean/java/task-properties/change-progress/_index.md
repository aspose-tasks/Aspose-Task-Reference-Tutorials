---
date: 2026-01-28
description: Aspose.Tasks, 강력한 Java 프로젝트 관리 라이브러리를 사용하여 MPP 프로젝트를 Java로 생성하고 작업 진행률을
  수정하는 방법을 배워보세요. 지금 단계별 가이드를 따라하세요!
linktitle: Change Progress of Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MPP 프로젝트 Java 만들기 – Aspose.Tasks로 작업 진행률 변경
url: /ko/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP 프로젝트 Java 만들기 – Aspose.Tasks로 작업 진행률 변경

## 소개
현대 **java project management**에서는 **create mpp project java** 파일을 생성하고 작업 진행 상황을 최신 상태로 유지하는 것이 제시간에 전달하기 위해 필수적입니다. Aspose.Tasks for Java는 강력한 **java project management library** 역할을 하며, Microsoft Project 파일을 구축, 수정 및 보고할 수 있는 깔끔한 API를 제공합니다. 이 튜토리얼에서는 MPP 프로젝트를 생성하고, 작업을 추가하며, 진행 상황을 업데이트하는 전체 과정을 명확하고 대화형 설명과 함께 안내합니다.

## 빠른 답변
- **“create mpp project java”가 무엇을 의미합니까?**  
  이는 Java 코드를 사용하여 Microsoft Project (.mpp) 파일을 프로그래밍 방식으로 생성하는 것을 의미합니다.  
- **어떤 라이브러리가 이를 도와줍니까?**  
  Aspose.Tasks for Java, 전용 **java project management library**입니다.  
- **작업 진행률을 설정하는 데 필요한 코드 라인은 몇 줄입니까?**  
  프로젝트가 인스턴스화된 후 10줄 미만입니다.  
- **프로덕션 사용을 위해 라이선스가 필요합니까?**  
  예, 상업용 라이선스가 필요합니다; 무료 체험판을 사용할 수 있습니다.  
- **이 코드를 모든 Java IDE에서 실행할 수 있나요?**  
  물론입니다 – Java 8 이상을 지원하는 모든 IDE에서 작동합니다.

## “create mpp project java”란 무엇인가요?
Java에서 MPP 프로젝트를 만든다는 것은 코드를 사용하여 Microsoft Project 파일(`.mpp`)을 생성하는 것을 의미합니다. 이 파일은 Microsoft Project 또는 기타 호환 도구에서 열 수 있으며, 자동 일정 생성, 대량 작업 생성 및 다른 비즈니스 시스템과의 통합을 가능하게 합니다.

## 왜 Aspose.Tasks를 java project management library로 사용하나요?
- **Full API coverage** – 프로젝트 생성부터 상세 작업 조작까지 모두 지원합니다.  
- **No external dependencies** – 표준 Java만으로 바로 사용할 수 있습니다.  
- **Cross‑platform** – Windows, Linux, macOS에서 실행됩니다.  
- **Rich reporting** – 이해관계자와의 커뮤니케이션을 위해 PDF, PNG 또는 HTML로 내보낼 수 있습니다.

## 사전 요구 사항
1. **Java Development Environment** – JDK 8 이상이 설치되고 구성되어 있어야 합니다.  
2. **Aspose.Tasks for Java Library** – 공식 사이트에서 다운로드: [link](https://releases.aspose.com/tasks/java/).  
3. **Document Directory** – 생성된 `.mpp` 파일이 저장될 머신상의 폴더.

## 패키지 가져오기
먼저 필요한 Aspose.Tasks 클래스를 가져옵니다. 이 스니펫은 환경을 설정하고 이후 50 % 진행률을 가진 작업을 추가합니다.

```java
import com.aspose.tasks.*;
```

## 단계별 가이드

### 단계 1: Java 프로젝트 설정
새 Maven 또는 Gradle 프로젝트를 만들고 Aspose.Tasks JAR를 클래스패스에 추가합니다. 이렇게 하면 `Project`, `Task` 및 관련 클래스를 사용할 수 있습니다.

### 단계 2: Document Directory 정의
프로젝트 파일이 저장될 위치를 지정합니다. 자리표시자를 실제 머신 경로로 교체하세요.

```java
String dataDir = "Your Document Directory";
```

### 단계 3: 새 프로젝트 생성 (create mpp project java)
`Project` 객체를 인스턴스화합니다. 파일이 존재하지 않으면 Aspose.Tasks가 새로운 `.mpp` 파일을 생성합니다.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 단계 4: 프로젝트에 작업 추가 (add task project)
루트 작업의 자식 컬렉션을 사용해 새 작업을 삽입합니다. 이는 라이브러리의 **add task project** 기능을 보여줍니다.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### 단계 5: 작업 진행률 설정
작업의 퍼센트 완료 값을 업데이트합니다. `percent` 헬퍼는 정수를 라이브러리 내부 표현으로 변환합니다.

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### 단계 6: 업데이트된 진행률 표시
콘솔에 현재 진행률을 출력하여 변경이 적용됐는지 확인합니다.

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

이 단계를 따라 하면 **Created an MPP project in Java**, 작업을 추가하고 진행률을 변경했으며, 모두 Aspose.Tasks를 사용한 것입니다.

## 일반적인 문제 및 해결 방법
- **FileNotFoundException** – `dataDir`이 파일 구분자(`/` 또는 `\`)로 끝나는지, 디렉터리가 존재하는지 확인하세요.  
- **LicenseException** – 프로덕션 사용 시 `Project` 객체를 만들기 전에 Aspose.Tasks 라이선스를 로드하세요.  
- **Incorrect Percent Value** – `percent` 메서드는 0~100 사이의 값을 기대합니다; 범위를 벗어나면 예외가 발생합니다.

## 자주 묻는 질문

### Aspose.Tasks는 모든 Java 개발 환경과 호환됩니까?
문서에 있는 설치 지침을 따라 호환성을 확인하세요.

### 프로젝트 내 여러 작업의 진행률을 추적할 수 있나요?
모니터링하려는 각 작업에 대해 동일한 단계를 반복하면 됩니다.

### Aspose.Tasks for Java의 체험판이 있나요?
무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Tasks for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?
포괄적인 문서는 [여기](https://reference.aspose.com/tasks/java/)에서 확인하세요.

### Aspose.Tasks for Java 임시 라이선스는 어떻게 얻을 수 있나요?
[임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)를 방문하세요.

## 추가 FAQ (AI 최적화)

**Q: MPP 파일을 만들기 위해 필요한 Aspose.Tasks 버전은?**  
A: 2023‑2025 사이의 최신 버전이면 `Project` 생성이 지원됩니다; 버그 수정을 위해 항상 최신 버전을 사용하세요.

**Q: 진행률을 업데이트한 후 프로젝트를 PDF로 내보낼 수 있나요?**  
A: 예, 진행률을 설정한 뒤 `project.save("output.pdf", SaveFileFormat.PDF);`를 사용하면 됩니다.

**Q: 여러 작업의 진행률을 일괄 업데이트할 수 있나요?**  
A: `project.getRootTask().getChildren()`을 순회하면서 각 작업의 `Tsk.PERCENT_COMPLETE`를 설정하면 됩니다.

**Q: 라이브러리가 리소스 할당을 자동으로 처리하나요?**  
A: 리소스는 명시적으로 추가해야 하며, 작업 진행률은 리소스 할당에 영향을 주지 않습니다.

**Q: 생성된 MPP 파일에 비밀번호를 설정하려면?**  
A: 파일을 저장하기 전에 `project.setPassword("yourPassword");`를 호출하세요.

## 결론
Aspose.Tasks, 전용 **java project management library**를 사용하면 Java에서 MPP 프로젝트를 만들고 작업 진행률을 관리하는 것이 간단합니다. 이 단계를 마스터하면 일정 자동 생성, 이해관계자에게 최신 정보 제공, 프로젝트 데이터를 대규모 엔터프라이즈 워크플로에 통합할 수 있습니다.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}