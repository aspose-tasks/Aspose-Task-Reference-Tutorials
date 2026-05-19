---
date: 2026-01-15
description: Aspose.Tasks for Java를 사용하여 프로젝트에 리소스를 추가하고, 리소스 데이터를 업데이트하며, 프로젝트를 MPP
  파일로 저장하는 방법을 배웁니다.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 프로젝트에 리소스 추가
url: /ko/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java를 사용하여 프로젝트에 리소스 추가

## Introduction
이 실습 튜토리얼에서는 Aspose.Tasks Java API를 사용하여 **프로젝트에 리소스를 추가하는 방법**을 프로그래밍 방식으로 배우게 됩니다. 기존 MS Project XML 파일을 로드하고, 새로운 리소스를 삽입하고, 속성을 업데이트한 뒤, 최종적으로 **프로젝트를 MPP 형식으로 저장**하는 과정을 단계별로 안내합니다. 튜토리얼을 마치면 Java 기반 보고서 또는 자동화 도구에 손쉽게 적용할 수 있는 명확하고 재사용 가능한 패턴을 얻게 됩니다.

## Quick Answers
- **‘프로젝트에 리소스 추가’가 의미하는 것은?** Microsoft Project 파일 내부에 새로운 리소스 항목(인력, 장비, 자재 등)을 생성하는 것입니다.  
- **어떤 라이브러리를 사용하나요?** Aspose.Tasks for Java – Microsoft Project를 설치할 필요가 없습니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **XML을 MPP로 변환할 수 있나요?** 예, XML 파일을 로드한 뒤 `project.save(...)`를 사용해 **프로젝트를 MPP로 저장**하면 됩니다.  
- **필요한 Java 버전은?** Java 6 이상 (Java 8 이상 권장).

## What is “add resource to project”?
프로젝트에 리소스를 추가한다는 것은 MS Project 파일의 Resources 테이블에 새로운 행을 삽입하는 것을 의미합니다. 이 행에는 이름, 비용 요율, 그룹 및 작업이 이후에 참조할 수 있는 사용자 정의 필드와 같은 세부 정보가 저장됩니다.

## Why use Aspose.Tasks for Java?
- **Microsoft Project 의존성 없음** – 모든 OS 및 CI 서버에서 동작합니다.  
- **완전한 충실도** – 형식 변환 시 모든 고유 Project 기능을 보존합니다.  
- **풍부한 API** – 작업, 리소스, 캘린더 등을 읽고, 쓰고, 조작할 수 있습니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

1. Java Development Kit (JDK) 8 이상이 설치되어 있어야 합니다.  
2. Aspose.Tasks for Java 라이브러리 – [here](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. Java 문법 및 Maven/Gradle 프로젝트 설정에 대한 기본적인 이해.

## Import Packages
Java 소스 파일에 필요한 Aspose.Tasks 클래스를 추가합니다:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory
소스 XML 파일과 결과 MPP 파일이 저장될 위치를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files
변환하려는 XML 파일(**XML을 MPP로 변환**)과 새로운 리소스를 포함할 대상 MPP 파일을 지정합니다:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project
XML 소스에서 `Project` 객체를 생성합니다:

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes
여기서 **프로젝트에 리소스를 추가**하고 요율 및 그룹을 설정합니다:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*팁:* `add` 호출을 루프 안에서 반복하면 한 번에 **여러 리소스를 업데이트**할 수 있습니다.

## Step 5: Save the Project
마지막으로, 변경 사항을 저장하기 위해 **프로젝트를 MPP로 저장**합니다:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion
이제 **프로젝트에 리소스를 추가하는 방법**을 배우고, 속성을 업데이트하며, Aspose.Tasks for Java를 사용해 **프로젝트를 MPP로 저장**하는 방법을 익혔습니다. 이 방법은 자동화된 보고 파이프라인, 대량 리소스 가져오기, 또는 데스크톱 애플리케이션 없이 MS Project 파일을 조작해야 하는 모든 상황에 이상적입니다.

## Frequently Asked Questions

**Q1: Aspose.Tasks for Java를 사용해 동일한 프로젝트에서 여러 리소스를 업데이트할 수 있나요?**  
A: 예, `project.getResources()`를 순회하거나 `add`를 반복 호출하여 각 리소스의 필드를 필요에 따라 설정하면 됩니다.

**Q2: Aspose.Tasks가 MS Project 외에 다른 파일 형식을 지원하나요?**  
A: 물론입니다 – XML, MPP, MPX, Primavera 등 다양한 형식을 지원합니다.

**Q3: Aspose.Tasks는 다양한 Java 버전과 호환되나요?**  
A: 이 라이브러리는 Java 6 이상에서 작동하며, 최상의 성능을 위해 Java 8 이상을 강력히 권장합니다.

**Q4: Aspose.Tasks를 사용해 MS Project 파일에서 다른 작업을 수행할 수 있나요?**  
A: 예, 작업, 캘린더, 할당, 사용자 정의 필드를 읽고/쓸 수 있으며 보고서 생성도 가능합니다.

**Q5: Aspose.Tasks에 대한 추가 도움이나 지원을 어디서 찾을 수 있나요?**  
A: 커뮤니티 지원 및 공식 지원을 위해 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하십시오.

---

**마지막 업데이트:** 2026-01-15  
**테스트 환경:** Aspose.Tasks for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}