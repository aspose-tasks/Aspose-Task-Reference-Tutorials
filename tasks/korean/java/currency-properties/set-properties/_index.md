---
title: Aspose.Tasks 프로젝트에서 통화 속성 설정
linktitle: Aspose.Tasks 프로젝트에서 통화 속성 설정
second_title: Aspose.Tasks 자바 API
description: Java를 사용하여 Aspose.Tasks 프로젝트에서 통화 속성을 설정하는 방법을 알아보세요. Microsoft Project 파일을 쉽게 조작할 수 있습니다.
weight: 11
url: /ko/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 프로젝트에서 통화 속성 설정

## 소개
이 튜토리얼에서는 Java를 사용하여 Aspose.Tasks 프로젝트에서 통화 속성을 설정하는 방법을 살펴보겠습니다. Aspose.Tasks는 개발자가 Microsoft Project 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 Java 라이브러리입니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Tasks for Java 라이브러리: 다음에서 Aspose.Tasks for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/tasks/java/).
3. 통합 개발 환경(IDE): Eclipse 또는 IntelliJ IDEA와 같이 선호하는 IDE를 선택하세요.
## 패키지 가져오기
먼저 Java에서 Aspose.Tasks를 사용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## 1단계: 데이터 디렉터리 설정
프로젝트 파일이 있는 데이터 디렉터리를 설정합니다.
```java
String dataDir = "Your Data Directory";
```
## 2단계: 프로젝트 인스턴스 생성
Aspose.Tasks를 사용하여 새 프로젝트 인스턴스를 만듭니다.
```java
Project project = new Project();
```
## 3단계: 통화 속성 설정
이제 프로젝트의 통화 속성을 설정해 보겠습니다.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## 4단계: 프로젝트 저장
업데이트된 통화 속성으로 프로젝트를 저장합니다.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## 5단계: 완료 메시지 표시
프로세스가 성공적으로 완료되었음을 나타내는 메시지를 표시합니다.
```java
System.out.println("Process completed Successfully");
```
축하해요! Java를 사용하여 Aspose.Tasks 프로젝트에서 통화 속성을 성공적으로 설정했습니다.
## 결론
이 튜토리얼에서는 Java용 Aspose.Tasks를 사용하여 프로젝트 파일에서 통화 속성을 설정하는 방법을 배웠습니다. Aspose.Tasks를 사용하면 개발자는 프로젝트 데이터를 효율적으로 조작할 수 있으므로 프로젝트 관리 애플리케이션을 위한 유용한 도구가 됩니다.
## FAQ
### Aspose.Tasks를 사용하여 단일 프로젝트에 여러 통화를 설정할 수 있나요?
예, Aspose.Tasks를 사용하면 단일 프로젝트 파일 내에서 여러 통화를 처리할 수 있습니다.
### Aspose.Tasks는 다른 버전의 Microsoft Project 파일과 호환됩니까?
예, Aspose.Tasks는 다양한 버전의 Microsoft Project 파일을 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Aspose.Tasks는 사용자 정의 통화 형식을 지원합니까?
물론 Aspose.Tasks는 특정 프로젝트 요구 사항을 충족하기 위해 사용자 정의 통화 형식을 정의하는 유연성을 제공합니다.
### Aspose.Tasks를 다른 Java 라이브러리 또는 프레임워크와 통합할 수 있나요?
예, Aspose.Tasks는 다른 Java 라이브러리 및 프레임워크와 원활하게 통합되어 기능과 다양성을 향상시킬 수 있습니다.
### Aspose.Tasks에 대한 추가 지원은 어디에서 찾을 수 있나요?
 추가 지원을 받으려면 다음을 방문하세요.[Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)에서 유용한 리소스를 찾고 커뮤니티에 참여할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
