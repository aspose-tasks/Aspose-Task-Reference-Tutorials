---
title: Aspose.Tasks를 사용한 다양한 단위의 작업 기간
linktitle: Aspose.Tasks를 사용한 다양한 단위의 작업 기간
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks를 사용하여 Java 프로젝트의 작업 기간 관리를 살펴보세요. 기간을 분, 일, 시간, 주, 월 단위로 정확하게 계산하고 변환합니다.
type: docs
weight: 32
url: /ko/java/task-properties/task-duration-different-units/
---
## 소개
프로젝트 관리 영역에서는 작업 기간을 이해하고 관리하는 것이 중요한 측면입니다. Aspose.Tasks for Java는 이를 효율적으로 처리할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 사용하여 다양한 단위로 작업 기간을 검색하는 방법을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- JDK(Java 개발 키트)가 설치되었습니다.
-  Aspose.Tasks for Java 라이브러리. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/tasks/java/)
- Java 프로그래밍에 대한 기본 이해
## 패키지 가져오기
Java 프로젝트에 Aspose.Tasks 라이브러리를 포함합니다. 코드 시작 부분에 다음 import 문을 추가합니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 1단계: 프로젝트 설정
선호하는 IDE(통합 개발 환경)에서 새 Java 프로젝트를 생성하는 것부터 시작하세요. 프로젝트 종속성에 Aspose.Tasks 라이브러리를 포함해야 합니다.
## 2단계: 프로젝트 템플릿 읽기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// MS 프로젝트 템플릿 파일 읽기
String fileName = dataDir + "project.xml";
// 입력 파일을 프로젝트로 읽기
Project project = new Project(fileName);
```
 반드시 교체하세요`"Your Document Directory"` 프로젝트 파일의 실제 경로를 사용하세요.
## 3단계: 작업 검색
```java
// 다양한 형식으로 기간을 계산하는 작업 가져오기
Task task = project.getRootTask().getChildren().getById(1);
```
 여기서는 프로젝트에서 작업을 가져옵니다. 조정하다`getById(1)` 프로젝트의 작업 ID를 기반으로 합니다.
## 4단계: 지속 시간(분)
```java
// 시간을 분 단위로 가져옵니다.
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
이 단계에서는 작업 기간을 분 단위로 계산합니다.
## 5단계: 기간(일)
```java
// 기간을 일 단위로 가져옵니다.
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
이 단계에서는 작업 기간을 일 단위로 계산합니다.
## 6단계: 기간(시간)
```java
// 시간 단위로 기간 가져오기
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
이 단계에서는 작업 기간을 시간 단위로 계산합니다.
## 7단계: 기간(주)
```java
// 기간을 주 단위로 가져옵니다.
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
이 단계에서는 작업 기간을 주 단위로 계산합니다.
## 8단계: 기간(개월)
```java
// 기간을 개월 단위로 가져옵니다.
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
이 단계에서는 작업 기간을 개월 단위로 계산합니다.
## 결론
Aspose.Tasks for Java를 사용하면 작업 기간 관리가 간단해집니다. 이 튜토리얼에서는 다양한 시간 단위에 대한 명확성을 제공하면서 프로세스를 단계별로 안내했습니다.
## 자주 묻는 질문
### Q: Java IDE에서 Aspose.Tasks for Java를 사용할 수 있나요?
예, Aspose.Tasks for Java는 모든 Java 통합 개발 환경(IDE)과 호환됩니다.
### Q: Microsoft Project 파일에서 작업 ID를 어떻게 얻을 수 있습니까?
프로젝트 파일을 검사하거나 Aspose.Tasks API를 사용하여 프로그래밍 방식으로 작업 ID를 검색할 수 있습니다.
### Q: Aspose.Tasks는 대규모 프로젝트를 처리하는 데 적합합니까?
전적으로. Aspose.Tasks는 다양한 규모의 프로젝트를 효율적으로 처리하도록 설계되었습니다.
### Q: 추가 문서는 어디서 찾을 수 있나요?
 방문하다[선적 서류 비치](https://reference.aspose.com/tasks/java/)포괄적인 자원을 위해.
### Q: 구매하기 전에 Java용 Aspose.Tasks를 사용해 볼 수 있나요?
 예, 다음을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 그 능력을 평가합니다.