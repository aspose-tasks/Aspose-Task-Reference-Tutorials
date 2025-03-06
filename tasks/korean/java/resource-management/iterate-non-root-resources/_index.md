---
title: Aspose.Tasks에서 루트가 아닌 리소스를 반복합니다.
linktitle: Aspose.Tasks에서 루트가 아닌 리소스를 반복합니다.
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 루트가 아닌 리소스를 효율적으로 반복하는 방법을 알아보세요. 개발 프로세스를 강화하세요.
weight: 12
url: /ko/java/resource-management/iterate-non-root-resources/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 루트가 아닌 리소스를 반복합니다.

## 소개
Aspose.Tasks for Java는 개발자에게 Microsoft Project 파일을 효율적으로 조작하는 데 필요한 도구를 제공하는 강력한 라이브러리입니다. 직관적인 인터페이스와 광범위한 기능을 갖춘 Aspose.Tasks는 프로젝트 데이터 작업 프로세스를 단순화하여 개발자가 강력한 애플리케이션을 구축하는 데 집중할 수 있도록 합니다.
## 전제조건
Java용 Aspose.Tasks를 사용하기 전에 다음 사항을 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/tasks/java/).

## 패키지 가져오기
Java 프로젝트에서 Aspose.Tasks 작업을 시작하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 1단계: 데이터 디렉터리 설정
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 파일이 저장된 디렉터리의 경로를 사용하세요.
## 2단계: 프로젝트 파일 로드
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
 이 줄은 새로운 것을 초기화합니다`Project` 이름이 지정된 프로젝트 파일을 로드하여 객체를 생성합니다.`"ResourceCosts.mpp"` 지정된 데이터 디렉토리에서.
## 3단계: 루트가 아닌 리소스에 대한 반복
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
이 루프는 프로젝트의 각 리소스를 반복합니다(`prj.getResources()`). 리소스가 루트 리소스인 경우 다음 반복으로 건너뜁니다. 그렇지 않으면 루트가 아닌 리소스의 이름을 인쇄합니다.

## 결론
이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 루트가 아닌 리소스를 반복하는 방법을 살펴보았습니다. 다음 단계를 수행하면 프로젝트 데이터를 효과적으로 조작하고 개발 프로세스를 간소화할 수 있습니다.
## FAQ
### Aspose.Tasks for Java를 사용하여 새 프로젝트 파일을 만들 수 있나요?
예, Aspose.Tasks는 다양한 형식으로 프로젝트 파일을 생성, 수정 및 저장하는 기능을 제공합니다.
### Aspose.Tasks는 모든 버전의 Microsoft Project 파일을 지원합니까?
Aspose.Tasks는 MPP, MPT 및 XML을 포함한 Microsoft Project 2003-2019 파일 형식을 지원합니다.
### Aspose.Tasks는 Spring과 같은 Java 프레임워크와 호환됩니까?
예, Aspose.Tasks는 엔터프라이즈급 애플리케이션을 위해 Spring과 같은 Java 프레임워크에 원활하게 통합될 수 있습니다.
### Aspose.Tasks를 사용하여 프로젝트 데이터 필드를 사용자 정의할 수 있나요?
물론 Aspose.Tasks는 요구 사항에 따라 프로젝트 데이터 필드를 사용자 정의하기 위한 광범위한 API를 제공합니다.
### Aspose.Tasks는 개발자를 위한 지원과 문서를 제공합니까?
예, Aspose.Tasks는 개발자가 직면하는 모든 쿼리나 문제를 지원하기 위해 포괄적인 문서와 전용 지원 포럼을 제공합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
