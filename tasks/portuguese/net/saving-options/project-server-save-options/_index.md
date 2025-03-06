---
title: Opções de salvamento do MS Project no servidor para Aspose.Tasks
linktitle: Opções de salvamento do Project Server para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar opções do Microsoft Project para Aspose.Tasks usando a integração do Project Server. Aprimore seus fluxos de trabalho de gerenciamento de projetos.
weight: 16
url: /pt/net/saving-options/project-server-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opções de salvamento do MS Project no servidor para Aspose.Tasks

## Introdução
Neste tutorial, nos aprofundaremos em salvar opções do Microsoft Project para Aspose.Tasks usando o Project Server. Aspose.Tasks é uma API .NET poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente. Aproveitando os recursos do Project Server, podemos integrar perfeitamente o Aspose.Tasks em nossos fluxos de trabalho de gerenciamento de projetos. Este tutorial irá guiá-lo através do processo passo a passo.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1.  Aspose.Tasks for .NET: Instale Aspose.Tasks for .NET a partir do[Link para Download](https://releases.aspose.com/tasks/net/).
   
2. Acesso ao Project Server: você precisará de credenciais de acesso e da URL da sua instância do Project Server. Se você não tiver um, poderá obter uma avaliação gratuita em[aqui](https://releases.aspose.com/).
3. Arquivo do Microsoft Project: Prepare o arquivo do Microsoft Project (.mpp) que você deseja salvar usando Aspose.Tasks.

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para o seu projeto:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Etapa 1: inicializar projeto e credenciais
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Certifique-se de substituir`"Your Document Directory"`, `URL`, `Domain`, `UserName` , e`Password` com seus valores reais.
## Etapa 2: Criar o Gerenciador do Project Server
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Etapa 3: definir opções para salvar
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Ajusta a`ProjectGuid`, `ProjectName`, `Timeout` , e`PollingInterval` de acordo com suas necessidades.
## Etapa 4: Salvar projeto no servidor
```csharp
manager.CreateNewProject(project, options);
```
Isso salvará o projeto no Project Server com as opções especificadas.

## Conclusão
Neste tutorial, aprendemos como salvar opções do Microsoft Project para Aspose.Tasks usando a integração do Project Server. Seguindo essas etapas, você pode incorporar perfeitamente o Aspose.Tasks em seus fluxos de trabalho de gerenciamento de projetos, aumentando a eficiência e a produtividade.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks com diferentes versões do Microsoft Project?
R: Sim, Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.
### P: Existe uma versão de teste disponível para Aspose.Tasks?
 R: Sim, você pode obter uma versão de avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### P: O Aspose.Tasks oferece suporte a multithreading?
R: Sim, o Aspose.Tasks foi projetado para ser thread-safe, permitindo acesso simultâneo aos dados do projeto.
### P: Posso personalizar as opções de salvamento ao usar a integração do Project Server?
R: Sim, você pode personalizar opções de salvamento, como nome do projeto, tempo limite e intervalo de pesquisa, para atender às suas necessidades.
### P: Onde posso encontrar suporte para Aspose.Tasks?
 R: Você pode encontrar suporte e assistência no site[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
