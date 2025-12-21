---
date: 2025-12-21
description: Aspose.Tasks for Java를 사용하여 프로젝트를 만들고 새 작업에 대한 MS Project 속성을 설정하는 방법을
  배우고, 프로젝트를 XML로 저장하고 작업 속성을 사용자 지정하는 방법을 포함합니다.
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 프로젝트 생성 방법 – Aspose.Tasks로 새 작업 속성 설정
url: /ko/java/project-file-operations/set-attributes-new-tasks/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프로젝트 만들기 – Aspose.Tasks로 새 작업 속성 설정

## 소개
이 포괄적인 가이드에서는 Aspose.Tasks Java 라이브러리를 사용하여 **프로젝트 만들기** 파일을 만들고 새 작업에 대한 Microsoft Project 속성을 설정하는 방법을 알아봅니다. 개발 환경을 준비하는 단계부터 프로젝트를 XML 파일로 저장하는 단계까지 차근차근 안내하므로 **작업 속성 맞춤화**를 쉽게 수행하고 프로젝트 관리 워크플로를 효율화할 수 있습니다.

## 빠른 답변
- **튜토리얼은 무엇을 다루나요?** 새 작업에 대한 기본 시작 날짜를 설정하고 프로젝트를 XML로 저장합니다.  
- **필요한 라이브러리는?** Aspose.Tasks for Java.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **다른 작업 기본값을 변경할 수 있나요?** 예, Aspose.Tasks를 사용하면 많은 작업 수준 기본값을 수정할 수 있습니다.  
- **사용되는 출력 형식은?** XML (SaveFileFormat.Xml).

## Aspose.Tasks에서 프로젝트란?
*프로젝트*는 Microsoft Project 파일을 그대로 반영하는 객체 모델입니다. 작업, 리소스, 캘린더 및 기타 일정 데이터를 저장하며, 프로그래밍 방식으로 프로젝트 파일을 읽고, 수정하고, 생성할 수 있게 합니다.

## 작업 기본값을 설정하는 이유
새 작업의 시작 날짜와 같은 기본값을 설정하면 전체 계획에서 일관성을 유지할 수 있습니다. 각 작업을 수동으로 업데이트하는 번거로움을 없애고 일정 오류 위험을 줄여줍니다.

## 사전 요구 사항
1. **Java 개발 환경** – Java 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [download link](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **IDE** – Eclipse, IntelliJ IDEA 또는 Java 호환 편집기.

## 패키지 가져오기
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## 프로젝트 만들기 – 새 작업 속성 설정
### 단계 1: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 출력 파일을 저장하려는 절대 경로로 교체합니다.

### 단계 2: Project 인스턴스 생성
```java
Project prj = new Project();
```
이 코드는 사용자 정의를 위해 빈 프로젝트를 생성합니다.

### 단계 3: 새 작업 속성 설정
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
위 코드는 Aspose.Tasks에 이후에 추가하는 모든 작업의 시작 날짜를 **현재 날짜**로 지정하도록 지시합니다.

### 단계 4: 프로젝트 저장
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
여기서는 **프로젝트를 XML로 저장**합니다. 이는 교환 및 추가 처리에 널리 지원되는 형식입니다.

### 단계 5: 결과 표시
```java
System.out.println("Project file generated Successfully");
```
간단한 콘솔 메시지가 파일이 오류 없이 생성되었음을 확인합니다.

## 작업 속성 설정 방법
시작 날짜 외에도 `Prj` 열거형을 사용하여 기간, 캘린더, 우선순위와 같은 다른 기본 작업 설정을 수정할 수 있습니다. 이러한 유연성을 통해 **작업 속성 맞춤화**를 조직 표준에 맞출 수 있습니다.

## 프로젝트를 XML로 저장하는 방법
XML로 저장하면 전체 프로젝트 구조를 유지하면서 파일을 사람이 읽기 쉬운 형태로 보존합니다. 다른 도구와의 통합, 버전 관리, 자동 파이프라인에 이상적입니다.

## 일반적인 문제 및 해결책
- **잘못된 데이터 디렉터리 경로** – 폴더가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인합니다.  
- **라이선스를 찾을 수 없음** – 평가 워터마크를 방지하려면 `Project` 객체를 만들기 전에 Aspose.Tasks 라이선스를 로드합니다.  
- **예상치 못한 시작 날짜** – 설정 후 다른 코드가 `Prj.NEW_TASK_START_DATE`를 덮어쓰지 않는지 확인합니다.

## FAQ
### Q: Aspose.Tasks for Java를 사용하여 기존 프로젝트 파일을 조작할 수 있나요?
A: 예, Aspose.Tasks for Java는 기존 프로젝트 파일을 읽고, 수정하고, 다양한 형식으로 저장하는 등 광범위한 기능을 제공합니다.

### Q: Aspose.Tasks for Java에 대한 문서 및 리소스를 어디서 찾을 수 있나요?
A: [Aspose.Tasks for Java documentation page](https://reference.aspose.com/tasks/java/)에서 문서와 리소스를 확인할 수 있습니다.

### Q: Aspose.Tasks for Java의 무료 체험판이 있나요?
A: 예, [here](https://releases.aspose.com/)에서 Aspose.Tasks for Java 무료 체험판을 다운로드할 수 있습니다.

### Q: Aspose.Tasks for Java의 임시 라이선스를 어떻게 받을 수 있나요?
A: Aspose.Tasks for Java의 임시 라이선스는 [temporary license page](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

### Q: Aspose.Tasks for Java와 관련된 문제나 문의에 대한 지원은 어디서 받을 수 있나요?
A: [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15)에서 지원을 받고 커뮤니티와 소통할 수 있습니다.

**Additional Q&A**

**Q: 프로젝트 생성 후 기본 시작 날짜를 변경할 수 있나요?**  
A: 예, 새 작업을 추가하기 전 언제든지 `prj.set(Prj.NEW_TASK_START_DATE, ...)`를 호출하여 변경할 수 있습니다.

**Q: XML로 저장하면 대형 프로젝트의 성능에 영향을 미치나요?**  
A: XML은 텍스트 기반이므로 파일 크기가 바이너리 형식보다 클 수 있지만, 대부분의 일반적인 프로젝트 규모에서는 여전히 빠릅니다.

**Q: 전역적으로 설정할 수 있는 다른 작업 기본값이 있나요?**  
A: 물론입니다 – `NEW_TASK_DURATION`, `NEW_TASK_COST`, `NEW_TASK_PRIORITY`와 같은 속성도 `Prj` 열거형을 통해 전역 설정이 가능합니다.

## 결론
이제 Aspose.Tasks for Java를 사용하여 **프로젝트 만들기** 파일을 생성하고, 새 작업의 기본 시작 날짜를 설정하며, **프로젝트를 XML로 저장**하는 방법을 배웠습니다. 이러한 단계를 숙달하면 **작업 속성 맞춤화**를 손쉽게 수행하여 모든 프로젝트 관리 상황에 적용할 수 있어 일관성을 높이고 소중한 시간을 절약할 수 있습니다.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}