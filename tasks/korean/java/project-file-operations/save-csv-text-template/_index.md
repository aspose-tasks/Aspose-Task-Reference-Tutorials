---
date: 2025-12-21
description: Aspose.Tasks for Java를 사용하여 프로젝트를 템플릿으로 저장하고, MPP를 CSV로 내보내며, MPP를 텍스트로
  변환하는 방법을 알아보세요.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 프로젝트를 템플릿, CSV 및 텍스트로 저장
url: /ko/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트를 템플릿, CSV, 텍스트로 저장하기 (Aspose.Tasks)

## 소개
이 튜토리얼에서는 **프로젝트를 템플릿으로 저장하는 방법**과 Aspose.Tasks for Java 라이브러리를 사용하여 Microsoft Project(MPP) 파일을 CSV 및 일반 텍스트 형식으로 내보내는 방법을 알아봅니다. 재사용 가능한 프로젝트 템플릿을 만들거나, 분석을 위한 CSV 보고서를 생성하거나, 통합을 위한 간단한 텍스트 추출물을 만들고자 할 때, 이 단계들을 따라 하면 빠르고 효율적으로 작업을 수행할 수 있습니다.

## 빠른 답변
- **MPP를 CSV로 내보낼 수 있나요?** 예 – `project.save(..., SaveFileFormat.CSV)`를 사용합니다.  
- **텍스트로 내보내는 방법은?** `SaveFileFormat.TEXT`로 저장합니다.  
- **“프로젝트를 템플릿으로 저장”은 무엇을 하나요?** 실제 값과 기준값을 제거한 `.mpt` 파일을 생성하여 재사용이 가능하도록 합니다.  
- **라이선스가 필요합니까?** 체험판을 사용할 수 있지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상을 지원합니다.

## “프로젝트를 템플릿으로 저장”이란?
프로젝트를 템플릿(`.mpt`)으로 저장하면 구조, 작업 계층 및 리소스 할당은 유지하면서 실제 시작/종료 날짜와 기준선 데이터를 제거합니다. 이를 통해 표준 프로젝트 레이아웃을 여러 새로운 프로젝트에 재사용할 수 있는 템플릿이 만들어집니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
Aspose.Tasks는 Microsoft Project를 직접 설치하지 않아도 Microsoft Project 파일을 조작할 수 있게 해줍니다. **MPP 내보내기**, **텍스트 내보내기**, **MPP를 CSV로 변환** 등을 순수 Java 코드만으로 수행할 수 있어 서버‑사이드 자동화, CI 파이프라인, 데스크톱 유틸리티 등에 최적입니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하세요:

1. Java Development Kit (JDK) 8 이상이 설치되어 있어야 합니다.  
2. 프로젝트에 Aspose.Tasks for Java 라이브러리를 추가합니다. 라이브러리는 [here](https://releases.aspose.com/tasks/java/)에서 다운로드할 수 있습니다.  
3. Java 문법 및 Maven/Gradle 프로젝트 설정에 대한 기본적인 이해가 필요합니다.

## 패키지 가져오기
Java 소스 파일에 필요한 클래스를 먼저 가져옵니다:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## 프로젝트를 CSV로 저장 (MPP를 CSV로 내보내기)
MPP 파일을 CSV로 내보내면 Excel이나 BI 도구에서 데이터 분석이 용이합니다.

### 단계 1: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 단계 2: CSV로 저장
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## 프로젝트를 텍스트로 저장 (텍스트 내보내기)
작업, 리소스 또는 할당 정보를 일반 텍스트 형태로 저장하려면 프로젝트를 텍스트 파일로 저장합니다.

### 단계 1: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 단계 2: 텍스트로 저장
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## 프로젝트를 템플릿으로 저장 (Java에서 프로젝트 템플릿 만들기)
재사용 가능한 템플릿을 만들면 실제 날짜와 기준선을 제거하고 새로운 프로젝트를 위한 깔끔한 골격을 제공합니다.

### 단계 1: 프로젝트 로드
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 단계 2: 템플릿 옵션 설정
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### 단계 3: 템플릿으로 저장
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 일반적인 문제 및 팁
- **파일을 찾을 수 없음:** `YourProject.mpp` 경로가 올바른지 확인하거나 절대 경로를 사용하세요.  
- **라이선스 예외:** 유효한 라이선스가 없으면 라이브러리가 평가 모드로 실행되어 워터마크가 추가될 수 있습니다. 코드 초기에 라이선스를 적용하세요 (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **대형 프로젝트:** 매우 큰 MPP 파일의 경우 JVM 힙 크기를 늘려(`-Xmx2g`) `OutOfMemoryError`를 방지하세요.

## 결론
우리는 **프로젝트를 템플릿으로 저장하는 방법**과 **MPP를 CSV로 내보내는 방법**, **MPP를 텍스트로 변환하는 방법**을 Aspose.Tasks for Java를 사용해 살펴보았습니다. 이러한 기능을 통해 프로젝트 데이터 처리를 자동화하고, 재사용 가능한 템플릿을 생성하며, 프로젝트 정보를 다른 시스템에 통합할 수 있습니다—Microsoft Project를 설치할 필요 없이 말이죠.

## FAQ
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 파일을 처리할 수 있나요?
A: 물론입니다! Aspose.Tasks for Java는 다양한 복잡도의 프로젝트를 손쉽게 처리하며, Microsoft Project 파일 형식에 대한 포괄적인 지원을 제공합니다.  
### Q: Aspose.Tasks for Java 체험판을 사용할 수 있나요?
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks for Java 무료 체험판을 받을 수 있습니다.  
### Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?
A: Aspose.Tasks 관련 문의는 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 도움을 받을 수 있습니다.  
### Q: Aspose.Tasks for Java 임시 라이선스를 구매할 수 있나요?
A: 예, [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 구매하여 라이브러리의 전체 기능을 평가할 수 있습니다.  
### Q: Aspose.Tasks for Java는 다양한 운영 체제와 호환되나요?
A: 예, Aspose.Tasks for Java는 Windows, macOS, Linux 등 다양한 운영 체제에서 호환됩니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** Aspose.Tasks for Java 24.12 (latest)  
**작성자:** Aspose  

---