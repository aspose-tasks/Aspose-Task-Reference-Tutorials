---
date: 2026-09-09
description: Aspose.Tasks for Java를 사용하여 교차 프로젝트 작업을 식별하는 방법을 배우세요. 원활한 통합, 효율적인 관리
  및 실제 사례를 살펴보세요.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Aspose.Tasks에서 교차 프로젝트 작업 식별
og_description: Aspose.Tasks for Java에서 교차 프로젝트 작업을 식별합니다. 문서 디렉터리 설정, 작업 ID 검색 및
  연결된 프로젝트를 효율적으로 관리하는 방법을 배우세요.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Aspose.Tasks에서 교차 프로젝트 작업 식별 – Java 가이드
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Aspose.Tasks에서 교차 프로젝트 작업 식별
url: /ko/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 교차 프로젝트 작업 식별

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **교차 프로젝트 작업을 식별하는 방법**을 배웁니다. 상호 의존적인 일정 포트폴리오를 관리하거나 외부 종속성을 감사해야 할 경우, 아래 단계에서는 다른 프로젝트 파일을 참조하는 작업을 찾고, 해당 식별자를 가져오며, 프로그래밍 방식으로 작업하는 방법을 보여줍니다.

## 빠른 답변
- **“교차 프로젝트 작업을 식별한다”는 무슨 의미인가요?** 다른 프로젝트 파일의 작업을 참조하거나 의존하는 작업을 찾는 것을 의미합니다.  
- **어떤 메서드가 작업 ID를 출력합니까?** `externalTask.get(Tsk.ID)`를 사용하여 작업 ID를 출력합니다.  
- **문서 디렉터리를 어떻게 설정합니까?** 폴더 경로를 `String` 변수(예: `dataDir`)에 할당합니다.  
- **UID로 작업을 검색하는 속성은 무엇입니까?** `getChildren().getByUid(yourUid)`를 호출합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 예, 상업적 배포를 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## “교차 프로젝트 작업을 식별한다”는 무엇입니까?
교차 프로젝트 작업을 식별하면 여러 Microsoft Project 파일에 걸쳐 분산된 작업 간의 관계를 추적할 수 있습니다. 외부 일정에 참조되거나 의존하는 작업을 찾음으로써 작업 항목이 프로젝트 경계에서 어떻게 상호 작용하는지 이해하고, 중복 작업을 방지하며, 정확한 일정 관리를 유지할 수 있습니다. 이 기능은 작업이 공유되거나 외부 일정에 의존하는 대규모 포트폴리오에 필수적입니다.

## 왜 Aspose.Tasks for Java를 사용합니까?
Aspose.Tasks for Java는 **50개 이상의 입력 및 출력 형식**(MPP, MPX, XML, CSV 등)을 지원하며 전체 파일을 메모리에 로드하지 않고 **최대 10,000개의 작업**을 처리할 수 있습니다. 이 라이브러리는 모든 JVM 호환 플랫폼에서 작동하고 Microsoft Project 설치가 필요 없으며, ID, UID, 외부 ID 및 연결 메타데이터에 대한 전체 API 접근을 제공합니다.

## 전제 조건
- 작동하는 Java 개발 환경 (JDK 8 이상).  
- Aspose.Tasks for Java가 설치되어 있습니다. **[here](https://releases.aspose.com/tasks/java/)**에서 다운로드할 수 있습니다.  
- 프로덕션에서 코드를 실행할 계획이라면 유효한 Aspose.Tasks 라이선스 파일이 필요합니다.

## 패키지 가져오기
`Project` 클래스는 Microsoft Project 파일을 나타내고, `Task`는 개별 작업을 나타내며, `Tsk`는 작업 필드 상수를 제공합니다.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 1단계: 문서 디렉터리 설정
`dataDir` 문자열은 `.mpp` 파일이 들어 있는 폴더 경로를 보유합니다.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 2단계: 외부 프로젝트 로드
`Project externalProject`는 지정된 외부 프로젝트 파일을 로드하여 검사합니다.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## 3단계: UID로 외부 작업 검색
`externalProject.getChildren().getByUid(uid)`는 고유 식별자를 사용하여 외부 프로젝트의 작업 컬렉션에서 작업을 검색합니다.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## 4단계: 작업 ID 출력 (주요 사용 사례)
`externalTask.get(Tsk.ID)`는 해당 작업에 대해 Aspose.Tasks가 할당한 내부 ID를 반환합니다.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## 5단계: 원본(외부) 작업 ID 출력
`externalTask.get(Tsk.ExternalID)`는 소스 프로젝트 파일에 정의된 작업의 원본 ID를 가져옵니다.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

프로젝트 간에 추적해야 하는 추가 작업이 있는 경우 위 단계를 반복하십시오.

## 일반적인 문제 및 팁
- **경로 오류** – `dataDir`가 적절한 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하십시오.  
- **UID를 찾을 수 없음** – 외부 프로젝트에 해당 UID가 존재하는지 확인하고, 사용 가능한 UID를 나열하려면 `externalProject.getRootTask().getChildren().size()`를 사용하십시오.  
- **라이선스 예외** – 누락되었거나 유효하지 않은 라이선스는 런타임에 라이선스 예외를 발생시킵니다.  
- **대형 프로젝트** – 작업이 5,000개를 초과하는 경우 `LoadOptions` 플래그와 함께 `ProjectReader`를 사용하여 데이터를 스트리밍하고 메모리 사용량을 줄이는 것을 고려하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 Java, .NET 등을 포함한 여러 언어를 지원합니다.

**Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 **[here](https://reference.aspose.com/tasks/java/)**를 참고하십시오.

**Q: Aspose.Tasks for Java에 대한 무료 체험이 있나요?**  
A: 예, 무료 체험은 **[here](https://releases.aspose.com/)**에서 받을 수 있습니다.

**Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 받을 수 있나요?**  
A: 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 얻을 수 있습니다.

**Q: 도움이 필요하거나 구체적인 질문이 있나요?**  
A: Aspose.Tasks 지원 포럼을 **[here](https://forum.aspose.com/c/tasks/15)**에서 방문하십시오.

---

**마지막 업데이트:** 2026-09-09  
**테스트 환경:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Tasks에서 프로젝트 관리 작업 종속성 만들기](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks에서 프로젝트 시작 날짜 설정 및 상위/하위 작업 관리](/tasks/java/task-properties/parent-child-tasks/)
- [MPP 프로젝트 Java 생성 – Aspose.Tasks로 작업 진행률 변경](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}