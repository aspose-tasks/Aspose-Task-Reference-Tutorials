---
title: Gerenciando o MS Project Server com Aspose.Tasks
linktitle: Gerenciando o Project Server com Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Desbloqueie o gerenciamento contínuo do MS Project Server com Aspose.Tasks for .NET. Automatize as tarefas do projeto sem esforço.
type: docs
weight: 23
url: /pt/net/project-management-integration/project-server-management/
---
## Introdução
Neste tutorial, nos aprofundaremos no gerenciamento do MS Project Server usando Aspose.Tasks for .NET. Aspose.Tasks é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project de forma programática, permitindo integração e manipulação perfeitas dos dados do projeto.
## Pré-requisitos
Antes de mergulharmos no gerenciamento do MS Project Server com Aspose.Tasks, certifique-se de ter os seguintes pré-requisitos configurados:
1. Microsoft Project Server: você precisa de acesso a uma instância do Microsoft Project Server onde tenha privilégios administrativos ou pelo menos permissões para criar e gerenciar projetos.
2.  Biblioteca Aspose.Tasks for .NET: certifique-se de ter baixado e instalado a biblioteca Aspose.Tasks for .NET. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/tasks/net/).
3. Credenciais: Obtenha as credenciais necessárias para autenticar com sua instância do MS Project Server. Isso normalmente inclui um nome de usuário e uma senha.
## Importar namespaces
Antes de começar, certifique-se de ter importado os namespaces necessários em seu código C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Etapa 1: configurar credenciais de autenticação
Primeiro, você precisa configurar credenciais de autenticação para se conectar à sua instância do MS Project Server. Isso inclui o endereço de domínio, nome de usuário e senha.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Etapa 2: carregar o projeto
Em seguida, carregue o arquivo MS Project que você deseja gerenciar usando Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Etapa 3: Criar o Gerenciador do Project Server
 Instanciar um`ProjectServerManager` objeto usando as credenciais definidas anteriormente.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Etapa 4: definir opções para salvar
Defina quaisquer opções de salvamento específicas para o seu projeto. Por exemplo, você pode definir um tempo limite para a operação.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Etapa 5: criar ou atualizar projeto
Por fim, crie ou atualize o projeto no MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Parabéns! Você gerenciou com sucesso o MS Project Server usando Aspose.Tasks for .NET.

## Conclusão
Neste tutorial, exploramos como gerenciar o MS Project Server programaticamente usando Aspose.Tasks for .NET. Com as etapas fornecidas, você pode integrar perfeitamente o Aspose.Tasks em seus aplicativos .NET para automatizar tarefas de gerenciamento de projetos no MS Project Server.
## Perguntas frequentes
### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project Server?
R: Aspose.Tasks oferece suporte à integração com várias versões do Microsoft Project Server, garantindo compatibilidade em diferentes ambientes.
### P: Posso realizar operações em massa em projetos usando Aspose.Tasks?
R: Sim, Aspose.Tasks permite realizar operações em massa, como criar, atualizar e excluir projetos no MS Project Server.
### P: O Aspose.Tasks fornece suporte para agendamento de projetos e gerenciamento de recursos?
R: Com certeza, Aspose.Tasks oferece suporte abrangente para agendamento de projetos, alocação de recursos e funcionalidades de gerenciamento de tarefas.
### P: É possível automatizar tarefas de relatórios com Aspose.Tasks?
R: Sim, Aspose.Tasks permite automatizar a geração de relatórios personalizados com base nos dados do projeto, facilitando o monitoramento e análise eficiente do projeto.
### P: Posso experimentar o Aspose.Tasks antes de comprá-lo?
 R: Sim, você pode explorar os recursos do Aspose.Tasks acessando uma avaliação gratuita no[local na rede Internet](https://purchase.aspose.com/temporary-license/).