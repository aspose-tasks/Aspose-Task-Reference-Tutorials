---
date: 2025-12-31
description: Aspose.Tasks for Java를 사용하여 프로젝트 시작 날짜를 설정하고, 프로젝트 정보를 작성하며, 프로젝트를 XML로
  저장하는 방법을 배웁니다.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java를 사용하여 MS Project에서 프로젝트 시작 날짜 설정
url: /ko/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project에서 Aspose.Tasks for Java를 사용하여 프로젝트 시작일 설정하기

## 소개
이 튜토리얼에서는 **프로젝트 시작일 설정**하고 Aspose.Tasks for Java를 추가로 사용하여 MS 프로젝트 정보를 작성하는 방법을 알아봅니다. 프로젝트 작업 계획, 업무 생성, 또는 프로젝트 데이터를 더 큰 시스템에 통합할 때, 프로그래밍 방식으로 시작일을 제어하면 일정에 대한 제어가 가능해집니다. 환경 설정부터 업데이트된 프로젝트를 XML 파일로 저장하는 단계까지 차근차근 축하하므로 바로 적용할 수 있습니다.

## 빠른 답변
- **프로젝트를 처리하는 주요 클래스는?** Aspose.Tasks그룹의 `Project`.
- **프로젝트 시작일은 어떻게 조작됐나요?** `project.set(Prj.START_DATE, <date>)`를 사용합니다.
- **상태 데이트도 접근할 수 없나요?** 네, `project.set(Prj.STATUS_DATE, <date>)`로 설정합니다.
- **프로젝트를 어떤 형식으로 해야 할까요?** `SaveFileFormat.Xml`을 사용하여 XML로 작성합니다.
- **프로덕션 규모가 필요한가요?** 전체 기능을 사용하려면 Aspose.Tasks가 필요합니다.

## **프로젝트 시작일 설정**이란 무엇인가요?
프로젝트 시작일을 설정한다는 것은 모든 작업이 시작되는 기준을 정의하는 것입니다. 작업기간, 외곽성, 그리고 중요한 경로와 이동의 기준점입니다. 프로그래밍 날짜를 설정하면 여러 프로젝트 파일을 일관성 있게 유지하고 매뉴얼을 입력할 수 없습니다.

## 프로젝트 정보를 작성하기 위해 Java용 Aspose.Tasks를 사용하는 이유는 무엇입니까?
- **전체 API 적용 범위:** Microsoft Project를 설치하지 않고 모든 프로젝트 속성을 이해하고 수정하고 더 이상 사용할 수 없습니다.
- **크로스 플랫폼:** Windows, Linux, macOS에서 동작합니다.
- **자동화 지원:** 배치 처리, CI라인 파이프, 혹은 앞으로 프로젝트 일정을 생성하는 백엔드 서비스에 아쉽습니다.

## 전제 조건
시작하기 전에 다음 항목을 준비하시기 바랍니다:

1. **JDK(Java Development Kit)** – 최신 버전(8 이상 추천).
2. **Aspose.Tasks for Java 라이브러리** – [여기](https://releases.aspose.com/tasks/java/)에서 다운로드하세요.
3. **IDE** – IntelliJ IDEA, Eclipse 또는 선호하는 Java 편집기.

## 패키지 가져오기
먼저 Java 프로젝트에 필요한 패키지를 import합니다.
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 1단계: 데이터 디렉터리 설정
프로젝트 데이터가 저장될 디렉터리를 정의합니다.
```java
String dataDir = "Your Data Directory";
```

## 2단계: 프로젝트 인스턴스 생성
새 프로젝트 인스턴스를 초기화합니다.
```java
Project project = new Project();
```

## 3단계: 프로젝트 정보 속성 설정
여기서는 **프로젝트 시작일**, 시작부터 일정, 상태 날짜를 설정합니다—주요 키워드 *write project information*와 *how to set status*를 모두 포함합니다.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## 4단계: 프로젝트를 XML 파일로 저장
마지막으로 업데이트된 프로젝트 파일을 저장합니다. 이는 보조 키워드 **save project as xml**을 보여줍니다.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 일반적인 문제 및 해결 방법
| 이슈 | 이유 | 수정 |
|-------|---------|-----|
| **잘못된 시작 날짜** | Java에서는 달이 0부터 시작합니다. | 예시와 같이 `Calendar.JULY`를 사용하거나 월등한 경우에는 1을 더 권장하십시오. |
| **파일이 저장되지 않음** | `dataDir`이 존재하지 않습니다. 등록 권한이 없습니다. | 출력을 미리 생성하거나 출력할 수 있도록 선택하세요. |
| **라이센스 경고** | 이를 실행하면 워터마크가 추가됩니다. | `프로젝트`를 만들기 전에 Aspose.Tasks를 적용하십시오. |

## FAQ
### Q: Aspose.Tasks for Java를 사용하여 MS Project 파일을 받을 수 있나요?
A: 네, Aspose.Tasks for Java는 MS Project 파일을 참조하여 작성 기능을 제공합니다.
### Q: Aspose.Tasks for Java는 MS Project와 호환되나요?
A: 물론입니다. Aspose.Tasks for Java에는 MS 프로젝트 파일 형식의 다양한 버전이 지원되므로 호환성을 갖습니다.
### Q: Aspose.Tasks for Java 체험판에 제한이 있나요?
A: 시험판으로 서버 기능을 수행할 수 있지만, 출력 파일에 워터마크가 삽입되는 등 일부 제한이 있습니다.
### Q: Aspose.Tasks for Java에 대한 지원을 어떻게 받을 수 있나요?
A: Aspose.Tasks 커뮤니티 도어에서 도움을 받을 수 있는 곳은 [여기](https://forum.aspose.com/c/tasks/15)입니다.
### Q: Aspose.Tasks for Java 임시 전력을 구매할 수 있습니까?
A: 네, 단기 사용을 임시 권력을 제공하며 [여기](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.

## 결론
이제 **프로젝트 시작일을 설정**하고, 필수 프로젝트 정보를 작성하며, **XML 형식으로 프로젝트를 생성**하는 방법을 배웠습니다. 이러한 기본 요소들을 활용하면 프로젝트 관리 플로를 자동화하고, 작업 작업을 생성하며, MS 프로젝트 데이터를 Java에 통합할 수 있습니다.

---

**최종 업데이트:** 2025-12-31
**테스트 대상:** Java 24.12용 Aspose.Tasks
**저자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}