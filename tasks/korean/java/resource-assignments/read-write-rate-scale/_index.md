---
title: Aspose.Tasks의 리소스 할당에 대한 읽기 및 쓰기 비율 척도
linktitle: Aspose.Tasks의 리소스 할당에 대한 읽기 및 쓰기 비율 척도
second_title: Aspose.Tasks 자바 API
description: 이 포괄적인 튜토리얼을 통해 Java용 Aspose.Tasks에서 자원 할당 비율 규모를 효과적으로 관리하는 방법을 알아보세요.
weight: 20
url: /ko/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks의 리소스 할당에 대한 읽기 및 쓰기 비율 척도

## 소개
이 튜토리얼에서는 Microsoft Project 파일을 프로그래밍 방식으로 작업하기 위한 강력한 라이브러리인 Aspose.Tasks for Java를 사용하여 자원 할당 비율 척도를 관리하는 방법을 살펴보겠습니다. 다음 단계를 수행하면 Java 애플리케이션에서 리소스 할당에 대한 속도 범위 설정을 효과적으로 조작할 수 있습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 사용하려면 필요한 패키지를 가져와야 합니다. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## 1단계: 프로젝트 설정
Java 프로젝트를 설정하여 시작하고 종속 항목에 Aspose.Tasks 라이브러리를 포함하세요.
## 2단계: 프로젝트 파일 로드
작업하려는 프로젝트 파일을 Java 애플리케이션에 로드합니다.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3단계: 작업 추가
프로젝트에 새 작업을 추가합니다.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## 4단계: 리소스 정의
물질적 자원과 비물질적 자원을 정의하고 그 유형을 지정합니다.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## 5단계: 작업에 자원 할당
이전에 정의한 자원을 비율 척도 유형과 함께 작업에 할당합니다.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## 6단계: 프로젝트 저장
수정된 자원 할당으로 프로젝트를 저장합니다.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## 7단계: 자원 할당 검색
저장된 프로젝트를 다시 로드하고 리소스 할당을 검색하여 비율 척도 설정을 확인합니다.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 결론
Aspose.Tasks for Java에서 자원 할당 비율 척도를 관리하는 것은 효과적인 프로젝트 관리에 매우 중요합니다. 이 단계별 가이드를 따르면 Java 애플리케이션에서 리소스 할당에 대한 속도 범위 설정을 원활하게 조작할 수 있습니다.
## FAQ
### Q1: Java IDE에서 Aspose.Tasks for Java를 사용할 수 있나요?
A: 예, Aspose.Tasks for Java는 IntelliJ IDEA, Eclipse 및 NetBeans를 포함한 모든 주요 Java IDE와 호환됩니다.
### Q2: Aspose.Tasks는 MPP 외에 다른 파일 형식을 지원합니까?
A: 예, Aspose.Tasks는 MPP, XML 및 HTML을 포함한 다양한 파일 형식을 지원합니다.
### Q3: Aspose.Tasks는 기업 수준의 프로젝트 관리에 적합합니까?
A: 물론 Aspose.Tasks는 모든 규모의 프로젝트 관리를 위한 포괄적인 기능을 제공하므로 기업 수준의 프로젝트 관리에 적합합니다.
### Q4: 요율 범위를 넘어서 리소스 할당을 사용자 정의할 수 있습니까?
A: 예, Aspose.Tasks는 비용, 작업 및 기간 조정을 포함하여 리소스 할당을 사용자 정의하기 위한 광범위한 기능을 제공합니다.
### Q5: Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?
 A: 예, Aspose.Tasks 포럼에서 지원을 찾고 다른 사용자와 상호 작용할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
