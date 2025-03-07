---
title: Aspose.Tasks에 업데이트된 리소스 데이터 쓰기
linktitle: Aspose.Tasks에 업데이트된 리소스 데이터 쓰기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 파일의 리소스 데이터를 손쉽게 업데이트하는 방법을 알아보세요.
weight: 21
url: /ko/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에 업데이트된 리소스 데이터 쓰기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 리소스 데이터를 업데이트하는 과정을 안내합니다. Aspose.Tasks는 시스템에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일을 조작할 수 있는 강력한 Java API입니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Aspose.Tasks for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. Java 프로그래밍에 대한 기본 지식.

## 패키지 가져오기

먼저 Java 코드에서 Aspose.Tasks를 사용하는 데 필요한 패키지를 가져와야 합니다. Java 파일에 다음 가져오기 문을 추가합니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 1단계: 데이터 디렉터리 설정

데이터 파일이 있는 디렉터리를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

## 2단계: 입력 및 출력 파일 지정

입력 MS 프로젝트 파일과 업데이트된 결과 파일의 경로를 정의합니다.

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // 업데이트할 RSC가 하나 있는 테스트 파일
String resultFile = dataDir + "OutputMPP.mpp"; // 테스트 프로젝트를 작성할 파일
```

## 3단계: 프로젝트 로드

 MS 프로젝트 파일을`Project` 물체:

```java
Project project = new Project(file);
```

## 4단계: 리소스 추가 및 속성 설정

프로젝트에 새 자원을 추가하고 표준 요율, 초과 근무 수당, 그룹 등의 속성을 설정합니다.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 5단계: 프로젝트 저장

수정된 리소스 데이터로 업데이트된 프로젝트를 저장합니다.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 결론

이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 리소스 데이터를 업데이트하는 방법을 보여주었습니다. 다음 단계를 수행하면 MS 프로젝트 파일의 리소스 정보를 프로그래밍 방식으로 효율적으로 조작할 수 있습니다.

## FAQ

### Q1: Aspose.Tasks for Java를 사용하여 동일한 프로젝트에서 여러 리소스를 업데이트할 수 있나요?

A1: 예, 여러 리소스를 반복하고 그에 따라 속성을 설정하여 업데이트할 수 있습니다.

### Q2: Aspose.Tasks는 MS Project 외에 다른 파일 형식을 지원합니까?

A2: 예, Aspose.Tasks는 XML, MPP 등을 포함한 다양한 파일 형식을 지원합니다.

### Q3: Aspose.Tasks는 다른 버전의 Java와 호환됩니까?

A3: Aspose.Tasks는 Java 버전 6 이상과 호환됩니다.

### Q4: Aspose.Tasks를 사용하여 MS 프로젝트 파일에 다른 작업을 수행할 수 있나요?

A4: 예, 작업, 리소스, 달력 읽기, 쓰기, 조작 등 광범위한 작업을 수행할 수 있습니다.

### Q5: Aspose.Tasks에 대한 추가 도움말이나 지원은 어디서 찾을 수 있나요?

 A5: 다음을 방문할 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 도움이나 문의사항이 있으면

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
