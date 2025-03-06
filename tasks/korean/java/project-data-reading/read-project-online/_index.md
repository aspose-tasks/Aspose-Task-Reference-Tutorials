---
title: Aspose.Tasks를 사용한 간편한 MS 프로젝트 온라인 데이터 읽기
linktitle: Aspose.Tasks에서 프로젝트 온라인 데이터 읽기
second_title: Aspose.Tasks 자바 API
description: Aspose.Tasks for Java를 사용하여 Microsoft Project Online 데이터를 쉽게 읽는 방법을 알아보세요. 프로젝트 관리 역량을 강화하세요.
type: docs
weight: 13
url: /ko/java/project-data-reading/read-project-online/
---
## 소개
프로젝트 관리 영역에서는 효율적인 운영을 위해 Microsoft Project Online 데이터를 효율적으로 처리하는 것이 중요합니다. Aspose.Tasks for Java는 이러한 데이터를 손쉽게 읽을 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Tasks를 활용하여 MS Project Online 데이터에 원활하게 액세스하고 조작하는 방법을 살펴봅니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1. JDK(Java Development Kit): JDK를 설치하여 Java 프로그램을 컴파일하고 실행합니다.
2.  Java 라이브러리용 Aspose.Tasks: Aspose.Tasks 라이브러리를 다운로드하여 Java 프로젝트에 포함하세요. 에서 취득하실 수 있습니다.[여기](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online 계정: MS Project Online 데이터에 액세스하기 위한 유효한 자격 증명을 얻습니다.
4. SharePoint 도메인 주소: MS Project Online 데이터가 있는 SharePoint 도메인 주소입니다.
5. 사용자 이름 및 비밀번호: MS Project Online에 대한 액세스를 인증하기 위한 자격 증명입니다.
## 패키지 가져오기
Java 프로젝트에서 원활한 통합을 위해 필요한 Aspose.Tasks 패키지를 가져옵니다.
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 1단계: SharePoint 도메인 주소, 사용자 이름 및 비밀번호 설정
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 바꾸다`"https://contoso.sharepoint.com"` SharePoint 도메인 주소로`"admin@contoso.onmicrosoft.com"` 귀하의 사용자 이름과`"MyPassword"` 당신의 비밀번호로.
## 2단계: Project Server 자격 증명으로 인증
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 만들다`ProjectServerCredentials` SharePoint 도메인 주소, 사용자 이름 및 비밀번호가 포함된 개체입니다. 그런 다음 초기화`ProjectServerManager` 이 자격 증명으로.
## 3단계: 프로젝트 목록 검색 및 정보 표시
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 다음에서 얻은 프로젝트 목록을 반복합니다.`reader.getProjectList()` 이름, 생성 날짜, 마지막 저장 날짜와 같은 프로젝트 세부 정보를 표시합니다.
## 4단계: 개별 프로젝트 및 출력 리소스 수 로드
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 각 프로젝트에 대해 다음을 사용하여 로드합니다.`reader.getProject(p.getId())` 관련 리소스 수와 함께 프로젝트 이름을 출력합니다.

## 결론
Aspose.Tasks for Java는 MS Project Online 데이터를 읽는 프로세스를 단순화하여 개발자에게 프로젝트 관리 작업을 간소화할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼을 따르면 Aspose.Tasks를 Java 애플리케이션에 효율적으로 통합하여 프로젝트 데이터에 쉽게 액세스하고 조작할 수 있습니다.
## FAQ
### Q: Java용 Aspose.Tasks를 사용하여 MS Project Online 데이터를 수정할 수 있습니까?
A: 예, Aspose.Tasks는 프로그래밍 방식으로 MS Project Online 데이터를 읽을 뿐만 아니라 수정할 수 있는 광범위한 기능을 제공합니다.
### Q: Aspose.Tasks는 다른 프로젝트 관리 파일 형식을 지원합니까?
A: 물론 Aspose.Tasks는 MPP, XML 등 다양한 파일 형식을 지원하여 다양한 프로젝트 관리 시스템과의 호환성을 보장합니다.
### Q: Aspose.Tasks for Java에 사용할 수 있는 무료 평가판이 있나요?
 A: 네, 다음 사이트에서 무료 평가판을 이용하실 수 있습니다.[여기](https://releases.aspose.com/) Aspose.Tasks의 특징과 기능을 탐색합니다.
### Q: Aspose.Tasks for Java에 대한 포괄적인 문서는 어디서 찾을 수 있나요?
 A: 자세한 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/tasks/java/)Java 프로젝트에서 Aspose.Tasks 활용에 대한 포괄적인 지침을 확인하세요.
### Q: Aspose.Tasks for Java에는 어떤 지원 옵션을 사용할 수 있나요?
 A: 문제가 발생하거나 문의사항이 있는 경우 Aspose.Tasks 커뮤니티 포럼에서 도움을 요청할 수 있습니다.[여기](https://forum.aspose.com/c/tasks/15).