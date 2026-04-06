---
date: 2026-03-27
description: Aspose.Tasks를 사용하여 Java에서 MPP를 SVG로 내보내는 방법을 배워보세요. 단계별 가이드, 코드 예제 및
  프로젝트를 빠르게 SVG로 저장하는 팁.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks를 사용하여 Java에서 MPP를 SVG로 내보내는 방법
url: /ko/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 MPP를 SVG로 내보내는 방법

## Export MPP to SVG – 소개
이 튜토리얼에서는 Aspose.Tasks for Java를 사용하여 **export MPP to SVG** 파일을 내보내는 방법을 배웁니다. Microsoft Project (MPP) 파일을 Scalable Vector Graphics (SVG) 이미지로 변환하면 고품질의 해상도에 독립적인 다이어그램을 웹 페이지, 보고서 또는 대시보드에 직접 삽입할 수 있습니다. 필요한 설정 과정을 단계별로 안내하고, 정확한 코드를 보여주며, 각 단계를 설명하여 여러분이 직접 **save project as SVG**를 자신 있게 수행할 수 있도록 합니다.

## 빠른 답변
- **“export MPP to SVG”는 무엇을 의미합니까?**  
  Microsoft Project 파일(.mpp)을 SVG 이미지로 변환하여 품질 손실 없이 모든 브라우저에서 표시할 수 있게 합니다.  
- **어떤 라이브러리가 변환을 담당합니까?**  
  Aspose.Tasks for Java가 단일 라인 `save` 메서드를 제공하여 변환을 수행합니다.  
- **라이선스가 필요합니까?**  
  상업적 사용을 위해 임시 라이선스가 필요하며, 무료 체험판을 이용할 수 있습니다.  
- **전제 조건은 무엇입니까?**  
  Java JDK 8 이상 및 Aspose.Tasks for Java JAR 파일이 필요합니다.  
- **변환에 얼마나 걸립니까?**  
  일반적인 프로젝트 파일은 보통 1초 미만이 소요됩니다.

## “export MPP to SVG”란?
Export MPP to SVG는 프로젝트 일정(작업, 타임라인, 리소스)의 시각적 표현을 SVG 파일로 기록하는 것을 의미합니다. SVG는 XML 기반이며 가볍고 고해상도 디스플레이에서도 완벽하게 확대됩니다.

## 왜 Aspose.Tasks로 export MPP to SVG를 하나요?
- **Microsoft Project 설치 불필요** – 라이브러리가 독립적으로 동작합니다.  
- **전체 충실도** – 차트, 간트 바, 마일스톤이 스타일을 그대로 유지합니다.  
- **크로스‑플랫폼** – Windows, Linux, macOS에서 코드를 실행할 수 있습니다.  
- **한 줄 API** – 한 번의 호출로 프로젝트를 SVG로 저장하여 기존 Java 파이프라인에 자연스럽게 통합됩니다.

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

## Step 1: 데이터 디렉터리 정의
소스 MPP 파일이 위치한 경로와 SVG가 저장될 경로를 지정합니다.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `FileNotFoundException`을 방지하려면 절대 경로나 프로젝트 리소스 폴더에 대한 상대 경로를 사용하세요.

## Step 2: MPP 파일 로드
기존 Microsoft Project 파일을 로드하여 `Project` 인스턴스를 생성합니다.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

이 라인은 앞서 정의한 폴더에서 *HomeMovePlan.mpp*를 읽어옵니다.

## Step 3: 프로젝트를 SVG로 저장
이제 **export MPP to SVG**를 한 줄 명령으로 수행할 수 있습니다.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

이 메서드는 `project5.svg`를 동일한 디렉터리에 기록합니다. 생성된 SVG는 최신 브라우저에서 열 수 있으며 HTML에 직접 삽입할 수도 있습니다.

## 일반적인 사용 사례
- **프로젝트 대시보드** – 클라이언트가 Microsoft Project를 설치하지 않아도 웹 포털에 실시간 간트 차트를 삽입합니다.  
- **자동화된 보고** – PDF 또는 HTML 보고서를 위해 SVG 이미지를 실시간으로 생성합니다.  
- **팀 간 협업** – 브라우저만 있으면 일정 시각화를 확인할 수 있도록 이해관계자와 공유합니다.

## 일반적인 문제 및 해결책
| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** | `dataDir` 경로가 올바르지 않음 | 디렉터리 문자열이 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요. |
| **Blank SVG output** | 뷰 없이 프로젝트가 로드됨 | 저장하기 전에 MPP 파일에 간트 차트 뷰가 포함되어 있는지 확인하세요. |
| **License exception** | 유효한 라이선스가 적용되지 않음 | `save` 호출 전에 `License.setLicense("path/to/license.xml")`을 사용해 임시 라이선스를 적용하세요. |

## 자주 묻는 질문

**Q: Aspose.Tasks for Java가 모든 버전의 Microsoft Project 파일과 호환됩니까?**  
A: 네, 오래된 버전부터 최신 버전까지 MPP, MPT, XML 형식을 지원합니다.

**Q: SVG 출력의 모양을 사용자 정의할 수 있나요?**  
A: 물론입니다. `save` 호출 전에 `SvgOptions`를 사용해 글꼴, 색상 및 레이아웃 옵션을 설정하세요.

**Q: Aspose.Tasks for Java는 상업적 사용에 라이선스가 필요합니까?**  
A: 네, 프로덕션 환경에서는 유효한 라이선스가 필요합니다. 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

**Q: 구매 전에 Aspose.Tasks for Java를 체험해볼 수 있나요?**  
A: 네, 무료 체험판은 **[here](https://purchase.aspose.com/buy)**에서 이용 가능합니다.

**Q: Aspose.Tasks for Java에 대한 지원은 어디에서 받을 수 있나요?**  
A: 커뮤니티 포럼 **[here](https://forum.aspose.com/c/tasks/15)**에서 질문하고 피드백을 공유하세요.

## 결론
이제 Java에서 **export MPP to SVG**를 수행하고 Aspose.Tasks를 사용해 **save project as SVG**를 효율적으로 할 수 있습니다. 이 기능을 활용하면 웹 포털, 보고 대시보드 또는 확장 가능한 그래픽이 필요한 모든 곳에 풍부한 프로젝트 시각화를 통합할 수 있습니다. `SvgOptions`를 실험해 출력물을 미세 조정하고, 개발 도구 상자에 강력한 도구를 추가해 보세요.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}