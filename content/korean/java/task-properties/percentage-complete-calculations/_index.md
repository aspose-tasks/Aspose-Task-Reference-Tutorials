---
title: Aspose.Tasks의 작업에 대한 완료율 계산
linktitle: Aspose.Tasks의 작업에 대한 완료율 계산
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks를 살펴보고 프로젝트 진행 상황 추적을 간소화하세요. 효율적인 프로젝트 관리를 위해 작업 비율을 쉽게 계산합니다.
type: docs
weight: 25
url: /ko/java/task-properties/percentage-complete-calculations/
---
## 소개
Aspose.Tasks for Java를 사용한 마스터링 작업 비율 계산에 대한 심층 가이드에 오신 것을 환영합니다. Aspose.Tasks는 Microsoft Project 파일 작업을 위해 설계된 강력한 Java 라이브러리로, 프로젝트 관리를 위한 강력한 기능 세트를 제공합니다. 이 튜토리얼에서는 완료율 계산에 중점을 두고 프로젝트 진행 상황을 효과적으로 모니터링하고 분석하는 데 필요한 지식을 제공합니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 갖추어져 있는지 확인하세요.
- Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오.
-  Aspose.Tasks 라이브러리: 다음에서 Java용 Aspose.Tasks 라이브러리를 다운로드하세요.[이 링크](https://releases.aspose.com/tasks/java/).
## 패키지 가져오기
Aspose.Tasks for Java 프로젝트에 필요한 패키지를 가져오는 것부터 시작해 보겠습니다. 프로젝트에 다음 코드 조각을 포함합니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
이제 자세한 설명과 함께 각 단계를 살펴보겠습니다.
## 1단계: 패키지 가져오기
첫 번째 단계에서는 Aspose.Tasks 프로젝트를 설정하는 데 필요한 패키지를 가져옵니다.
## 2단계: 문서 디렉터리 설정
 다음을 사용하여 문서 디렉토리의 경로를 정의하십시오.`dataDir`변하기 쉬운. "Software Development.mpp"와 같은 Microsoft Project 파일이 이 디렉터리에 있는지 확인하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 3단계: 프로젝트 로드
 새로 초기화`Project` 개체를 만들고 Microsoft Project 파일을 프로젝트 인스턴스에 로드합니다.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## 4단계: 작업 컬렉션 검색하기
 프로젝트의 루트 작업을 가져오고 다음을 사용하여 해당 하위 작업을 컬렉션으로 검색합니다.`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## 5단계: 인쇄 완료율
컬렉션의 각 작업을 반복하고 완료율, 작업 완료율, 실제 완료율을 인쇄합니다.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
프로젝트의 각 작업에 대해 이러한 단계를 반복하여 각 작업의 진행 상황에 대한 통찰력을 얻으세요.
## 결론
축하해요! Aspose.Tasks for Java를 사용하여 작업 비율 계산을 성공적으로 마스터했습니다. 이 강력한 라이브러리를 통해 개발자는 프로젝트 진행 상황을 효율적으로 관리하고 분석할 수 있습니다.
## 자주 묻는 질문
### Q: Aspose.Tasks 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/tasks/java/).
### Q: Java용 Aspose.Tasks 라이브러리를 어떻게 다운로드할 수 있나요?
 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
### Q: 무료 평가판이 제공됩니까?
예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 지원은 어디서 받을 수 있나요?
 지원 포럼 방문[여기](https://forum.aspose.com/c/tasks/15).
### Q: 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).