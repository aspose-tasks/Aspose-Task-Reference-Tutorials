---
date: 2026-01-23
description: Aspose.Tasks for Java를 사용하여 교차 프로젝트 작업을 식별하는 방법을 배우세요. 원활한 통합과 효율적인 관리를
  탐구하세요.
linktitle: Identify Cross Project Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 교차 프로젝트 작업 식별
url: /ko/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 교차 프로젝트 작업 식별

## 소개
Aspose.Tasks for Java를 사용하여 교차 프로젝트 작업을 효율적으로 식별하는 방법에 대한 포괄적인이션 통합하는 데 필요한 모든 단계를 안내합니다.

## 빠른이란 무엇을 의미합니까?** 다른 프로젝트 파일의 작업을 참조하거나 의존하는 작업을 찾는 것을 의미합니다.  
- **작업 ID를 출력하는 메서드는 무엇입니까?** `externalTask.get(Tsk.ID)`를 사용하여 작업 ID를 출력합니다.  
- **문서 디렉터리를 어떻게 설정합니까?** 폴더 경로를 `String` 변수(예: `dataDir`)에 할당합니다.  
- **UID로 작업을 검색하는 속성은 무엇입니까?** `getChildren().getByUid(yourUid)`를 호출합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 예, 상업적 배포를 위해서는 유효한 Aspose.Tasks 라이선스가 필요합니다.

## “교차 프로젝트 작업 식별”이란 무엇입니까?
교차 프로젝트 작업을 식별하면 여러 Microsoft Project 파일에 걸쳐 있는 작업 간의 관계를 추적할 수 있습니다. 이는 작업이 공유되거나 외부 일정에 의존하는 대규모 프로젝트 포트폴리오에 필수적입니다.

## 왜 Aspose.Tasks for Java를 사용합니까?
- **No Microsoft Project required** – Java에서 .mpp 파일을 직접 작업합니다.  
- **Full API access** – ID, 외부 ID, UID 등을 검색합니다.  
- **Cross‑platform** – 모든 JVM 호환 환경에서 실행됩니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Tasks for Java가 설치되어 있어야 합니다. **[here](https://releases.aspose.com/tasks/java/)**에서 다운로드할 수 있습니다.

## 패키지 가져오기
먼저, 프로젝트 조작을 가능하게 하는 필수 Aspose.Tasks 클래스를 가져옵니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 단계 1: 문서 디렉터리 설정
.mpp 파일이 위치한 폴더를 정의합니다. 이 단계는 보조 키워드 **set document directory**와 일치합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 단계 2: 외부 프로젝트 로드
외부 프로젝트 파일(예: *External.mpp*)을 로드하여 해당 작업을 검사합니다.

```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## 단계 3: UID로 외부 작업 검색
작업의 **UID**(고유 식별자)를 사용하여 원하는 특정 작업을 가져옵니다. 이는 보조 키워드 **get task uid**를 만족합니다.

```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## 단계 4: 작업 ID 출력 (주요 사용 사례)
이제 작업 객체를 얻었으므로 내부 ID를 출력합니다. 이는 보조 키워드 **print task id**를 보여줍니다.

```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## 단계 5: 원본(외부) 작업 ID 출력
작업이 원본 프로젝트 파일에서 가지고 있던 ID도 검색할 수 있습니다.

```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

프로젝트 간에 추적해야 하는 추가 작업에 대해 위 단계를 반복하십시오.

## 일반적인 문제 및 팁
- **Path errors** – `dataDir`이 적절한 파일 구분자(`/` 또는 `\\`)로 끝나는지 **UID not found** – 외부 프로젝트에 UID가 존재하는지 확인하고, `externalProject.getRootTask().getChildren().size()`를 사용하여 사용 가능한 UID를 나열하십시오.  
- **License exceptions** – 라이선스가 없거나 유효하지 않으면 런타임에 라이선스 예외가 발생합니다.

## 자주 묻는 질문

**Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks는 Java, .NET 등 여러 언어를 지원합니다.

**Q: Aspose.Tasks for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 **[here](https://reference.aspose.com/tasks/java/)**를 참조하십시오.

**Q: Aspose.Tasks for Java에 대한 무료 체험이 있나요?**  
A: 예, 무료 체험은 **[here](https://releases.aspose.com/)**에서 받을 수 있습니다.

**Q: Aspose.Tasks에 대한 임시 라이선스를 어떻게 받을 수 있나요?**  
A: 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 얻을 수 있습니다.

**Q: 도움이 필요하거나 특정 질문이 있습니까?**  
A: Aspose.Tasks 지원 포럼 **[here](https://forum.aspose.com/c/tasks/15)**을 방문하십시오.

---

**마지막 업데이트:** 2026-01-23  
**테스트 환경:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-wrap-class >}}