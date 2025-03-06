---
title: Aspose.Tasks의 평일 속성
linktitle: Aspose.Tasks의 평일 속성
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java에서 평일 속성을 효율적으로 관리하는 방법을 알아보세요. 한 주의 시작 날짜, 월별 날짜 등을 쉽게 사용자 정의하세요.
type: docs
weight: 25
url: /ko/java/project-file-operations/weekday-properties/
---
## 소개
Aspose.Tasks for Java는 Java 개발자가 컴퓨터에 Microsoft Project를 설치하지 않고도 Microsoft Project 파일로 작업할 수 있도록 하는 강력한 API입니다. 주요 기능 중 하나는 주중 속성을 관리하여 사용자가 주 시작 날짜, 월별 날짜, 하루별 분, 주별 분을 사용자 정의할 수 있도록 하는 것입니다. 이 튜토리얼에서는 이러한 기능을 효과적으로 활용하는 방법에 대한 자세한 가이드를 제공합니다.
## 전제조건
Aspose.Tasks for Java를 시작하기 전에 다음 전제 조건이 있는지 확인하세요.
### JDK(자바 개발 키트)
시스템에 JDK가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 JDK를 다운로드하여 설치할 수 있습니다.
### Java 라이브러리용 Aspose.Tasks
 웹사이트에서 Aspose.Tasks for Java 라이브러리를 다운로드하여 설치하세요. 다운로드 링크에 접속하실 수 있습니다[여기](https://releases.aspose.com/tasks/java/).
### 통합 개발 환경(IDE)
Java 개발을 위해 선호하는 IDE를 선택하세요. 널리 사용되는 선택에는 IntelliJ IDEA, Eclipse 또는 NetBeans가 있습니다.
## 패키지 가져오기
시작하려면 필요한 Aspose.Tasks 패키지를 Java 프로젝트로 가져옵니다. 방법은 다음과 같습니다.

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

이제 더 나은 이해를 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 파일 로드
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
이 단계에는 지정된 데이터 디렉터리에서 "project.mpp"라는 프로젝트 파일을 로드하는 작업이 포함됩니다.
## 2단계: 평일 속성 표시
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
여기서는 로드된 프로젝트의 주 시작 날짜, 월별 일수, 하루별 분, 주당 분 속성을 검색하고 인쇄합니다.
## 3단계: 평일 속성 설정
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
이 단계에는 새 프로젝트 인스턴스를 생성하고 주 시작일, 월별 날짜, 일일 분, 주당 분과 같은 사용자 정의 평일 속성을 설정하는 작업이 포함됩니다.
## 4단계: 프로젝트 저장
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
마지막으로, 업데이트된 평일 속성이 포함된 수정된 프로젝트를 XML 파일로 저장합니다.
## 5단계: 결과 표시
```java
System.out.println("Process completed Successfully");
```
이 단계에서는 프로세스가 성공적으로 완료되었음을 확인합니다.
## 결론
효과적인 프로젝트 관리를 위해서는 Aspose.Tasks for Java의 평일 속성을 마스터하는 것이 중요합니다. 이 튜토리얼을 따라가면서 평일 속성을 쉽게 조작하고 사용자 정의하는 방법을 배웠습니다. 프로젝트 관리 기능을 향상시키기 위한 추가 문서와 예제를 살펴보세요.
## FAQ
### Q: Java용 Aspose.Tasks가 복잡한 프로젝트 구조를 처리할 수 있습니까?
A: 예, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 쉽게 처리할 수 있도록 포괄적인 지원을 제공합니다.
### Q: Aspose.Tasks for Java는 다른 버전의 Microsoft Project 파일과 호환됩니까?
A: 물론 Aspose.Tasks for Java는 다양한 버전의 Microsoft Project 파일을 지원하여 플랫폼 간 호환성을 보장합니다.
### Q: Aspose.Tasks for Java를 기존 Java 애플리케이션에 통합할 수 있나요?
A: 예, Aspose.Tasks for Java는 원활한 통합 기능을 제공하므로 강력한 프로젝트 관리 기능으로 Java 애플리케이션을 향상시킬 수 있습니다.
### Q: Aspose.Tasks for Java는 문서와 지원을 제공합니까?
 A: 예, Aspose.Tasks for Java에 대한 광범위한 문서 및 커뮤니티 지원에 액세스할 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
A: 예, 다음 사이트에서 Aspose.Tasks for Java의 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://reference.aspose.com/tasks/java/) 구매하기 전에 기능을 살펴보세요.