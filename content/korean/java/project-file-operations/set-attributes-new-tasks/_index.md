---
title: Aspose.Tasks에서 새 작업에 대한 MS 프로젝트 속성 설정
linktitle: Aspose.Tasks에서 새 작업에 대한 속성 설정
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 새 작업에 대한 MS 프로젝트 속성을 설정하는 방법을 알아보세요. 이 포괄적인 가이드를 사용하여 작업 속성을 손쉽게 사용자 정의하세요.
type: docs
weight: 21
url: /ko/java/project-file-operations/set-attributes-new-tasks/
---
## 소개
Aspose.Tasks for Java의 새로운 작업에 대한 MS 프로젝트 속성 설정에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다! 이 가이드에서는 이 강력한 Java 라이브러리를 사용하여 작업을 쉽게 관리하고 사용자 정의할 수 있도록 프로세스를 단계별로 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 시스템에 Java가 설치되어 있고 기본 Java 프로그래밍 개념을 잘 알고 있는지 확인하십시오.
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/).
3. Java IDE: 코딩을 위해 Eclipse 또는 IntelliJ IDEA와 같은 Java IDE(통합 개발 환경)를 선택합니다.

## 패키지 가져오기
새 작업에 대한 MS 프로젝트 속성 설정을 시작하기 전에 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## 1단계: 데이터 디렉터리 정의
먼저 프로젝트 파일을 저장할 디렉터리의 경로를 지정합니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 원하는 디렉토리의 경로로.
## 2단계: 프로젝트 인스턴스 생성
프로젝트 작업을 시작하려면 새 Project 객체를 인스턴스화하세요.
```java
Project prj = new Project();
```
그러면 새 프로젝트 인스턴스가 생성됩니다.
## 3단계: 새 작업 속성 설정
이제 새 작업의 시작 날짜를 설정해 보겠습니다. 이 예에서는 현재 날짜로 설정합니다.
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
 이 줄은 속성을 설정합니다`NEW_TASK_START_DATE` 에게`TaskStartDateType.CurrentDate`.
## 4단계: 프로젝트 저장
새 작업 속성을 사용하여 프로젝트를 XML 형식으로 저장합니다.
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
이 줄은 앞서 정의한 디렉터리에 지정된 파일 이름으로 프로젝트를 저장합니다.
## 5단계: 결과 표시
마지막으로 프로젝트 파일이 성공적으로 생성되었는지 확인하는 메시지를 인쇄해 보겠습니다.
```java
System.out.println("Project file generated Successfully");
```
이 줄은 콘솔에 성공 메시지를 표시합니다.

## 결론
축하해요! Aspose.Tasks for Java를 사용하여 새 작업에 대한 MS 프로젝트 속성을 설정하는 방법을 성공적으로 배웠습니다. 이러한 지식을 바탕으로 이제 요구 사항에 따라 작업 속성을 사용자 정의하여 프로젝트 관리 기능을 향상시킬 수 있습니다.
## FAQ
### Q: Aspose.Tasks for Java를 사용하여 기존 프로젝트 파일을 조작할 수 있습니까?
A: 예, Aspose.Tasks for Java는 다양한 형식으로 읽기, 수정 및 저장을 포함하여 기존 프로젝트 파일을 조작하는 광범위한 기능을 제공합니다.
### Q: Aspose.Tasks for Java에 대한 추가 문서와 리소스는 어디서 찾을 수 있나요?
 A: 다음에서 문서와 리소스를 탐색할 수 있습니다.[Aspose.Tasks for Java 문서 페이지](https://reference.aspose.com/tasks/java/).
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 예, 다음에서 Aspose.Tasks for Java의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 A: Aspose.Tasks for Java의 임시 라이선스는 다음에서 얻을 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for Java와 관련된 문제나 쿼리에 대한 지원은 어디서 받을 수 있나요?
 A: 다음에서 지원을 받고 커뮤니티와 상호 작용할 수 있습니다.[Aspose.Tasks for Java 지원 포럼](https://forum.aspose.com/c/tasks/15).