---
date: 2026-01-13
description: Aspose.Tasks for Java를 사용하여 사용자 정의 속성을 만들고, Microsoft Project 파일을 로드하고,
  숫자 값을 설정한 다음 프로젝트를 XML로 저장하는 방법을 배웁니다.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MS Project에서 사용자 지정 속성 만들기
url: /ko/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project에서 Aspose.Tasks를 사용하여 사용자 정의 속성 만들기

## 소개
이 튜토리얼에서는 **Aspose.Tasks for Java**를 사용하여 Microsoft Project 파일의 리소스에 **사용자 정의 속성**을 만드는 방법을 알아봅니다. Microsoft Project 파일을 로드하고, 새로운 숫자형 속성을 정의하고, 값을 할당한 뒤, 프로젝트를 XML 형식으로 저장하는 과정을 단계별로 진행합니다. 끝까지 따라오시면 직접 프로젝트 관리 솔루션에 적용할 수 있는 실용적인 예제를 얻게 됩니다.

## 빠른 답변
- **“사용자 정의 속성”이란?**  
  리소스나 작업에 추가 정보를 저장하기 위해 사용자가 정의하는 필드(예: 연령, 기술 수준)입니다.  
- **어떤 라이브러리를 사용하나요?**  
  Aspose.Tasks for Java가 유창한 API를 제공하여 사용자 정의 속성을 생성·관리합니다.  
- **라이선스가 필요합니까?**  
  평가용으로는 무료 임시 라이선스로 충분하지만, 실제 운영 환경에서는 정식 라이선스가 필요합니다.  
- **숫자 값을 설정할 수 있나요?**  
  네 – `setNumericValue`와 `BigDecimal`(예: `30.5345`)을 사용합니다.  
- **프로젝트는 어떻게 저장하나요?**  
  수정된 파일은 `SaveFileFormat.Xml`을 사용해 XML 형식으로 저장할 수 있습니다.

## 사용자 정의 속성이란?
**사용자 정의 속성**(확장 속성이라고도 함)은 Microsoft Project의 리소스 또는 작업에 추가할 수 있는 열입니다. 기본 필드에 포함되지 않은 데이터(예: 직원 연령, 인증 수준, 비즈니스 전용 지표 등)를 캡처할 수 있습니다.

## MS Project에서 사용자 정의 속성을 만들어야 하는 이유
- **프로젝트 데이터를 조직에 맞게 맞춤화**합니다.  
- **고급 보고**를 가능하게 하여 나중에 값을 조회할 수 있습니다.  
- **여러 프로젝트에 일관성**을 유지하도록 동일한 속성 정의를 프로그래밍 방식으로 적용할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요.

1. **Java 개발 환경** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 최신 버전을 [here](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE** – Eclipse, IntelliJ IDEA 또는 Java를 지원하는 기타 IDE.

## 단계별 가이드

### 패키지 가져오기
먼저 프로젝트와 리소스, 확장 속성을 다루는 데 필요한 Aspose.Tasks 클래스를 가져옵니다.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### 단계 1: 데이터 디렉터리 정의
소스 프로젝트 파일이 위치한 폴더와 출력 파일이 저장될 폴더를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 2: Microsoft Project 파일 로드
기존 파일을 로드하여 `Project` 인스턴스를 생성합니다. 이 단계가 **Microsoft 프로젝트 파일 로드**이며, 파일 내용에 완전하게 접근할 수 있게 해줍니다.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### 단계 3: 사용자 정의 속성 정의
새로운 숫자형 속성 **Age**를 정의합니다. API는 정의가 이미 존재하는지 확인하고, 없으면 새로 생성합니다.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### 단계 4: Java에서 숫자 값 설정
특정 리소스에 대한 속성 인스턴스를 만들고 `setNumericValue`를 사용해 숫자 값을 할당합니다. 이는 **set numeric value java**가 실제로 동작하는 예시입니다.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### 단계 5: 리소스 추가 및 사용자 정의 속성 연결
새 리소스 **R1**을 추가하고 앞서 만든 사용자 정의 속성을 연결합니다.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### 단계 6: 프로젝트를 XML로 저장
변경 사항을 영구히 저장하기 위해 프로젝트를 저장합니다. 이는 **save project as xml** 단계이며, 업데이트된 파일의 깔끔한 XML 표현을 생성합니다.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### 단계 7: 결과 표시
프로세스가 오류 없이 완료되었음을 알리는 친절한 확인 메시지를 출력합니다.

```java
System.out.println("Process completed Successfully");
```

위 단계를 따라 하면 **사용자 정의 속성**을 성공적으로 만들고, Microsoft Project 파일을 로드한 뒤, Java에서 숫자 값을 설정하고, 프로젝트를 XML로 저장할 수 있습니다.

## 흔히 발생하는 문제와 팁
- **속성 ID 충돌**: 새 정의를 만들기 전에 `getById`를 호출해 중복 ID가 없는지 항상 확인하세요.  
- **정밀도 처리**: `BigDecimal`은 소수점 정밀도를 보존합니다. 정확한 값을 위해 `float`나 `double` 대신 사용하세요.  
- **파일 경로**: 절대 경로를 사용하거나 IDE 작업 디렉터리를 올바르게 설정해 `FileNotFoundException`을 방지하세요.

## 자주 묻는 질문

**Q: 작업에도 사용자 정의 속성을 만들 수 있나요?**  
A: 네 – 속성을 정의할 때 `ExtendedAttributeTask`를 사용하면 작업에 적용할 수 있습니다.

**Q: 한 번에 여러 사용자 정의 속성을 추가할 수 있나요?**  
A: 가능합니다. 각 속성마다 별도의 `ExtendedAttributeDefinition` 객체를 생성하고 원하는 리소스 또는 작업에 연결하면 됩니다.

**Q: 프로젝트를 어떤 형식으로 저장할 수 있나요?**  
A: Aspose.Tasks는 XML, MPP 외에도 PDF, HTML 등 여러 형식을 지원합니다. 이 예제에서는 `SaveFileFormat.Xml`을 사용했습니다.

**Q: 개발 빌드에도 Aspose.Tasks 라이선스가 필요합니까?**  
A: 평가용 임시 라이선스로 충분합니다. 실제 운영 환경에서는 정식 라이선스가 필요합니다.

**Q: 나중에 사용자 정의 속성 값을 어떻게 읽어올 수 있나요?**  
A: `resource.getExtendedAttributes()`를 사용해 연결된 속성을 순회하고, `getNumericValue()` 또는 `getTextValue()`로 값을 가져올 수 있습니다.

## 결론
Aspose.Tasks for Java를 이용해 Microsoft Project에 **사용자 정의 속성**을 만드는 과정은 간단합니다. 프로젝트를 로드하고, 속성을 정의하고, 값을 설정하고, 리소스에 연결한 뒤 파일을 저장하면 됩니다. 이 방법을 통해 프로젝트 데이터 모델을 프로그래밍 방식으로 확장하여 보다 풍부한 보고와 비즈니스 프로세스와의 긴밀한 연동이 가능해집니다.

---

**마지막 업데이트:** 2026-01-13  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}