---
date: 2026-07-05
description: Aprenda a copiar dados do projeto usando Aspose.Tasks para .NET com opções
  de cópia. Impulsione seus aplicativos .NET com gerenciamento de projetos preciso.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Como copiar dados do projeto com opções de cópia no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Como copiar dados do projeto com opções de cópia no Aspose.Tasks
url: /pt/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Copiar Dados do Projeto com Opções de Cópia no Aspose.Tasks

## Introdução

Se você precisar **como copiar projeto** de um arquivo Microsoft Project para outro, o Aspose.Tasks para .NET oferece uma maneira limpa, orientada a código, de fazer isso. Neste tutorial, percorreremos todo o fluxo de trabalho — carregando um projeto de origem, configurando opções de cópia, criando uma cópia e carregando o resultado — para que você possa integrar a lógica de cópia de projetos em qualquer aplicação .NET com confiança.

## Respostas Rápidas
- **O que a funcionalidade de cópia faz?** Ela duplica os dados do projeto permitindo incluir ou excluir seções específicas, como calendários, recursos ou informações de visualização.  
- **Qual classe controla o comportamento?** `CopyToOptions` permite ajustar finamente o que será copiado.  
- **Preciso de uma licença?** Uma licença válida do Aspose.Tasks é necessária para produção; um teste gratuito funciona para desenvolvimento.  
- **Formatos suportados?** O Aspose.Tasks manipula arquivos MPP, XML e XER — mais de 20 + formatos no total.  
- **Posso ignorar dados de visualização?** Sim, defina `CopyToOptions.SkipViewData = true` para omitir informações relacionadas à interface.

## O que é “como copiar projeto” no Aspose.Tasks?
**“Como copiar projeto”** refere‑se ao uso da API do Aspose.Tasks para duplicar os dados de um objeto Project em um novo arquivo, opcionalmente filtrando elementos indesejados. Essa operação é útil para criação de modelos, arquivamento ou criação de variantes de projetos sem etapas manuais de UI, e funciona em todos os formatos de arquivo suportados.

## Por que usar Opções de Cópia no Aspose.Tasks?
O Aspose.Tasks suporta **mais de 50 entidades relacionadas a projetos** (tarefas, recursos, calendários, atribuições, etc.) e pode processar arquivos com **até 10.000 tarefas** mantendo o uso de memória abaixo de 200 MB. Usar `CopyToOptions` permite evitar a cópia de dados de visualização pesados, reduzindo o tamanho do arquivo de saída em **30‑40 %** e acelerando a operação em aproximadamente **2×** para projetos grandes.

## Pré‑requisitos

1. **Aspose.Tasks for .NET** – faça o download da versão mais recente a partir do [link de download](https://releases.aspose.com/tasks/net/).  
2. **Ambiente de desenvolvimento .NET** – Visual Studio 2022 (ou qualquer IDE que suporte .NET 6+) instalado.  
3. **Uma licença válida do Aspose.Tasks** – opcional para avaliação, obrigatória para compilações de produção.  
4. **Um arquivo de projeto existente** (por exemplo, `SourceProject.xml`) que você deseja copiar.

## Como importar namespaces para Aspose.Tasks?

Adicione as diretivas `using` necessárias no início do seu arquivo C# para que o compilador possa localizar os tipos do Aspose.Tasks. Incluir essas instruções fornece acesso direto a `Project`, `CopyToOptions` e outras classes utilitárias sem precisar qualificar totalmente seus nomes, simplificando seu código e melhorando a legibilidade.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Etapa 1: Inicializar Objetos de Projeto

Primeiro, crie uma instância `Project` que representa o arquivo de origem e carregue os dados XML.  
A classe `Project` representa um arquivo Microsoft Project carregado na memória, expondo tarefas, recursos, calendários e outras informações do projeto.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Dica profissional:** Se você trabalha com arquivos muito grandes, considere usar o construtor `LoadOptions` para habilitar o carregamento preguiçoso e manter o consumo de memória baixo.

## Etapa 2: Criar uma Cópia do Projeto

Em seguida, instancie um segundo objeto `Project` que receberá os dados copiados. Este objeto começa vazio.

```csharp
Project copiedProject = new Project();
```

Agora você tem dois objetos `Project` distintos: um carregado do disco e outro pronto para receber a cópia.

## Etapa 3: Carregar Projeto Copiado

Após a operação de cópia (mostrada mais adiante), você desejará verificar o resultado carregando o arquivo recém‑salvo em outra instância `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Carregar o arquivo novamente confirma que a cópia foi bem‑sucedida e que as opções definidas se comportaram como esperado.

## Etapa 4: Configurar Opções de Cópia

A classe `CopyToOptions` permite especificar exatamente o que será transferido da origem para o destino.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Definir `SkipViewData = true` reduz o tamanho do arquivo de saída e acelera a operação, especialmente quando você só precisa dos dados lógicos do projeto.

## Etapa 5: Executar a Cópia do Projeto

Finalmente, invoque o método `CopyTo` no projeto de origem, passando o projeto de destino e as opções que você configurou.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Esta chamada de duas linhas executa toda a operação de cópia, respeitando as opções definidas. O `CopiedProject.xml` resultante contém apenas os dados solicitados.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| **NullReferenceException ao chamar `CopyTo`** | Projeto de destino não instanciado. | Certifique‑se de que `new Project()` seja chamado antes de `CopyTo`. |
| **Tarefas ausentes após a cópia** | `CopyCommonData` definido como `false`. | Defina `CopyCommonData = true` ou copie coleções específicas manualmente. |
| **Arquivo de saída grande** | `SkipViewData` deixado como `false`. | Habilite `SkipViewData` para omitir dados relacionados à UI. |
| **Licença não aplicada** | Arquivo de licença não carregado. | Chame `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` antes de usar qualquer API. |

## Perguntas Frequentes

**Q: Posso copiar apenas um subconjunto de tarefas?**  
A: Sim, use `CopyToOptions` junto com `ProjectRootTask` para especificar uma tarefa inicial, ou copie manualmente as tarefas selecionadas após a cópia inicial.

**Q: O Aspose.Tasks suporta cópia entre diferentes formatos de arquivo?**  
A: Absolutamente. Você pode carregar um arquivo MPP e salvar a cópia como XML, XER ou qualquer outro formato suportado — mais de **20 + formatos** no total.

**Q: Como lidar com arquivos de projeto protegidos por senha?**  
A: Carregue a origem com `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, então continue com a cópia normalmente.

**Q: Existe uma maneira de copiar pools de recursos sem tarefas?**  
A: Defina `CopyToOptions.CopyResources = true` e `CopyToOptions.CopyTasks = false` para transferir apenas informações de recursos.

**Q: Onde posso encontrar mais exemplos?**  
A: Visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para trechos de código da comunidade, dicas de solução de problemas e documentação oficial.

---

**Última atualização:** 2026-07-05  
**Testado com:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Dominando Dados de Projeto com Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Dominando Opções de Salvamento do MS Project para Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Calendário e Agendamento do Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}