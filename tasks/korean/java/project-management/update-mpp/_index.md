---
date: 2025-12-28
description: Aspose.Tasks for Java, 자바 프로젝트 관리 라이브러리를 사용하여 작업을 추가하고 MPP 파일을 업데이트하는
  방법을 배워보세요. 단계별 가이드를 따라 MPP 파일에 작업을 생성하고 프로젝트를 MPP 형식으로 저장하세요.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 작업 추가 및 MPP 파일 업데이트 방법
url: /ko/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 작업 추가 및 MPP 파일 업데이트 방법

## 소개
이 튜토리얼에서는 **작업 추가 방법**과 Aspose.Tasks for Java를 사용하여 MPP 파일을 업데이트하는 방법을 보여드립니다. Aspose.Tasks는 선도적인 **java 프로젝트 관리 라이브러리**입니다. 맞춤형 스케줄러를 구축하거나 기존 프로젝트 계획을 프로그래밍 방식으로 수정해야 할 경우, 이 가이드는 파일을 로드하는 단계부터 변경 사항을 새로운 MPP 문서로 저장하는 단계까지 모든 과정을 안내합니다.

## 빠른 답변
- **“작업 추가 방법”이 이 문맥에서 의미하는 바는 무엇인가요?** 기존 Microsoft Project (MPP) 파일 내부에 새로운 작업을 프로그래밍 방식으로 생성하는 것을 의미합니다.  
- **어떤 라이브러리가 이 작업을 처리하나요?** Aspose.Tasks for Java, 강력한 java 프로젝트 관리 라이브러리.  
- **라이선스가 필요합니까?** 개발용으로는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **결과를 MPP 형식으로 저장할 수 있나요?** 예—`project.save(..., SaveFileFormat.Mpp)`를 사용하여 **프로젝트를 mpp로 저장**합니다.  
- **필요한 Java 버전은 무엇인가요?** Java 8 이상.

## MPP 파일에서 “작업 추가 방법”이란?
작업을 추가한다는 것은 프로젝트 계층 구조에 새로운 작업 항목을 삽입하고, 시작/종료 날짜를 정의한 뒤, 변경 내용을 MPP 파일에 저장하는 것을 의미합니다. Aspose.Tasks는 저수준 파일 형식 세부 사항을 추상화하여 비즈니스 로직에 집중할 수 있게 해줍니다.

## 왜 Aspose.Tasks for Java를 사용하나요?
- **전체 호환성**: Microsoft Project 2007‑2021 파일과 호환됩니다.  
- **COM 또는 Office 설치 불필요**—순수 Java API.  
- **풍부한 기능 세트**: 작업 연결, 리소스 할당, 사용자 정의 필드 등.  
- **고성능**: 대형 프로젝트 파일에서도 뛰어나며 서버‑사이드 자동화에 이상적입니다.

## 사전 요구 사항
1. **Java 개발 환경** – JDK 8 이상이 설치되고 구성되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – [다운로드 페이지](https://releases.aspose.com/tasks/java/)에서 다운로드합니다.  
3. **기본 Java 지식** – 클래스, 객체 및 날짜 처리에 익숙해야 합니다.  

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다. 이를 통해 프로젝트 조작, 작업 속성 및 날짜 처리를 사용할 수 있습니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 단계 1: 데이터 디렉터리 정의
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"`를 소스 MPP 파일이 위치한 절대 경로로 교체합니다.

## 단계 2: 기존 프로젝트 읽기
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
`Project` 생성자는 **SampleMSP2010.mpp**를 로드하여 조작 가능한 객체 모델을 제공합니다.

## 단계 3: 새 작업 생성 (작업 추가 방법)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
이 코드는 루트 작업에 *Task1*이라는 자식 작업을 추가하여 **MPP에 작업을 생성**합니다.

## 단계 4: 시작 및 종료 날짜 설정
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
여기서는 새로 추가된 작업의 일정을 정의합니다. 프로젝트 일정에 맞게 날짜를 조정하세요.

## 단계 5: 프로젝트 저장 (프로젝트를 mpp로 저장)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
새 작업이 포함된 업데이트된 프로젝트가 **AfterLinking.mpp** 파일로 저장됩니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **파일을 찾을 수 없음** | `dataDir`이 경로 구분자(`/` 또는 `\\`)로 끝나는지, 파일 이름이 정확한지 확인하세요. |
| **날짜 오류** | `Calendar`의 월은 0부터 시작한다는 점을 기억하세요; `Calendar.JULY`는 7월을 의미합니다. |
| **라이선스 예외** | 평가용 워터마크를 방지하려면 API 호출 전에 유효한 Aspose.Tasks 라이선스를 설치하세요. |

## FAQ
### Q: Aspose.Tasks for Java가 복잡한 프로젝트 구조를 처리할 수 있나요?
A: 예, Aspose.Tasks for Java는 복잡한 프로젝트 구조를 효율적으로 처리할 수 있는 강력한 기능을 제공합니다.  
### Q: Aspose.Tasks for Java의 무료 체험판을 이용할 수 있나요?
A: 예, [웹사이트](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.  
### Q: Aspose.Tasks for Java가 다양한 버전의 Microsoft Project 파일을 지원하나요?
A: 물론입니다. Aspose.Tasks for Java는 MPP, MPT, XML 형식을 포함한 다양한 버전의 Microsoft Project 파일을 지원합니다.  
### Q: Aspose.Tasks for Java의 임시 라이선스를 받을 수 있나요?
A: 예, 테스트 용도로 임시 라이선스를 제공하고 있습니다. [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.  
### Q: Aspose.Tasks for Java에 대한 도움이나 지원을 어디서 받을 수 있나요?
A: 도움이나 문의 사항이 있으면 [Aspose.Tasks 포럼](https://forum.aspose.com/c/tasks/15)을 방문하세요.

## 자주 묻는 질문
**Q: 여러 작업을 한 번에 추가하려면 어떻게 해야 하나요?**  
A: 작업 이름 컬렉션을 순회하면서 루프 안에서 “작업 생성” 블록을 반복합니다.

**Q: 새 작업에 사용자 정의 필드를 설정할 수 있나요?**  
A: 예—`task.set(Tsk.CUSTOM_FIELD_x, value)`를 사용하며, *x*는 필드 인덱스입니다.

**Q: 기존 작업을 템플릿으로 복사할 수 있나요?**  
A: 소스 작업을 복제(`Task cloned = sourceTask.clone();`)한 뒤 원하는 상위 작업에 추가합니다.

**Q: 새 작업을 추가하는 대신 기존 작업을 업데이트해야 하면 어떻게 해야 하나요?**  
A: ID로 작업을 가져와(`Task existing = project.getRootTask().getChildren().getById(id);`) 속성을 수정합니다.

**Q: Aspose.Tasks가 PDF나 PNG와 같은 다른 형식으로 저장을 지원하나요?**  
A: 예—`project.save("output.pdf", SaveFileFormat.Pdf);` 또는 시각적 표현을 위해 `SaveFileFormat.Png`를 사용합니다.

**마지막 업데이트:** 2025-12-28  
**테스트 환경:** Aspose.Tasks for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}