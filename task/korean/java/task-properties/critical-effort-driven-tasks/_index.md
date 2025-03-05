---
title: Aspose.Tasks에서 중요하고 노력 중심적인 작업을 관리하세요
linktitle: Aspose.Tasks에서 중요하고 노력 중심적인 작업을 관리하세요
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java 프로젝트에서 중요하고 노력이 많이 드는 작업을 쉽게 관리하세요. 라이브러리를 다운로드하고 프로젝트 관리 기능을 강화하세요.
type: docs
weight: 14
url: /ko/java/task-properties/critical-effort-driven-tasks/
---
빠르게 변화하는 프로젝트 관리 세계에서 중요하고 노력이 많이 드는 작업을 효율적으로 처리하는 것은 성공적인 프로젝트 완료에 필수적입니다. Aspose.Tasks for Java는 이러한 작업을 원활하게 관리할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 프로젝트에서 중요하고 노력이 많이 드는 작업을 처리하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Aspose.Tasks for Java Library: 다음에서 라이브러리를 다운로드하고 설치합니다.[Aspose.Tasks for Java 문서](https://reference.aspose.com/tasks/java/).
- JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
- 통합 개발 환경(IDE): Java 개발에 선호하는 IDE를 사용합니다.
- 프로젝트 파일: 데모에 사용할 프로젝트 파일을 XML 형식으로 준비합니다.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks for Java의 기능을 활용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
이제 각 단계를 포괄적인 가이드로 나누어 보겠습니다.
## 1단계: ChildTasksCollector를 사용하여 작업 수집
 만들기`ChildTasksCollector` 인스턴스를 사용하여 루트 작업에서 모든 작업을 수집합니다.`TaskUtils.apply`. 이렇게 하면 프로젝트 내의 모든 작업에 액세스할 수 있습니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// ChildTasksCollector 인스턴스 만들기
ChildTasksCollector collector = new ChildTasksCollector();
// TaskUtils를 사용하여 RootTask에서 모든 작업 수집
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 2단계: 수집된 작업을 통해 반복
 다음을 사용하여 수집된 모든 작업을 구문 분석합니다.`for` 고리. 각 작업에 대해 노력 중심적이고 중요한 작업인지 확인하고 해당 상태를 인쇄합니다.
```java
// 수집된 모든 작업을 분석합니다.
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
다음 단계를 수행하면 Aspose.Tasks for Java를 사용하여 프로젝트에서 중요하고 노력이 많이 드는 작업을 효과적으로 관리할 수 있습니다.
## 결론
결론적으로 Aspose.Tasks for Java는 Java 개발자가 프로젝트 관리에서 중요하고 노력이 많이 드는 작업을 효율적으로 관리할 수 있도록 지원합니다. 사용하기 쉬운 기능과 강력한 기능을 통해 복잡한 프로젝트 시나리오를 쉽게 처리할 수 있습니다.
## 자주 묻는 질문
### Q: Windows 및 Linux 환경 모두에서 Java용 Aspose.Tasks를 사용할 수 있습니까?
예, Aspose.Tasks for Java는 플랫폼 독립적이며 Windows 및 Linux 환경 모두에서 사용할 수 있습니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 예, Aspose.Tasks for Java의 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks에 대한 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 커뮤니티 지원 및 토론을 위해.
### Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Java용 Aspose.Tasks는 어디에서 구매할 수 있나요?
 Java용 Aspose.Tasks를 다음에서 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).