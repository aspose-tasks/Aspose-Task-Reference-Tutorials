---
title: Aspose.Tasks에서 MPP 파일 업데이트
linktitle: Aspose.Tasks에서 MPP 파일 업데이트
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MPP 파일을 원활하게 업데이트하는 방법을 알아보세요. 효율적인 프로젝트 파일 조작을 위한 단계별 가이드를 따르세요.
type: docs
weight: 19
url: /ko/java/project-management/update-mpp/
---
## 소개
프로젝트 관리 영역에서 프로젝트 파일을 처리하고 업데이트하는 것은 중요한 작업입니다. Aspose.Tasks for Java는 Java 개발자가 Microsoft Project 파일을 원활하게 조작할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 파일을 업데이트하는 방법을 살펴보겠습니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1. Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오.
2.  Java용 Aspose.Tasks: 다음에서 Java용 Aspose.Tasks를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).
3. Java 기본 지식: 예제를 따라가려면 Java 프로그래밍 언어에 대한 지식이 필요합니다.

## 패키지 가져오기
먼저 Aspose.Tasks 기능을 효과적으로 활용하려면 필요한 패키지를 Java 프로젝트로 가져와야 합니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
이 코드 줄은 Aspose.Tasks 라이브러리에서 모든 필수 클래스와 메서드를 가져오므로 Microsoft Project 파일을 쉽게 사용할 수 있습니다.

이제 Aspose.Tasks for Java를 사용하여 MPP 파일을 업데이트하는 프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 2단계: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` MPP 파일이 있는 실제 경로를 사용하세요.
## 3단계: 기존 프로젝트 읽기
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 이 코드는 다음과 같은 기존 MPP 프로젝트 파일을 읽습니다.`SampleMSP2010.mpp` 지정된 데이터 디렉토리에서.
## 4단계: 새 작업 만들기
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
여기서는 프로젝트의 루트 작업에 "Task1"이라는 새 작업을 추가합니다.
## 5단계: 시작 및 종료 날짜 설정
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
이 코드 줄은 새로 생성된 작업의 시작 날짜와 완료 날짜를 설정합니다.
## 6단계: 프로젝트 저장
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 마지막으로 이 단계에서는 새로 추가된 작업과 함께 업데이트된 프로젝트를`AfterLinking.mpp`.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 파일을 업데이트하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 Java 애플리케이션 내에서 Microsoft Project 파일을 효율적으로 조작할 수 있습니다.
## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있습니까?
A: 예, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 효율적으로 처리할 수 있는 강력한 기능을 제공합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음 사이트에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Q: Java용 Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원합니까?
A: 물론 Aspose.Tasks for Java는 MPP, MPT 및 XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.
### Q: Aspose.Tasks for Java에 대한 임시 라이선스를 얻을 수 있나요?
 A: 예, 테스트 목적으로 임시 라이센스를 사용할 수 있습니다. 당신은에서 얻을 수 있습니다[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for Java에 관해 도움이나 지원을 어디서 구할 수 있나요?
 A: 다음을 방문하실 수 있습니다.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15) 도움이나 문의사항이 있으면