---
date: 2026-01-05
description: Aspose.Tasks for Java를 사용하여 프로젝트 시작 날짜를 설정하고 MS Project XML을 저장하는 방법을
  배웁니다. Java 개발자를 위한 단계별 가이드.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 프로젝트 시작 날짜 설정
url: /ko/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java로 프로젝트 시작 날짜 설정

## 소개
이 튜토리얼에서는 Microsoft Project 파일에서 **프로젝트 시작 날짜를 설정하는 방법**과 Aspose.Tasks for Java 라이브러리를 사용하여 **MS Project XML을 저장하는 방법**을 배웁니다. 보고 파이프라인을 자동화하거나 맞춤형 프로젝트 관리 도구를 구축하든, 이 작업을 숙달하면 시간을 절약하고 수동 오류를 없앨 수 있습니다.

## 빠른 답변
- **시작 날짜를 설정하는 기본 메서드는 무엇인가요?** `project.set(Prj.START_DATE, …)`를 사용합니다.  
- **파일을 내보낼 때 어떤 형식을 사용해야 하나요?** `SaveFileFormat.Xml`으로 XML 형식으로 저장합니다.  
- **이 작업에 라이선스가 필요합니까?** 체험판도 동작하지만, 정식 라이선스를 사용하면 워터마크가 제거됩니다.  
- **작업을 만든 후에도 시작 날짜를 변경할 수 있나요?** 예, 작업을 추가하기 전에 프로젝트 속성을 업데이트하면 됩니다.  
- **모든 MS Project 버전과 호환되나요?** Aspose.Tasks는 XML, MPP 등 다양한 형식을 지원합니다.

## “프로젝트 시작 날짜 설정”이란?
프로젝트 시작 날짜를 설정하면 모든 작업 일정 계산이 시작되는 기준 캘린더가 정의됩니다. 이는 신뢰할 수 있는 프로젝트 일정을 프로그래밍 방식으로 구축하는 첫 번째 단계입니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
Aspose.Tasks는 Microsoft Project가 설치되지 않은 환경에서도 작동하는 순수 Java API를 제공합니다. 프로젝트 데이터를 빠르게 생성, 수정 및 내보낼 수 있어 서버‑사이드 자동화에 최적입니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – 최신 JDK 버전 중 하나.  
2. **Aspose.Tasks for Java** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드.  
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java IDE.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 단계 1: 데이터 디렉터리 설정
생성된 파일을 저장할 위치를 정의합니다.

```java
String dataDir = "Your Data Directory";
```

### 단계 2: 프로젝트 인스턴스 생성
새로운 빈 프로젝트를 인스턴스화합니다.

```java
Project project = new Project();
```

### 단계 3: 프로젝트 정보 속성 설정
여기서 **프로젝트 시작 날짜**와 관련 일정 속성을 설정합니다.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 단계 4: MS Project XML 저장
구성된 프로젝트를 XML 파일로 내보냅니다.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결책
- **날짜 형식 오류:** `java.util.Calendar`를 사용하고 할당 전에 `getTime()`을 호출했는지 확인하세요.  
- **파일이 저장되지 않음:** `dataDir`이 존재하고 쓰기 가능한 폴더를 가리키는지 확인하세요.  
- **라이선스 경고:** 체험판은 워터마크를 추가합니다. 정식 라이선스를 적용하면 제거됩니다.

## 자주 묻는 질문

### Q: Aspose.Tasks for Java를 사용해 MS Project 파일을 읽을 수 있나요?  
**A:** 예, Aspose.Tasks for Java는 MS Project 파일을 읽고 쓰는 강력한 기능을 제공합니다.

### Q: Aspose.Tasks for Java는 다양한 MS Project 버전과 호환되나요?  
**A:** 물론입니다. Aspose.Tasks for Java는 여러 MS Project 형식을 지원하여 폭넓은 호환성을 보장합니다.

### Q: Aspose.Tasks for Java 체험판에 제한이 있나요?  
**A:** 체험판을 사용하면 라이브러리를 탐색할 수 있지만 출력 파일에 워터마크가 추가됩니다.

### Q: Aspose.Tasks for Java에 대한 지원은 어떻게 받을 수 있나요?  
**A:** Aspose.Tasks 커뮤니티 포럼 [여기](https://forum.aspose.com/c/tasks/15)에서 도움을 받을 수 있습니다.

### Q: Aspose.Tasks for Java의 임시 라이선스를 구매할 수 있나요?  
**A:** 예, 단기 사용을 위한 임시 라이선스를 제공합니다. 자세한 내용은 [여기](https://purchase.aspose.com/temporary-license/)에서 확인하세요.

### Q: XML로 저장하면 사용자 정의 필드가 보존되나요?  
**A:** 네, `SaveFileFormat.Xml`로 저장하면 모든 사용자 정의 속성과 확장 필드가 유지됩니다.

### Q: 작업을 추가한 후에도 시작 날짜를 변경할 수 있나요?  
**A:** 저장하기 전 언제든지 시작 날짜를 업데이트할 수 있습니다. 다시 `project.set(Prj.START_DATE, …)`를 호출하면 됩니다.

**마지막 업데이트:** 2026-01-05  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}