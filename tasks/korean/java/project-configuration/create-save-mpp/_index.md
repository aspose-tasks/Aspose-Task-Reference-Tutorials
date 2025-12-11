---
date: 2025-12-11
description: Aspose.Tasks for Java를 사용하여 mpp 파일을 생성하고 빈 MS Project 파일(MPP)을 저장하는 방법을
  배우세요. 프로젝트 관리 작업을 손쉽게 간소화하세요.
linktitle: Create and Save Empty Project in MPP Format with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MPP 파일 만들기 – Aspose.Tasks를 사용하여 빈 프로젝트를 MPP 형식으로 생성 및 저장
url: /ko/java/project-configuration/create-save-mpp/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용하여 MPP 형식의 빈 프로젝트 만들기 및 저장

## 소개
이 튜토리얼에서는 **Aspose.Tasks for Java**를 사용하여 **MPP 파일을 만드는 방법**을 배웁니다. 빈 MS Project 파일(MPP)을 생성하고 저장하는 간단한 과정을 단계별로 안내하므로, 프로젝트 파일을 빠르게 생성하고 Java 애플리케이션에 통합할 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** Aspose.Tasks for Java를 사용하여 빈 MPP 파일을 만들고 저장합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java(최신 버전).  
- **라이선스가 필요하나요?** 무료 체험판을 사용할 수 있으며, 프로덕션 사용 시 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **구현 시간은 얼마나 걸리나요?** 일반적으로 10분 이내.

## MPP 파일이란?
MPP 파일은 프로젝트 일정, 리소스 및 작업 계층 구조를 저장하는 Microsoft Project 고유 파일 형식입니다. 프로그래밍 방식으로 MPP 파일을 생성하면 프로젝트 계획 작성을 자동화하고, 다른 시스템과 통합하거나, 템플릿을 즉석에서 만들 수 있습니다.

## Aspose.Tasks for Java를 사용하는 이유
- **Microsoft Project가 필요 없음** – 모든 플랫폼에서 MPP 파일을 생성합니다.  
- **전체 기능 제공** – 작업, 리소스, 캘린더 등 다양한 요소를 지원합니다.  
- **고품질 호환성** – 생성된 파일을 Microsoft Project에서 정상적으로 열 수 있습니다.  

## 사전 요구 사항
시작하기 전에 다음 항목이 준비되어 있는지 확인하세요.

1. 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java 라이브러리를 다운로드하여 프로젝트 종속성에 추가합니다.  
3. Java 프로그래밍에 대한 기본 이해가 필요합니다.  

## Java로 MS Project 만들기 – 단계별 가이드

### 단계 1: 패키지 가져오기
Aspose.Tasks 기능을 제공하는 필수 클래스를 먼저 가져옵니다:

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

### 단계 2: 데이터 디렉터리 설정
생성된 프로젝트 파일을 저장할 폴더를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 원하는 절대 경로나 상대 경로로 교체하세요.

### 단계 3: Project 인스턴스 생성
새 `Project` 객체를 인스턴스화합니다. 이는 메모리 상에 빈 MS Project를 생성합니다:

```java
Project newProject = new Project();
```

### 단계 4: 프로젝트를 MPP로 저장
`save` 메서드를 사용해 프로젝트를 MPP 형식으로 디스크에 기록합니다—**save project as mpp**:

```java
newProject.save(dataDir + "project1.mpp", SaveFileFormat.Mpp);
```

`project1.mpp` 파일이 지정한 폴더에 생성됩니다.

### 단계 5: 확인 메시지 출력
작업이 성공했음을 알리는 확인 메시지를 출력합니다:

```java
System.out.println("Project file generated Successfully");
```

## 일반적인 문제와 해결 방법
- **디렉터리 경로 오류** – `dataDir`이 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하거나 `Paths.get`을 사용해 연결합니다.  
- **Aspose.Tasks JAR 누락** – 라이브러리가 클래스패스에 포함되어 있는지 확인합니다. Maven/Gradle 사용자는 적절한 의존성을 추가해야 합니다.  
- **라이선스 미설정** – 프로덕션 환경에서는 `License license = new License(); license.setLicense("Aspose.Tasks.lic");`와 같이 라이선스를 로드해야 합니다.

## 결론
이 단계를 따라 하면 **Aspose.Tasks for Java**를 사용해 프로그래밍 방식으로 **MPP 파일을 만드는 방법**을 익히게 됩니다. 이를 통해 프로젝트 계획 생성 자동화, 일정 데이터 통합, Microsoft Project에서 수동 입력을 피할 수 있습니다.

## FAQ
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 네, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 효과적으로 처리할 수 있는 강력한 기능을 제공합니다.  
### Q: Aspose.Tasks for Java의 체험 버전을 사용할 수 있나요?
A: 네, 웹사이트에서 무료 체험판을 받을 수 있습니다. 자세한 내용은 [여기](https://releases.aspose.com/)를 참고하세요.  
### Q: Aspose.Tasks for Java로 작업 및 리소스 속성을 커스터마이즈할 수 있나요?
A: 물론입니다. Aspose.Tasks for Java는 요구 사항에 맞게 작업 및 리소스 속성을 광범위하게 커스터마이즈할 수 있는 기능을 제공합니다.  
### Q: Aspose.Tasks for Java가 MPP 외에 다른 프로젝트 파일 형식을 지원하나요?
A: 네, Aspose.Tasks for Java는 XML, CSV 등 다양한 프로젝트 파일 형식을 지원합니다.  
### Q: Aspose.Tasks for Java에 대한 추가 지원은 어디서 받을 수 있나요?
A: Java 전용 지원 및 도움을 위해 Aspose.Tasks [포럼](https://forum.aspose.com/c/tasks/15)을 방문하세요.

## 자주 묻는 질문

**Q: 생성된 MPP 파일을 열려면 Microsoft Project가 설치되어 있어야 하나요?**  
A: 아니요, 파일은 Microsoft Project의 모든 버전이나 호환 뷰어에서 열 수 있습니다.

**Q: 저장하기 전에 작업이나 리소스를 추가할 수 있나요?**  
A: 예, `Project` 객체에 작업, 리소스, 캘린더 등을 추가한 뒤 `save`를 호출하면 됩니다.

**Q: 생성된 MPP 파일이 이전 버전 Project와 호환되나요?**  
A: Aspose.Tasks는 Microsoft Project 2007 이후 버전과 호환되는 파일을 생성합니다.

**Q: 프로젝트 시작 날짜를 사용자 지정하려면 어떻게 하나요?**  
A: 저장하기 전에 `newProject.setStartDate(java.util.Date)`를 호출하면 됩니다.

**Q: 어떤 라이선스 옵션이 있나요?**  
A: Aspose는 개발자, 사이트, OEM 라이선스를 제공하며 자세한 내용은 Aspose 웹사이트를 참고하세요.

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}