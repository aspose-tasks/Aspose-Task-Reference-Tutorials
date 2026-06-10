---
date: 2026-06-10
description: Aspose.Tasks for Java를 사용하여 리소스 할당에 대한 비율을 읽고 비율 스케일을 쓰는 방법을 배웁니다. 자재
  리소스, 다양한 형식 및 대규모 프로젝트를 지원합니다.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Aspose.Tasks에서 리소스 할당에 대한 비율 스케일 읽기 및 쓰기
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 리소스 할당에 대한 비율 스케일을 읽고 쓰는 방법
url: /ko/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 리소스 할당에 대한 비율 스케일 읽기 및 쓰기 방법

이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 리소스 할당에 대한 **비율을 읽는 방법** 스케일 설정을 조정하는 방법을 알아봅니다. 스케줄러, 보고 도구를 구축하거나 프로젝트 업데이트를 자동화하려는 경우, 비율 스케일 조작을 마스터하면 물자 및 작업 리소스에 대한 세밀한 제어가 가능합니다.

## 빠른 답변
`ResourceAssignment`는 작업과 리소스를 연결하고 할당‑특정 데이터를 보유합니다.  
`Asn`은 `RATE_SCALE`을 포함한 할당 필드에 대한 상수를 포함합니다.  
`RateScaleType` 열거형은 비율 스케일링에 사용할 수 있는 시간 단위를 나열합니다.  

- **비율 처리를 위한 주요 클래스는 무엇입니까?** `ResourceAssignment`와 `Asn.RATE_SCALE` 속성.  
- **스케일 옵션을 정의하는 열거형은 무엇입니까?** `RateScaleType` (Day, Week, Month 등).  
- **샘플을 실행하려면 라이선스가 필요합니까?** 무료 평가 라이선스로 테스트가 가능하며, 상용 라이선스는 프로덕션에 필요합니다.  
- **저장 후 스케일을 변경할 수 있나요?** 예 – 프로젝트를 다시 로드하고 `Asn.RATE_SCALE`을 수정하면 됩니다.  
- **지원 IDE는?** IntelliJ IDEA, Eclipse, NetBeans 등 모든 Java IDE에서 코드를 컴파일할 수 있습니다.

## 리소스 할당에 대한 비율 스케일을 읽는 방법

프로젝트를 로드하고 원하는 `ResourceAssignment`를 찾은 다음 `getRateScale()`을 호출합니다 – 이 메서드는 비율이 일, 주, 월 또는 다른 단위별로 적용되는지를 나타내는 `RateScaleType` 값을 반환합니다. 응답은 즉시 제공되며 API 호출 두 번만 필요하므로 감사 스크립트나 UI 표시용으로 이상적입니다.

## 리소스 할당에 대한 비율 스케일을 쓰는 방법

`ResourceAssignment` 객체를 생성하거나 가져온 후, 해당 객체의 `Asn.RATE_SCALE` 속성을 원하는 `RateScaleType`(예: `RateScaleType.Week`)으로 설정하고 프로젝트를 저장합니다. 이 단일 속성 변경으로 비용 계산이 자동으로 업데이트되며 모든 지원 파일 형식에 걸쳐 지속됩니다. 스케일을 설정한 후에는 새로운 시간 단위를 반영하도록 리소스의 표준 요금 또는 초과 근무 요금을 조정해야 할 수도 있어, 비용 계산의 정확성을 유지할 수 있습니다.

## 비율 스케일이란?

비율 스케일은 리소스의 비용 비율이 적용되는 시간 단위(일, 주, 월 등)를 결정합니다. 스케일을 조정하면 물자 소비나 노동 노력을 정확하게 모델링할 수 있습니다. 예를 들어, 스케일을 Week(주)로 설정하면 비용 비율이 주당 비용으로 해석되며, 작업의 총 비용은 리소스가 할당된 주 수를 기준으로 계산됩니다.

## 왜 비율 스케일을 읽고 쓰나요?

현재 스케일을 읽으면 기존 일정에 대한 감사를 수행할 수 있고, 새로운 스케일을 쓰면 리소스를 프로젝트의 청구 또는 소비 정책에 맞출 수 있습니다. 이는 특히 **물자 리소스** 비용을 정의하거나 비표준 작업 캘린더에 대해 **스케일을 설정**해야 할 때 유용합니다.

## 사전 요구 사항
시작하기 전에 다음 사전 요구 사항을 확인하십시오:
1. **Java Development Environment** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java Library** – 라이브러리를 [here](https://releases.aspose.com/tasks/java/)에서 다운로드하고 설치하십시오.

## 패키지 가져오기
`ResourceAssignment` 클래스는 작업과 리소스 간의 연결을 나타내며, `RateScaleType`은 비율에 사용할 수 있는 시간 단위를 열거합니다. 코딩을 시작하기 전에 필요한 Aspose.Tasks 클래스를 가져오십시오.  

`Project`는 Microsoft Project 파일을 로드하고 저장하는 주요 객체입니다.  
`Resource`는 작업 또는 물자와 같은 프로젝트 리소스를 정의합니다.  
`ResourceType` 열거형은 리소스가 작업인지 물자인지를 지정합니다.  
`Task`는 프로젝트 일정의 작업 항목을 나타냅니다.  
`SaveFileFormat` 열거형은 프로젝트 저장 시 출력 형식을 정의합니다.

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

## 단계 1: Java 프로젝트 설정
Maven 또는 Gradle 프로젝트를 생성하고 Aspose.Tasks JAR를 클래스패스에 추가하십시오. 이 단계는 컴파일러가 가져온 클래스를 찾을 수 있도록 보장합니다.

## 단계 2: 프로젝트 파일 로드
작업하려는 기존 Microsoft Project 파일을 로드합니다.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 단계 3: 작업 추가
나중에 리소스 할당을 받을 새 작업을 생성합니다.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 단계 4: 리소스 정의
여기서는 **물자 리소스**와 일반 작업 리소스를 **정의**합니다. 물자 유형 리소스에 `ResourceType.Material`을 사용한 것을 확인하십시오.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 단계 5: 작업에 리소스 할당
이제 `RateScaleType.Week`를 사용하여 **작업에 리소스를 할당**하고 **스케일 설정 방법**을 지정합니다. 이는 비율 스케일을 읽고 쓰는 두 가지를 모두 보여줍니다.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 단계 6: 프로젝트 저장
변경 사항을 새 파일에 저장하여 나중에 저장된 비율 스케일을 확인할 수 있도록 합니다.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 단계 7: 리소스 할당 검색
저장된 프로젝트를 다시 로드하고 **비율** 스케일을 읽어 올바르게 기록되었는지 확인합니다.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 일반적인 함정 및 팁
- **UID 불일치** – UID로 할당을 검색할 때, 생성 시 할당된 UID 값과 일치하는지 확인하십시오.  
- **잘못된 리소스 유형** – 작업 리소스에 `ResourceType.Material`을 사용하면 비율 계산이 예상치 못하게 동작합니다.  
- **저장 형식** – 비율 스케일과 같은 사용자 정의 필드를 보존하려면 항상 `SaveFileFormat.Mpp`(또는 다른 지원 형식)으로 저장하십시오.  
- **대형 프로젝트** – Aspose.Tasks는 스트리밍 아키텍처 덕분에 **500페이지 이상** 파일을 전체 문서를 메모리에 로드하지 않고도 처리할 수 있습니다.

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 모든 Java IDE와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 IntelliJ IDEA, Eclipse, NetBeans를 포함한 모든 주요 Java IDE와 호환됩니다.

**Q: Aspose.Tasks가 MPP 외에 다른 파일 형식을 지원하나요?**  
A: 예, Aspose.Tasks는 MPP, XML, HTML을 포함한 다양한 파일 형식을 지원합니다.

**Q: Aspose.Tasks가 엔터프라이즈 수준의 프로젝트 관리에 적합한가요?**  
A: 물론입니다. Aspose.Tasks는 모든 규모의 프로젝트 관리를 위한 포괄적인 기능을 제공하므로 엔터프라이즈 수준의 프로젝트 관리에 적합합니다.

**Q: 비율 스케일 외에도 리소스 할당을 더 맞춤화할 수 있나요?**  
A: 예, Aspose.Tasks는 비용, 작업, 기간 조정을 포함한 리소스 할당 맞춤화를 위한 광범위한 기능을 제공합니다.

**Q: Aspose.Tasks 지원을 위한 커뮤니티 포럼이 있나요?**  
A: 예, Aspose.Tasks 포럼에서 지원을 받고 다른 사용자와 상호 작용할 수 있습니다. [here](https://forum.aspose.com/c/tasks/15)

---

**마지막 업데이트:** 2026-06-10  
**테스트 환경:** Aspose.Tasks for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 리소스 할당 만들기](/tasks/java/resource-assignments/create-resource-assignments/)
- [할당 수정 방법 – Aspose와 공유 리소스 읽기](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Aspose.Tasks에서 리소스 할당에 메모 추가하는 방법](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}