---
date: 2025-12-21
description: Java에서 MPP 파일을 사용해 SVG를 생성하고 Aspose.Tasks 라이브러리를 이용해 프로젝트를 SVG로 저장하는
  방법을 배웁니다. 코드 예제가 포함된 단계별 가이드.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Java에서 Aspose.Tasks를 사용해 MPP를 SVG로 만드는 방법
url: /ko/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 MPP에서 SVG 만들기

## 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **MPP에서 SVG 만들기** 방법을 배웁니다. Microsoft Project (MPP) 파일을 확장 가능한 벡터 그래픽(SVG)으로 변환하면 고품질이며 해상도에 독립적인 다이어그램을 웹 페이지, 보고서 또는 대시보드에 직접 삽입할 수 있습니다. 필요한 설정 과정을 단계별로 안내하고, 정확한 코드를 보여주며, 각 단계별 설명을 통해 여러분이 직접 **프로젝트를 SVG로 저장**할 수 있도록 도와드립니다.

## 빠른 답변
- **“MPP에서 SVG 만들기”는 무엇을 의미하나요?**  
  Microsoft Project 파일(.mpp)을 SVG 이미지로 변환하여 브라우저에서 품질 손실 없이 표시할 수 있게 합니다.  
- **어떤 라이브러리가 변환을 담당하나요?**  
  Aspose.Tasks for Java가 단일 라인 `save` 메서드로 변환을 수행합니다.  
- **라이선스가 필요합니까?**  
  상업적 사용을 위해 임시 라이선스가 필요하며, 무료 체험판을 제공하고 있습니다.  
- **전제 조건은 무엇인가요?**  
  Java JDK 8 이상과 Aspose.Tasks for Java JAR 파일이 필요합니다.  
- **변환 시간은 얼마나 걸리나요?**  
  일반적인 프로젝트 파일은 보통 1초 미만에 완료됩니다.

## “MPP에서 SVG 만들기”란 무엇인가요?
MPP 파일에서 SVG를 만든다는 것은 프로젝트 일정(작업, 타임라인, 리소스 등)의 시각적 표현을 Scalable Vector Graphics 형식으로 내보내는 것을 의미합니다. SVG는 XML 기반이며 가볍고 고해상도 디스플레이에서도 완벽하게 확대됩니다.

## 왜 Aspose.Tasks를 사용해 프로젝트를 SVG로 저장하나요?
- **Microsoft Project 설치가 필요 없음** – 라이브러리가 독립적으로 동작합니다.  
- **완전한 충실도** – 차트, 간트 바, 마일스톤 등이 스타일을 그대로 유지합니다.  
- **크로스‑플랫폼** – Windows, Linux, macOS 어디서든 코드 실행 가능.  
- **쉬운 통합** – 한 줄 API 호출로 기존 Java 파이프라인에 자연스럽게 삽입됩니다.

## 전제 조건
- **Java Development Kit (JDK)** – 버전 8 이상. Oracle 웹사이트에서 다운로드하세요.  
- **Aspose.Tasks for Java** – 공식 다운로드 페이지 **[here](https://releases.aspose.com/tasks/java/)**에서 라이브러리를 받으세요.  

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. import 블록은 그대로 유지됩니다.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 단계 1: 데이터 디렉터리 정의
소스 MPP 파일이 위치한 경로와 SVG가 저장될 경로를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `FileNotFoundException`을 방지하려면 절대 경로나 프로젝트 리소스 폴더에 상대적인 경로를 사용하세요.

## 단계 2: MPP 파일 로드
기존 Microsoft Project 파일을 로드하여 `Project` 인스턴스를 생성합니다.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

이 코드는 앞서 정의한 폴더에서 *HomeMovePlan.mpp* 파일을 읽어옵니다.

## 단계 3: 프로젝트를 SVG로 저장
이제 한 줄 명령으로 **프로젝트를 SVG로 저장**할 수 있습니다.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

메서드는 `project5.svg` 파일을 동일한 디렉터리에 기록합니다. 생성된 SVG는 최신 브라우저에서 열 수 있으며 HTML에 직접 삽입할 수도 있습니다.

## 일반적인 문제와 해결 방법
| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** | `dataDir` 경로가 올바르지 않음 | 디렉터리 문자열이 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요. |
| **Blank SVG output** | 뷰 없이 프로젝트가 로드됨 | 저장하기 전에 MPP 파일에 간트 차트 뷰가 포함되어 있는지 확인하세요. |
| **License exception** | 유효한 라이선스가 적용되지 않음 | `save` 호출 전에 `License.setLicense("path/to/license.xml")`을 사용해 임시 라이선스를 적용하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환되나요?**  
A: 예, 오래된 버전부터 최신 버전까지 MPP, MPT, XML 형식을 모두 지원합니다.

**Q: SVG 출력의 모양을 커스터마이즈할 수 있나요?**  
A: 물론입니다. `SvgOptions`를 사용해 폰트, 색상 및 레이아웃 옵션을 설정한 후 `save`를 호출하면 됩니다.

**Q: Aspose.Tasks for Java는 상업적 사용에 라이선스가 필요합니까?**  
A: 예, 프로덕션 환경에서는 유효한 라이선스가 필요합니다. 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

**Q: 구매 전에 Aspose.Tasks for Java를 체험해볼 수 있나요?**  
A: 네, 무료 체험판을 **[here](https://purchase.aspose.com/buy)**에서 이용할 수 있습니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디서 받을 수 있나요?**  
A: 커뮤니티 포럼 **[here](https://forum.aspose.com/c/tasks/15)**에서 질문하고 피드백을 공유하세요.

## 결론
이제 Java에서 **MPP에서 SVG 만들기** 방법과 Aspose.Tasks를 사용해 **프로젝트를 SVG로 저장**하는 방법을 알게 되었습니다. 이 기능을 활용하면 웹 포털, 보고서 대시보드 또는 확장 가능한 그래픽이 필요한 모든 곳에 풍부한 프로젝트 시각화를 통합할 수 있습니다. `SvgOptions`를 실험해 출력물을 세밀하게 조정하고, 개발 툴킷에 강력한 도구를 추가해 보세요.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}