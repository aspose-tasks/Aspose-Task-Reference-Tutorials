---
title: Gerenciando credenciais do MS Project Server em Aspose.Tasks
linktitle: Gerenciando credenciais do Project Server em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar credenciais do MS Project Server perfeitamente com Aspose.Tasks for .NET. Aumente a eficiência do gerenciamento de projetos.
weight: 22
url: /pt/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciando credenciais do MS Project Server em Aspose.Tasks

## Introdução
No domínio do gerenciamento de projetos, a coordenação eficaz e a comunicação contínua são essenciais para a execução bem-sucedida do projeto. Aspose.Tasks for .NET fornece uma solução abrangente para gerenciar credenciais do Microsoft Project Server, permitindo que os usuários acessem e manipulem com segurança os dados do projeto. Este tutorial se aprofunda no processo de gerenciamento de credenciais do MS Project Server usando Aspose.Tasks for .NET, orientando os usuários em cada etapa para garantir uma experiência tranquila.
## Pré-requisitos
Antes de embarcar na jornada de gerenciamento de credenciais do MS Project Server com Aspose.Tasks for .NET, certifique-se de que os seguintes pré-requisitos sejam atendidos:
### 1. Instalando Aspose.Tasks para .NET
 Para começar, baixe e instale Aspose.Tasks for .NET do fornecido[Link para Download](https://releases.aspose.com/tasks/net/). Siga as instruções de instalação para integrar perfeitamente a biblioteca ao seu ambiente .NET.
### 2. Credenciais de acesso
Reúna as credenciais necessárias para acessar o MS Project Server. Isso inclui o endereço de domínio do SharePoint, o nome de usuário e a senha associados ao Project Server.

## Importar namespaces
Em seu projeto .NET, importe os namespaces necessários para utilizar as funcionalidades fornecidas pelo Aspose.Tasks for .NET com eficiência.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Etapa 1: definir o caminho do diretório do documento
```csharp
String DataDir = "Your Document Directory";
```
## Etapa 2: definir endereço de domínio, nome de usuário e senha do SharePoint
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Etapa 3: criar credenciais do Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Etapa 4: carregar o arquivo do projeto
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Etapa 5: inicializar o Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Etapa 6: Criar Novo Projeto
```csharp
manager.CreateNewProject(newProject);
```
## Etapa 7: recuperar a lista de projetos
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Etapa 8: iterar pela lista de projetos
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Conclusão
gerenciamento eficaz das credenciais do MS Project Server é fundamental para um gerenciamento simplificado de projetos. Aspose.Tasks for .NET simplifica esse processo, fornecendo um conjunto robusto de funcionalidades. Seguindo o guia passo a passo descrito neste tutorial, os usuários podem integrar perfeitamente o Aspose.Tasks for .NET em seus projetos, garantindo acesso seguro e manipulação dos dados do projeto.
## Perguntas frequentes
### P: O Aspose.Tasks for .NET é compatível com todas as versões do Microsoft Project Server?
R: O Aspose.Tasks for .NET foi projetado para ser compatível com várias versões do Microsoft Project Server, garantindo versatilidade e flexibilidade aos usuários.
### P: Posso integrar o Aspose.Tasks for .NET ao meu projeto .NET existente?
R: Sim, o Aspose.Tasks for .NET pode ser perfeitamente integrado a projetos .NET existentes, facilitando recursos eficientes de gerenciamento de projetos.
### P: O Aspose.Tasks for .NET fornece suporte para acessar recursos do projeto?
R: Com certeza, o Aspose.Tasks for .NET oferece suporte abrangente para acessar e manipular recursos do projeto, aumentando a eficiência do gerenciamento de projetos.
### P: Há alguma opção de licenciamento disponível para Aspose.Tasks for .NET?
R: Sim, o Aspose.Tasks for .NET oferece opções de licenciamento flexíveis, incluindo licenças temporárias para fins de teste e licenças completas para uso comercial.
### P: Onde posso procurar assistência ou suporte para Aspose.Tasks for .NET?
 R: Para qualquer dúvida ou assistência sobre Aspose.Tasks for .NET, você pode visitar o fórum de suporte em[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Código fonte completo
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
