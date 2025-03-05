---
title: Leitura de dados online do MS Project sem esforço com Aspose.Tasks
linktitle: Lendo dados on-line do projeto em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como ler dados do Microsoft Project Online sem esforço usando Aspose.Tasks for Java. Aprimore seus recursos de gerenciamento de projetos.
type: docs
weight: 13
url: /pt/java/project-data-reading/read-project-online/
---
## Introdução
No domínio do gerenciamento de projetos, o manuseio eficiente dos dados do Microsoft Project Online é crucial para operações simplificadas. Aspose.Tasks for Java fornece uma solução robusta para ler esses dados sem esforço. Este tutorial se aprofunda no aproveitamento do Aspose.Tasks para acessar e manipular dados do MS Project Online perfeitamente.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter o seguinte:
1. Java Development Kit (JDK): Instale o JDK para compilar e executar programas Java.
2.  Biblioteca Aspose.Tasks para Java: Baixe e inclua a biblioteca Aspose.Tasks em seu projeto Java. Você pode adquiri-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Conta do Microsoft Project Online: obtenha credenciais válidas para acessar dados do MS Project Online.
4. Endereço de domínio do SharePoint: o endereço de domínio do SharePoint onde residem os dados do MS Project Online.
5. Nome de usuário e senha: Credenciais para autenticação de acesso ao MS Project Online.
## Importar pacotes
Em seu projeto Java, importe os pacotes Aspose.Tasks necessários para uma integração perfeita:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Etapa 1: definir endereço de domínio, nome de usuário e senha do SharePoint
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Substituir`"https://contoso.sharepoint.com"` com seu endereço de domínio do SharePoint,`"admin@contoso.onmicrosoft.com"` com seu nome de usuário e`"MyPassword"` com sua senha.
## Etapa 2: autenticar com credenciais do Project Server
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Criar`ProjectServerCredentials` objeto com o endereço de domínio do SharePoint, nome de usuário e senha. Então inicialize`ProjectServerManager` com essas credenciais.
## Etapa 3: recuperar a lista de projetos e exibir informações
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Iterar pela lista de projetos obtida em`reader.getProjectList()` e exibir detalhes do projeto, como nome, data de criação e data da última gravação.
## Etapa 4: carregar projetos individuais e contagem de recursos de saída
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Para cada projeto, carregue-o usando`reader.getProject(p.getId())` e produza o nome do projeto junto com a contagem de recursos associados.

## Conclusão
Aspose.Tasks for Java simplifica o processo de leitura de dados do MS Project Online, oferecendo aos desenvolvedores um poderoso conjunto de ferramentas para agilizar as tarefas de gerenciamento de projetos. Seguindo este tutorial, você pode integrar Aspose.Tasks com eficiência em seus aplicativos Java para acessar e manipular dados do projeto com facilidade.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks for Java para modificar dados do MS Project Online?
R: Sim, o Aspose.Tasks oferece amplos recursos não apenas para ler, mas também para modificar dados do MS Project Online programaticamente.
### P: O Aspose.Tasks oferece suporte a outros formatos de arquivo de gerenciamento de projetos?
R: Com certeza, Aspose.Tasks oferece suporte a vários formatos de arquivo, incluindo MPP, XML e muito mais, garantindo compatibilidade com diversos sistemas de gerenciamento de projetos.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for Java?
 R: Sim, você pode aproveitar uma avaliação gratuita em[aqui](https://releases.aspose.com/) para explorar os recursos e funcionalidades do Aspose.Tasks.
### P: Onde posso encontrar documentação abrangente para Aspose.Tasks for Java?
 R: Você pode consultar a documentação detalhada[aqui](https://reference.aspose.com/tasks/java/)para obter orientação abrangente sobre a utilização do Aspose.Tasks em seus projetos Java.
### P: Quais opções de suporte estão disponíveis para Aspose.Tasks for Java?
 R: Se você encontrar algum problema ou tiver dúvidas, pode procurar ajuda no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).