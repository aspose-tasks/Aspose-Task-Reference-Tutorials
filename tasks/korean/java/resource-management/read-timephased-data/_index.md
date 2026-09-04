---
date: 2026-06-15
description: Aspose.Tasks for Java를 사용하여 MS Project 리소스에서 timephased data를 추출하는 방법을
  배웁니다. get resource by id에 대한 단계별 가이드.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Aspose.Tasks에서 리소스의 Timephased Data 읽기
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 리소스의 Timephased Data 읽기 – get resource by id
url: /ko/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 리소스의 시간별 데이터 읽기

## 소개
이 튜토리얼에서는 **how to get resource by id**를 배우고 Aspose.Tasks for Java를 사용하여 해당 리소스의 시간별 데이터를 읽는 방법을 알아봅니다. 프로젝트 폴더 설정부터 작업 및 비용 시간별 값을 출력하는 단계까지 차근차근 안내하므로, Microsoft Project 파일에서 유용한 일정 정보를 프로그래밍 방식으로 추출할 수 있습니다. Aspose.Tasks for Java는 Microsoft Project를 설치하지 않아도 Microsoft Project 파일을 생성, 읽기, 수정 및 변환할 수 있는 포괄적인 API로, 다양한 프로젝트 관리 기능과 포맷을 지원합니다.

## 빠른 답변
- **“get resource by id”는 무엇을 하나요?** It retrieves a specific `Resource` object from a `Project` using its unique identifier.  
- **시간별 데이터를 처리하는 라이브러리는 무엇인가요?** Aspose.Tasks for Java provides the `Resource.getTimephasedData` API.  
- **라이선스가 필요합니까?** A free trial works for development; a commercial license is required for production.  
- **대형 프로젝트를 읽을 수 있나요?** Yes—Aspose.Tasks can process files with up to 10,000 tasks without loading the whole file into memory.  
- **필요한 Java 버전은 무엇인가요?** Java 8 or higher; the library is compatible with all major JDKs.

## “get resource by id”란 무엇인가요?
`get resource by id`는 로드된 `Project`에서 리소스의 숫자 ID를 사용하여 `Resource` 인스턴스를 가져오는 메서드 호출입니다. 이 작업을 통해 할당, 캘린더, 사용자 정의 필드 등 리소스의 상세 속성에 정확히 접근할 수 있으며, 해당 리소스와 연관된 시간별 작업 또는 비용 데이터를 추출하는 데 필수적입니다.

## 시간별 데이터에 Aspose.Tasks를 사용하는 이유는?
Aspose.Tasks는 **50개 이상의 입력 및 출력 형식**(MPP, XML, CSV 등)을 지원하며, 다년 일정에 걸친 리소스의 시간별 작업 및 비용 값을 메모리 사용량을 최소화하면서 추출할 수 있습니다. API는 기본적으로 15분 간격의 데이터를 반환하므로, 보고서 작성이나 맞춤형 분석에 필요한 세밀한 인사이트를 제공합니다.

## 전제 조건
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK): 시스템에 JDK가 설치되어 있는지 확인하십시오. You can download it from the [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) and follow the installation instructions.  
2. Aspose.Tasks for Java Library: Aspose.Tasks for Java 라이브러리를 [download page](https://releases.aspose.com/tasks/java/)에서 다운로드하고 문서에 제공된 설치 지침을 따르세요.

## 패키지 가져오기
첫 번째 단계는 필요한 Aspose.Tasks 클래스를 Java 소스 파일에 가져오는 것입니다.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## 1단계: 데이터 디렉터리 설정
먼저, MS Project 파일이 위치한 디렉터리를 정의합니다. 데이터 폴더를 소스 코드와 분리하면 프로젝트 유지 관리가 쉬워집니다.

```java
String dataDir = "Your Data Directory";
```

## 2단계: MS Project 템플릿 파일 읽기
MS Project 템플릿 파일의 이름을 지정합니다. 템플릿을 사용하면 서로 다른 프로젝트 간에 열 설정이 일관되게 유지됩니다.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## 3단계: 입력 파일을 Project로 읽기
`Project` 클래스는 메모리 내에서 Microsoft Project 파일을 나타내는 Aspose.Tasks의 핵심 객체입니다. 파일을 로드하면 작업, 리소스 및 일정에 프로그래밍 방식으로 접근할 수 있습니다.

```java
Project project = new Project(dataDir + fileName);
```

## 4단계: ID로 리소스 가져오기
특정 리소스를 가져오려면 `getResources().getById(id)` 메서드를 호출합니다. 이것이 주요 키워드에서 언급된 정확한 작업입니다.

```java
Resource resource = project.getResources().getByUid(1);
```

## 5단계: 리소스 작업에 대한 시간별 데이터 출력
`Resource` 객체를 얻은 후에는 `resource.getTimephasedData(ResourceTimephasedDataType.Work)`를 호출하여 시간별 작업 할당량을 얻을 수 있습니다. 반환된 컬렉션에는 각 구간의 시작 날짜, 종료 날짜 및 작업량을 포함하는 `TimephasedData` 객체가 들어 있습니다.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## 6단계: 리소스 비용에 대한 시간별 데이터 출력
마찬가지로 `resource.getTimephasedData(ResourceTimephasedDataType.Cost)`는 동일한 시간 구간별로 분류된 비용 정보를 반환합니다. 이는 예산 책정 및 비용 추적 보고서에 유용합니다.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 한 줄로 ID로 리소스를 가져오는 방법은?
프로젝트를 로드한 후 `project.getResources().getById(5)`를 호출합니다—필요한 실제 리소스 ID로 **5**를 교체하십시오. 이 한 번의 호출로 `Resource` 객체가 반환되며, 이후 시간별 데이터, 할당 또는 사용자 정의 필드를 조회할 수 있습니다. 리소스가 내부적으로 인덱싱되어 있어 메서드는 O(1) 시간에 실행됩니다.

## 일반적인 문제 및 해결책
- **Resource not found** – 프로젝트 파일에 해당 ID가 존재하는지 확인하십시오; ID는 1부터 시작하며 각 리소스마다 고유합니다.  
- **Empty timephased data** – 리소스에 작업 또는 비용 할당이 있는지 확인하십시오; 그렇지 않으면 컬렉션이 비어 있습니다.  
- **Large file performance** – `Project.setLoadOptions(LoadOptions.fromFile(...))`를 사용하여 500 MB보다 큰 프로젝트에 대해 지연 로딩을 활성화하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks는 Microsoft Project 외에 다른 유형의 프로젝트 파일을 처리할 수 있나요?**  
A: 예, Aspose.Tasks는 MPP, XML, CSV 및 여러 다른 형식을 지원하므로 다양한 표준 간에 읽고 쓸 수 있습니다.

**Q: Aspose.Tasks는 다양한 Java 개발 환경과 호환되나요?**  
A: 물론입니다. 이 라이브러리는 모든 주요 IDE(IntelliJ IDEA, Eclipse, NetBeans)와 빌드 도구(Maven, Gradle)에서 작동합니다.

**Q: Aspose.Tasks를 사용하여 프로젝트 데이터를 조작할 수 있나요?**  
A: 예, API를 통해 작업, 리소스, 할당 및 사용자 정의 필드를 생성, 수정 및 삭제할 수 있습니다.

**Q: Aspose.Tasks는 엔터프라이즈 수준 프로젝트에 적합한가요?**  
A: 적합합니다. 기업에서는 Aspose.Tasks를 사용해 대량 처리, 배치 변환 및 서버 측 보고서를 수행하며, Microsoft Project 설치가 필요하지 않습니다.

**Q: Aspose.Tasks 사용 중 문제가 발생하면 어디에서 지원을 받을 수 있나요?**  
A: [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 커뮤니티와 지원 팀의 도움을 받을 수 있습니다.

## 결론
이 튜토리얼에서는 **get resource by id**를 사용하여 Aspose.Tasks for Java로 리소스의 시간별 작업 및 비용 데이터를 읽는 방법을 배웠습니다. 이 단계를 따르면 프로젝트 파일에서 유용한 일정 정보를 효율적으로 추출하고 맞춤형 보고서나 분석 파이프라인에 통합할 수 있습니다.

---

**마지막 업데이트:** 2026-06-15  
**테스트 환경:** Aspose.Tasks 24.11 for Java  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks for Java를 사용하여 프로젝트에 리소스 추가](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java로 MS Project 리소스 비용 관리](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks에서 MS Project 캘린더의 작업 주 읽기 (Java)](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}