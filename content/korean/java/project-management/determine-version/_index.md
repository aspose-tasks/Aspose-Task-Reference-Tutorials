---
title: Aspose.Tasks를 사용하여 MS 프로젝트 버전 확인
linktitle: Aspose.Tasks를 사용하여 프로젝트 버전 확인
second_title: Aspose.Tasks 자바 API
description: Java용 Aspose.Tasks를 사용하여 프로그래밍 방식으로 MS 프로젝트 파일의 버전을 확인하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 12
url: /ko/java/project-management/determine-version/
---
## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 파일의 버전을 단계별로 확인하는 과정을 안내합니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치하지 않고도 Microsoft Project 파일을 조작할 수 있는 강력한 Java API입니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks for Java JAR 파일: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[웹사이트](https://releases.aspose.com/tasks/java/) 그리고 Java 프로젝트에 추가하세요.
3. MS 프로젝트 파일: 테스트용 MS 프로젝트 파일(XML 형식)을 준비합니다.

## 패키지 가져오기
코드를 살펴보기 전에 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## 1단계: 프로젝트 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` MS 프로젝트 파일이 포함된 디렉터리 경로를 사용하세요.
## 2단계: 프로젝트 로드
```java
Project project = new Project(dataDir + "input.xml");
```
 바꾸다`"input.xml"` MS 프로젝트 파일 이름으로.
## 3단계: 프로젝트 버전 결정
```java
//프로젝트 버전 속성 표시
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
이 코드 조각은 MS 프로젝트 파일의 버전과 마지막으로 저장된 날짜를 검색하고 인쇄합니다.
## 4단계: 결과 표시
```java
//변환 결과를 표시합니다.
System.out.println("Process completed Successfully");
```
이 줄은 프로세스가 완료되었음을 나타냅니다.

## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MS 프로젝트 파일의 버전을 확인하는 방법을 배웠습니다. 단계별 가이드를 따르면 번거로움 없이 Java 애플리케이션에서 MS 프로젝트 파일을 효율적으로 사용할 수 있습니다.

## FAQ
### Q: Aspose.Tasks를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
A: 예, Aspose.Tasks는 .NET, Java 및 C를 포함한 여러 프로그래밍 언어를 지원합니다.++.
### Q: Aspose.Tasks는 대규모 프로젝트에 적합합니까?
A: 물론입니다. Aspose.Tasks는 모든 규모의 프로젝트를 쉽게 처리하도록 설계되었습니다.
### Q: Aspose.Tasks를 사용하여 프로젝트 데이터를 사용자 정의할 수 있나요?
A: 예, Aspose.Tasks를 사용하면 프로젝트 데이터를 조작하고 작업, 리소스 등을 수정할 수 있습니다.
### Q: Aspose.Tasks에는 Microsoft Project 설치가 필요합니까?
A: 아니요, Aspose.Tasks는 독립적으로 작동하며 Microsoft Project를 설치할 필요가 없습니다.
### Q: Aspose.Tasks에 대한 기술 지원이 제공됩니까?
 A: 예, Aspose.Tasks 포럼에서 기술 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).