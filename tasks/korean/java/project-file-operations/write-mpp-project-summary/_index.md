---
date: 2026-03-29
description: Aspose.Tasks for Java를 사용하여 MPP 프로젝트에서 키워드와 생성 날짜를 설정하는 방법을 배웁니다. 코드
  예제가 포함된 단계별 가이드.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 MPP 프로젝트 요약에 키워드 설정하는 방법
url: /ko/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks를 사용한 MPP 프로젝트 요약에 키워드 설정 방법

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 MPP 프로젝트 파일에 **키워드 설정 방법** 및 기타 요약 정보를 설정하는 방법을 알아봅니다. 작성자 정보, 개정 번호 또는 사용자 지정 생성 날짜를 삽입해야 할 경우, 이 가이드는 실행 가능한 코드와 함께 정확한 단계별 절차를 안내합니다. 최종적으로 키워드를 설정하고, set creation date java를 설정하며, 파일에서 데이터를 다시 가져올 수 있게 됩니다.

## 빠른 답변
- **어떤 라이브러리를 사용합니까?** Aspose.Tasks for Java  
- **주된 목적은?** MPP 파일에 키워드, 작성자 정보 및 생성 날짜 설정  
- **코드 단계는 몇 개입니까?** 초기화, 저장, 읽기 세 개의 간단한 코드 블록  
- **라이선스가 필요합니까?** 개발용 무료 체험판으로 가능하지만, 운영 환경에서는 상용 라이선스 필요  
- **지원되는 Java 버전?** Java 8 이상  

## MPP 파일에서 “키워드 설정 방법”이란?
키워드는 Microsoft Project (MPP) 파일 내부에 저장되는 메타데이터 필드입니다. 프로젝트를 분류하고 빠른 검색을 가능하게 하며, 하위 도구에 대한 컨텍스트 정보를 제공합니다. Aspose.Tasks는 `Prj.KEYWORDS` 속성을 제공하여 이 값을 프로그래밍 방식으로 쉽게 쓰거나 업데이트할 수 있게 합니다.

## 키워드 및 생성 날짜를 설정하기 위해 Aspose.Tasks for Java를 사용하는 이유
* **Full .MPP compatibility** – 모든 Project 2007‑2023 형식과 호환됩니다.  
* **No COM or Office installation required** – 순수 Java 기반으로 서버‑사이드 환경에 최적화되었습니다.  
* **Rich API** – 키워드 외에도 작성자, 개정, 주석 및 날짜를 한 번에 설정할 수 있습니다.  
* **Performance‑optimized** – 대용량 프로젝트 파일에서도 빠른 읽기/쓰기 성능을 제공합니다.

## 전제 조건
1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Tasks for Java** – 최신 JAR 파일을 [here](https://releases.aspose.com/tasks/java/)에서 다운로드하십시오.  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans 또는 선호하는 편집기.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 이 임포트를 통해 `Project` 객체, 요약 필드용 `Prj` 열거형, 저장 형식 지정용 `SaveFileFormat` 열거형에 접근할 수 있습니다.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 단계 1: 프로젝트 설정 및 요약 정보 정의
`Project` 인스턴스를 생성한 뒤 `set` 메서드를 사용해 원하는 메타데이터를 기록합니다. `Calendar` 객체를 이용해 **키워드**와 **set creation date java**를 설정하는 방법을 확인하세요.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## 단계 2: 프로젝트 요약 정보 저장
필드를 모두 채운 뒤 변경 사항을 영구 저장합니다. 여기서는 검토를 쉽게 하기 위해 XML 형식으로 저장하지만, MPP 형식으로 다시 저장할 수도 있습니다.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## 단계 3: 프로젝트 요약 정보 읽기
메타데이터가 올바르게 기록되었는지 확인하기 위해 파일을 다시 로드하고 각 속성을 읽어봅니다. 이 단계는 **키워드 설정 방법**이 실제로 엔드‑투‑엔드로 동작함을 보여줍니다.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 일반적인 문제 및 해결책
| 문제 | 발생 이유 | 해결 방법 |
|-------|----------------|-----|
| **`project.get(Prj.CREATION_DATE)`에서 NullPointerException** | 저장하기 전에 Calendar가 설정되지 않았습니다. | 저장(`save()`)하기 전에 `project.set(Prj.CREATION_DATE, cal.getTime())`를 호출했는지 확인하십시오. |
| **Microsoft Project UI에 키워드가 표시되지 않음** | 파일이 XML로 저장된 후 직접 Project에서 열었습니다. | MPP(`SaveFileFormat.MPP`)로 다시 저장하거나 Project에서 *Import*를 통해 XML을 열어보세요. |
| **시간대에 의해 날짜 값이 이동함** | Java `Date`는 시간대 정보를 포함합니다. | UTC 날짜가 필요하면 `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`를 사용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Tasks for Java는 다른 Java 라이브러리와 원활하게 통합되어 프로젝트 관리 기능을 향상시킬 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 체험판 버전이 있나요?**  
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: Aspose.Tasks for Java는 얼마나 자주 업데이트되나요?**  
A: Aspose.Tasks for Java는 최신 Java 및 Microsoft Project 파일 버전과의 호환성을 유지하기 위해 정기적으로 업데이트됩니다.

**Q: 프로젝트 요약 정보를 더 세부적으로 맞춤 설정할 수 있나요?**  
A: 물론입니다. Aspose.Tasks for Java는 특정 요구 사항에 맞게 프로젝트 요약 정보를 광범위하게 커스터마이징할 수 있는 옵션을 제공합니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: Aspose.Tasks 커뮤니티 포럼에서 지원을 받을 수 있습니다 [here](https://forum.aspose.com/c/tasks/15).

---

**마지막 업데이트:** 2026-03-29  
**테스트 환경:** Aspose.Tasks for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}