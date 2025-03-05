---
title: Aspose.Tasks에서 예상 및 마일스톤 작업 처리
linktitle: Aspose.Tasks에서 예상 및 마일스톤 작업 처리
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 효과적인 프로젝트 관리를 살펴보세요. 예상 작업과 주요 작업을 손쉽게 처리하세요. 지금 라이브러리를 다운로드하세요!
type: docs
weight: 15
url: /ko/java/task-properties/estimated-milestone-tasks/
---
## 소개
Aspose.Tasks for Java는 작업 처리, 프로젝트 관리 및 프로젝트 데이터 조작을 쉽게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 예상 작업과 마일스톤 작업을 처리하는 프로젝트 관리의 중요한 측면에 중점을 둘 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본적인 이해.
-  Aspose.Tasks for Java 라이브러리가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
- Eclipse 또는 IntelliJ와 같은 통합 개발 환경(IDE).
## 패키지 가져오기
Java 기능에 Aspose.Tasks를 활용하는 데 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;

```
## 1단계: ChildTasksCollector 인스턴스 만들기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
```
## 2단계: TaskUtils를 사용하여 RootTask에서 모든 작업 수집
```java
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 3단계: 수집된 모든 작업을 분석합니다.
```java
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
이 단계에서는 Java용 Aspose.Tasks를 활용하여 작업을 수집 및 분석하고 작업이 노력 중심적이고 중요한지 여부와 관련된 정보를 추출합니다.
예제를 이러한 단계로 분류함으로써 다양한 기술 수준의 사용자가 프로세스를 명확하고 관리하기 쉽게 만드는 것을 목표로 합니다.
## 결론
Aspose.Tasks for Java에서 예상 작업과 마일스톤 작업 처리를 마스터하면 효과적인 프로젝트 관리가 가능해집니다. 이 튜토리얼을 자세히 살펴보면서 주저하지 말고 Aspose.Tasks 라이브러리에서 제공하는 추가 기능을 실험하고 탐색해 보세요.

## 자주 묻는 질문
### Aspose.Tasks는 대규모 프로젝트 관리에 적합합니까?
전적으로! Aspose.Tasks는 다양한 규모의 프로젝트를 처리하도록 설계되어 효율적인 프로젝트 관리를 위한 강력한 기능을 제공합니다.
### Aspose.Tasks를 기존 Java 프로젝트에 통합할 수 있나요?
예, 제공된 문서에 따라 Aspose.Tasks를 Java 프로젝트에 원활하게 통합할 수 있습니다.
### Aspose.Tasks에 대한 추가 지원은 어디서 찾을 수 있나요?
 Aspose.Tasks 커뮤니티 포럼[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 도움을 구하고 경험을 공유할 수 있는 훌륭한 장소입니다.
### 무료 평가판이 제공되나요?
 예, Aspose.Tasks의 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Tasks에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).