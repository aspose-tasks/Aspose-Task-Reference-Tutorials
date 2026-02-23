---
date: 2026-02-23
description: Aspose.Tasks for Java를 탐색하여 프로젝트 관리를 간소화하고, 작업 비율을 계산하고 진행 상황을 효율적으로
  추적하는 방법을 배워보세요.
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: '프로젝트 관리 Java: Aspose.Tasks를 사용한 작업 % 완료'
url: /ko/java/task-properties/percentage-complete-calculations/
weight: 25
---

 all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 관리 Java: Aspose.Tasks를 사용한 작업 완료 비율 계산

## 소개
Aspose.Tasks for Java를 사용한 **project management java**에 대한 포괄적인 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 Microsoft Project 파일을 읽고, 작업 완료량을 계산하며, 모든 작업에 대한 정확한 진행 비율을 얻는 방법을 배웁니다. 이러한 계산을 마스터하면 이해관계자에게 정보를 제공하고 프로젝트가 일정대로 진행되도록 할 수 있습니다.

## 빠른 답변
- **Java에서 Microsoft Project 파일을 처리하는 라이브러리는 무엇인가요?** Aspose.Tasks for Java.  
- **전체 진행 상황을 표시하는 속성은 무엇인가요?** `Tsk.PERCENT_COMPLETE`.  
- **.mpp 파일을 어떻게 읽나요?** `new Project(filePath)` 로 로드합니다.  
- **작업 완료량을 계산할 수 있나요?** 예, `Tsk.PERCENT_WORK_COMPLETE` 를 사용합니다.  
- **프로덕션에 라이선스가 필요합니까?** 유효한 Aspose.Tasks 라이선스가 필요합니다.

## Project Management Java란?
Project management java는 Aspose.Tasks와 같은 Java 기반 도구 및 라이브러리를 사용하여 프로젝트 일정을 프로그래밍 방식으로 생성, 읽기 및 조작하는 것을 의미합니다. 이 접근 방식은 자동화된 보고, 맞춤형 대시보드 및 기존 Java 애플리케이션과의 원활한 통합을 가능하게 합니다.

## 작업 비율 계산에 Aspose.Tasks를 사용하는 이유
- **정확한 진행 상황 추적** – 수동 파싱 없이 기본 Project 필드를 가져옵니다.  
- **전체 .mpp 지원** – Microsoft Project 파일을 직접 읽고, 편집하고, 저장합니다.  
- **확장 가능한 자동화** – 수천 개의 작업을 몇 초 안에 처리하여 대규모 포트폴리오에 적합합니다.  
- **크로스 플랫폼** – 데스크톱부터 클라우드 서비스까지 모든 Java 런타임에서 작동합니다.

## 전제 조건
시작하기 전에 다음이 설치되어 있는지 확인하십시오:

- **Java Development Kit (JDK)** 가 설치되어 있음 (Java 8 이상).  
- **Aspose.Tasks for Java** 라이브러리 – [this link](https://releases.aspose.com/tasks/java/) 에서 다운로드하십시오.  
- 알려진 디렉터리에 배치된 샘플 Microsoft Project 파일 (예: *Software Development.mpp*).

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다. 이 코드 조각은 Aspose.Tasks를 사용하는 모든 Java 클래스에 추가해야 합니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### 단계 1: 문서 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의합니다. 자리표시자를 실제 경로로 교체하십시오.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 단계 2: 프로젝트 파일 로드
`Project` 인스턴스를 생성하고 Microsoft Project 파일을 로드합니다. 이 단계는 **Microsoft Project 파일을 읽어** 작업에 접근할 수 있게 합니다.

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### 단계 3: 작업 컬렉션 가져오기
루트 작업을 가져온 다음 그 하위 작업들을 가져옵니다. 이 컬렉션은 프로젝트의 모든 최상위 작업을 나타냅니다.

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### 단계 4: 완료 비율 값 출력
각 작업을 반복하면서 세 가지 주요 진행 지표를 표시합니다:

- **Percentage Complete** – 전체 작업 진행 상황.  
- **Percentage Work Complete** – 작업 기반 진행 상황.  
- **Physical Percentage Complete** – 물리적 진행 상황 (설정된 경우).

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

모니터링이 필요한 모든 작업에 대해 이 루프를 실행하십시오. 출력은 각 작업 항목에 대한 **진행 상황을 얻는 방법**을 명확히 보여줍니다.

## 일반적인 사용 사례
- **대시보드 보고:** 비율을 가져와 BI 도구에 전달합니다.  
- **자동 알림:** 작업의 `PERCENT_COMPLETE` 가 임계값 이하가 되면 알림을 트리거합니다.  
- **리소스 레벨링:** `PERCENT_WORK_COMPLETE` 를 기반으로 할당을 조정하여 일정이 현실적이도록 합니다.

## 문제 해결 및 팁
- **Null 값:** 프로젝트 파일에 실제로 조회하려는 필드가 포함되어 있는지 확인하십시오; 일부 오래된 .mpp 파일에는 `PHYSICAL_PERCENT_COMPLETE` 가 없을 수 있습니다.  
- **성능:** 매우 큰 프로젝트의 경우 `TaskCollection` 을 페이지 처리하거나 작업 ID로 필터링하여 메모리 사용량을 줄이는 것을 고려하십시오.  
- **라이선스 오류:** 라이선스 경고가 표시되면 `Project` 객체를 생성하기 전에 유효한 Aspose.Tasks 라이선스 파일이 로드되었는지 확인하십시오.

## 자주 묻는 질문

**Q: Aspose.Tasks 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [here](https://reference.aspose.com/tasks/java/) 에서 확인할 수 있습니다.

**Q: Java용 Aspose.Tasks 라이브러리를 어떻게 다운로드하나요?**  
A: [here](https://releases.aspose.com/tasks/java/) 에서 다운로드할 수 있습니다.

**Q: 무료 체험판이 있나요?**  
A: 예, 무료 체험판은 [here](https://releases.aspose.com/) 에서 이용할 수 있습니다.

**Q: Aspose.Tasks 지원은 어디서 받을 수 있나요?**  
A: 지원 포럼은 [here](https://forum.aspose.com/c/tasks/15) 에서 확인하십시오.

**Q: 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/) 에서 획득할 수 있습니다.

### 추가 Q&A

**Q: Aspose.Tasks 없이 작업 비율을 계산할 수 있나요?**  
A: .mpp 바이너리를 직접 파싱할 수는 하지만, Aspose.Tasks는 모든 예외 상황을 처리하는 신뢰할 수 있고 완전 지원되는 API를 제공합니다.

**Q: Aspose.Tasks가 Project Online 파일을 읽는 것을 지원하나요?**  
A: 예, .mpp 형식으로 저장된 경우 Project Online에서 내보낸 파일을 로드할 수 있습니다.

---

**마지막 업데이트:** 2026-02-23  
**테스트 환경:** Aspose.Tasks for Java 24.11 (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}