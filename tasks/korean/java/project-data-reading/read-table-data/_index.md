---
date: 2025-12-18
description: Aspose.Tasks를 사용하여 Java에서 테이블 필드를 가져오고 테이블 데이터를 읽는 방법을 배웁니다. 이 튜토리얼에서는
  프로젝트 파일에서 테이블 정보를 검색하는 방법을 보여줍니다.
linktitle: Read Table Data from File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks에서 테이블 필드를 가져오고 테이블 데이터를 읽는 방법
url: /ko/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks에서 테이블 필드를 가져오고 테이블 데이터를 읽는 방법

## 소개
이 튜토리얼에서는 Microsoft Project 파일에서 **테이블 필드를 가져오는 방법**과 Aspose.Tasks for Java를 사용하여 테이블 데이터를 보는 방법을 알아봅니다. 도구를 작성하거나, 데이터를 마이그레이션하거나, 프로젝트 분석을 자동화할 때, 프로그래밍 방식으로 테이블 정보를 추출하면 작업 시간을 크게 할 수 있습니다. 환경 설정부터 각 필드의 세부 정보를 출력하는 전체 과정을 기대하기 때문에, 바로 자신만의 특별한 기능을 통합할 수 있습니다.

## 빠른 답변
- **“테이블 필드 가져오기”는 무엇을 의미하는지?** 프로젝트를 위해 테이블에 표시되는 각 열의 정의(너비, 제목, 대신 등)를 가져오는 것을 말합니다.
- **필요한 라이브러리는?** Aspose.Tasks for Java.
- **개발에 전력이 필요한가요?** 평가용 무료 체험판을 사용할 수 있으며 실제 운영 환경에서 인스턴스 인스턴스가 필요합니다.
- **모든 프로젝트 버전에서 테이블을 사용할 수 있습니까?** 예, Aspose.Tasks는 Project 2003‑2016 및 최신 형식을 지원합니다.
- **추가 설정이 필요합니까?** JDK 8 이상과 클래스 패스트에 Aspose.Tasks JAR만 있으면 됩니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하세요:

1. **JDK(Java Development Kit)** – JDK 8이 설치되어 있어야 합니다. 오라클 웹사이트에서 다운로드하실 수 있습니다.
2. **Aspose.Tasks for Java JAR** – 최신 라이브러리를 [다운로드 링크](https://releases.aspose.com/tasks/java/)에서 수용 프로젝트 빌드 외부에 추가하세요.

## 패키지 가져오기
필요한 Aspose.Tasks 클래스를 가져옵니다:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## 1단계: 데이터 디렉터리 설정
*.mpp* 파일이 들어 있는 폴더를 정의합니다:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"`를 실제 절대 경로(예: `C:/Projects/Data/`)로 교체하세요.

## 2단계: 프로젝트 파일 불러오기
분석하려는 Project 파일을 가리키는 `Project` 인스턴스를 생성합니다:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

파일 이름이나 확장자가 다르면 문자열을 적절히 수정하세요.

## 3단계: 테이블 정보 가져오기
이제 **테이블 필드**를 가져와 각 필드의 속성을 표시합니다:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

이 스니펫은 기본 테이블에 있는 모든 열의 너비, 제목, 정렬을 출력하여 프로젝트에 정의된 **테이블 필드** 전체를 한눈에 보여줍니다.

## 테이블 정보를 검색하는 이유는 무엇입니까?
- **자동화** – 수동 복사본을 첨부하여 생성하도록 했습니다.
- **마이그레이션** – 레거시 프로젝트 파일의 데이터를 최신 데이터베이스로 옮깁니다.
- **검증** – 프로젝트 폴더가 조직을 준수하는지 확인합니다.

## 일반적인 함정 및 팁
- **Null 테이블** – 프로젝트에 테이블이 없으면 `project.getTables()`가 비어 있을 수 있습니다. 0`에 접근하기 전에 크기를 확인하세요.
- **인코딩 문제** – 최신 Aspose.Tasks 버전을 사용하면 제목에 포함된 ASCII 문자 표시가 적용됩니다.
- ** 협조하면 ** – 매우 큰 *.mpp* 파일을 메모리를 많이 사용합니다. 스트리밍 데이터셋의 경우 스트리밍 API를 사용해보세요.

## 결론
단계를 따라 Aspose.Tasks for Java를 사용하여 Microsoft Project 파일에서 **테이블 필드를 가져오고** 테이블 데이터를 사용하는 방법을 관계에 두는 것입니다. 이 기능을 통해 Java 파이프라인을 잘라내기, 데이터 마이그레이션라인, 끝내기 위한 솔루션을 제공할 수 있습니다.

## 추가 자주 묻는 질문

**Q: 다중 프로젝트 환경에서 테이블 데이터를 어떻게 읽나요?**  
A: `new Project(path)`로 각 프로젝트를 개별적으로 로드하고, 각 인스턴스에 대해 테이블‑필드 추출 루프를 반복하면 됩니다.

**Q: 추출한 테이블 필드를 CSV로 내보낼 수 있나요?**  
A: 예, 필드 세부 정보를 출력한 후 `FileWriter`에 기록하거나 OpenCSV와 같은 CSV 라이브러리를 사용해 저장할 수 있습니다.

**Q: 사용자가 만든 사용자 정의 테이블도 Aspose.Tasks가 처리하나요?**  
A: 물론입니다. `project.getTables()` 컬렉션에는 기본 테이블과 사용자 정의 테이블 모두 포함되므로 필요에 따라 반복할 수 있습니다.

**Q: Project 파일이 비밀번호로 보호되어 있으면 어떻게 하나요?**  
A: 비밀번호를 지정할 수 있는 `LoadOptions` 객체를 인수로 받는 `Project` 생성자를 사용하면 됩니다.

**Q: 표시된 열만 필터링하는 방법이 있나요?**  
A: 최신 버전에서는 각 `TableField`의 `getVisible()` 메서드를 확인해 UI에 표시되는 열인지 판단할 수 있습니다.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}