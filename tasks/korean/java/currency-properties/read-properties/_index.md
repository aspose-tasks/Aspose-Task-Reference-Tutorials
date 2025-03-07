---
title: Aspose.Tasks 프로젝트의 통화 속성 읽기
linktitle: Aspose.Tasks 프로젝트의 통화 속성 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 MS 프로젝트 파일에서 통화 정보를 추출하는 방법을 알아보세요. 단계별 가이드가 제공됩니다.
weight: 10
url: /ko/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 프로젝트의 통화 속성 읽기

## 소개
이 튜토리얼에서는 Java용 Aspose.Tasks를 활용하여 Microsoft Project 파일에서 통화 속성을 읽는 방법을 알아봅니다. Aspose.Tasks는 개발자가 Microsoft Project를 설치하지 않고도 Microsoft Project 문서를 조작할 수 있게 해주는 강력한 Java API입니다. 아래에 설명된 단계를 따르면 통화 관련 정보를 쉽게 추출할 수 있습니다.
## 전제조건
이 튜토리얼을 진행하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java JAR용 Aspose.Tasks: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/tasks/java/) 그리고 이를 Java 프로젝트에 포함시킵니다.
## 패키지 가져오기
필요한 패키지를 Java 클래스로 가져오는 것부터 시작하세요.
```java
import com.aspose.tasks.*;
```
## 1단계: 프로젝트 디렉터리 설정
먼저 Microsoft Project 파일이 있는 프로젝트 디렉터리를 설정합니다. 이 디렉터리 경로를 다음과 같이 정의할 수 있습니다.
```java
String dataDir = "Your Data Directory";
```
 바꾸다`"Your Data Directory"` 프로젝트 디렉터리의 실제 경로를 사용하세요.
## 2단계: 프로젝트 리더 인스턴스 생성
 인스턴스화`Project` Microsoft Project 파일의 경로를 제공하여 개체를 만듭니다.
```java
Project project = new Project(dataDir + "project.mpp");
```
 반드시 교체하세요`"project.mpp"` MS 프로젝트 파일 이름으로.
## 3단계: 통화 속성 표시
프로젝트 파일에서 통화 속성을 검색하고 표시합니다.
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
이 코드 세그먼트는 MS 프로젝트 파일에서 통화 코드, 숫자, 기호 및 기호 위치와 같은 정보를 가져와 콘솔에 인쇄합니다.
## 4단계: 프로세스 완료
마지막으로 프로세스가 성공적으로 완료되었음을 나타내는 메시지를 인쇄합니다.
```java
System.out.println("Process completed Successfully");
```
## 결론
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 통화 속성을 읽는 방법을 살펴보았습니다. 설명된 단계를 따르면 프로그래밍 방식으로 프로젝트 파일에서 통화 관련 정보를 손쉽게 추출하여 Java 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### Q: Aspose.Tasks는 모든 버전의 Microsoft Project와 호환됩니까?
A: Aspose.Tasks는 MS Project 2003-2021에서 생성된 MPP 파일을 포함하여 다양한 버전의 Microsoft Project를 지원합니다.
### Q: Aspose.Tasks를 사용하여 통화 속성을 수정할 수 있나요?
A: 예, Aspose.Tasks를 사용하면 프로그래밍 방식으로 MS 프로젝트 파일의 통화 속성을 읽고 수정할 수 있습니다.
### Q: Aspose.Tasks는 상업용으로 적합한가요?
 A: 예, Aspose.Tasks는 전문가용으로 설계된 상용 라이브러리입니다. 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).
### Q: Aspose.Tasks는 무료 평가판을 제공합니까?
 A: 예, Aspose의 무료 평가판을 이용할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Tasks에 대한 도움이나 지원은 어디서 구할 수 있나요?
 A: Aspose.Tasks 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15) 도움이나 문의사항이 있으면
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
