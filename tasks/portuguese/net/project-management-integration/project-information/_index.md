---
title: Extraia informações do MS Project em Aspose.Tasks
linktitle: Extraindo informações do projeto em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como extrair informações do MS Project sem esforço usando Aspose.Tasks for .NET. Mergulhe em nosso tutorial abrangente.
weight: 20
url: /pt/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraia informações do MS Project em Aspose.Tasks

## Introdução
Você está procurando extrair informações de arquivos do Microsoft Project com eficiência usando Aspose.Tasks for .NET? Neste tutorial, guiaremos você pelo processo passo a passo. Mas antes de nos aprofundarmos nos detalhes da implementação, vamos primeiro garantir que você tenha tudo o que precisa.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
### 1. Aspose.Tasks para .NET
 Certifique-se de ter instalado a biblioteca Aspose.Tasks for .NET. Caso ainda não tenha feito isso, você pode baixá-lo no site[Site Aspose.Tasks para .NET](https://releases.aspose.com/tasks/net/).
### 2. Credenciais para SharePoint
Você precisará das credenciais para acessar o SharePoint onde seus arquivos do MS Project estão armazenados. Certifique-se de ter as seguintes informações:
- Endereço de domínio do SharePoint
- Nome de usuário
- Senha
## Importando Namespaces
Depois de resolver seus pré-requisitos, é hora de importar os namespaces necessários para o seu projeto.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Agora vamos dividir o processo de extração de informações do MS Project em várias etapas.
## Etapa 1: forneça credenciais
Primeiro, você precisa fornecer suas credenciais do SharePoint para acessar o Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Etapa 2: inicializar o Project Server Manager
 A seguir, inicialize um`ProjectServerManager` instância com as credenciais fornecidas.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Etapa 3: recuperar a lista de projetos
Agora você pode recuperar a lista de projetos do Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Etapa 4: Imprimir informações do projeto
Por fim, percorra a lista de projetos e imprima suas informações.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Conclusão
Parabéns! Você aprendeu com sucesso como extrair informações do MS Project usando Aspose.Tasks for .NET. Com esse conhecimento, agora você pode integrar essa funcionalidade perfeitamente aos seus aplicativos .NET.
## Perguntas frequentes
### Q1: Posso usar Aspose.Tasks for .NET com qualquer versão do Microsoft Project?
R: Sim, Aspose.Tasks for .NET oferece suporte a várias versões do Microsoft Project, incluindo 2003, 2007, 2010, 2013, 2016 e 2019.
### Q2: O Aspose.Tasks for .NET é compatível com as plataformas Windows e Linux?
R: Sim, o Aspose.Tasks for .NET é compatível com as plataformas Windows e Linux, tornando-o versátil para diferentes ambientes de desenvolvimento.
### Q3: Posso extrair dependências de tarefas usando Aspose.Tasks for .NET?
R: Absolutamente! Aspose.Tasks for .NET fornece funcionalidade robusta para extrair não apenas informações básicas do projeto, mas também dependências de tarefas e outros detalhes intrincados.
### Q4: O Aspose.Tasks for .NET oferece suporte técnico?
 R: Sim, você pode obter suporte técnico para Aspose.Tasks for .NET através do[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), onde você pode tirar dúvidas e buscar ajuda de especialistas.
### Q5: Posso experimentar o Aspose.Tasks for .NET antes de comprá-lo?
 R: Certamente! Você pode aproveitar uma avaliação gratuita do Aspose.Tasks for .NET no site[página de lançamentos](https://releases.aspose.com/), permitindo que você explore seus recursos antes de tomar uma decisão de compra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
