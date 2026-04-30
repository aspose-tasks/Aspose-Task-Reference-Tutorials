---
date: 2026-04-30
description: Aprenda a definir a linha de base e manipular linhas de base de projetos
  de forma eficiente usando Aspose.Tasks para .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Tipos diferentes de linhas de base no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como definir a linha de base no Aspose.Tasks – Tipos diferentes de linha de
  base
url: /pt/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diferentes Tipos de Linhas de Base no Aspose.Tasks

## Introdução

Na gestão de projetos, **como definir a linha de base** corretamente pode fazer a diferença entre um projeto que permanece no caminho certo e um que sai de controle. Aspose.Tasks para .NET oferece uma API completa para criar, atualizar e comparar linhas de base, permitindo que você **acompanhe o progresso do projeto** em relação ao plano original. Neste tutorial você aprenderá como definir uma linha de base, trabalhar com múltiplos tipos de linha de base e usar os dados para analisar o **cronograma da linha de base versus o real** do seu projeto.

## Respostas Rápidas
- **O que é uma linha de base?** Uma captura do cronograma, custo e dados de trabalho tirada em um ponto específico de um projeto.  
- **Quantas linhas de base o Aspose.Tasks pode armazenar?** Até 11 linhas de base distintas por projeto.  
- **Por que definir uma linha de base?** Para comparar o desempenho real com o plano original e identificar variações.  
- **Preciso de uma licença para experimentar?** Um teste gratuito está disponível; uma licença é necessária para uso em produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “como definir linha de base” no Aspose.Tasks?
Definir uma linha de base significa chamar o método `SetBaseline` em um objeto `Project`. A API permite escolher entre vários valores de `BaselineType` (Baseline, Baseline1 … Baseline10) para que você possa manter capturas históricas à medida que o projeto evolui.

## Por que gerenciar linhas de base do projeto?
- **Medir variação:** Veja rapidamente se as tarefas estão adiantadas ou atrasadas em relação ao cronograma.  
- **Controle de custos:** Compare o custo da linha de base com o gasto real.  
- **Relatórios para stakeholders:** Exporte os dados da linha de base para PDF, XLSX ou outros formatos para comunicação clara.  
- **Planejamento de cenários:** Armazene múltiplas linhas de base para avaliar cronogramas “e se”.

## Pré-requisitos

### 1. Familiaridade com C# e .NET Framework
É necessário ter uma compreensão básica de classes, métodos e conceitos orientados a objetos em C#.

### 2. Instalação do Aspose.Tasks para .NET
Certifique‑se de que a biblioteca foi adicionada ao seu projeto. Você pode baixá‑la no [site do Aspose.Tasks](https://releases.aspose.com/tasks/net/) ou instalá‑la via NuGet.

### 3. Ambiente de Desenvolvimento Integrado (IDE)
Visual Studio (ou qualquer IDE compatível) é recomendado para escrever, compilar e depurar código C#.

## Importar Namespaces

Antes de começarmos a trabalhar com Aspose.Tasks em nosso projeto C#, precisamos importar os namespaces necessários para acessar as classes e métodos requeridos. Siga estes passos:

```csharp

```

Agora que configuramos nossos pré-requisitos e importamos os namespaces necessários, vamos mergulhar na definição de diferentes tipos de linhas de base usando Aspose.Tasks para .NET. Dividiremos cada exemplo em várias etapas para clareza e facilidade de compreensão.

## Como Definir Linha de Base no Aspose.Tasks

### Etapa 1: Carregar o Arquivo do Projeto
Primeiro, precisamos carregar o arquivo do projeto no qual pretendemos definir a linha de base. Esta etapa envolve inicializar um objeto `Project` e carregar o arquivo do projeto. Veja como fazer isso:

```csharp
var project = new Project("Project2.mpp");
```

### Etapa 2: Definir Linha de Base
Depois que o projeto for carregado, podemos prosseguir para definir a linha de base. As linhas de base fornecem uma captura do cronograma inicial do projeto, que serve como ponto de referência para comparação à medida que o projeto avança. Use o método `SetBaseline` para definir a linha de base. Por exemplo, para definir a linha de base para todo o projeto, use a enumeração `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Etapa 3: Trabalhar com Linhas de Base do Projeto
Depois de definir a linha de base, você pode trabalhar com vários campos de linha de base do projeto para analisar e acompanhar o progresso do projeto com precisão. Esta etapa envolve acessar dados da linha de base, como datas de início, datas de término, durações e custos. É aqui que você pode aproveitar o conjunto rico de recursos fornecidos pelo Aspose.Tasks para manipular os dados da linha de base de acordo com suas necessidades.

## Problemas Comuns e Soluções
- **Linha de base não aplicada:** Certifique‑se de que o arquivo do projeto seja salvo após chamar `SetBaseline`. Use `project.Save("output.mpp");` se precisar persistir as alterações.  
- **Conflito de múltiplas linhas de base:** Ao definir mais de uma linha de base, especifique o `BaselineType` correto (por exemplo, `Baseline1`, `Baseline2`).  
- **Incompatibilidade de versão:** Verifique se a versão da DLL do Aspose.Tasks corresponde ao runtime .NET alvo.

## Perguntas Frequentes

**Q: Posso definir múltiplas linhas de base para um único projeto usando Aspose.Tasks para .NET?**  
A: Sim, o Aspose.Tasks permite definir até 11 linhas de base para um projeto, oferecendo recursos de acompanhamento abrangentes.

**Q: O Aspose.Tasks é compatível com diferentes formatos de arquivo de projeto?**  
A: Absolutamente! O Aspose.Tasks suporta vários formatos de arquivo de projeto, como MPP, XML e MPX, garantindo compatibilidade em diferentes plataformas.

**Q: Como posso visualizar os dados da linha de base no meu projeto?**  
A: Você pode usar o Aspose.Tasks para exportar os dados do projeto para formatos populares como PDF ou XLSX, facilitando a visualização e o compartilhamento das informações da linha de base.

**Q: O Aspose.Tasks oferece suporte para integração com ferramentas de gerenciamento de projetos?**  
A: O Aspose.Tasks fornece documentação extensa e fóruns de suporte para ajudar desenvolvedores a integrar perfeitamente seus recursos com ferramentas e plataformas populares de gerenciamento de projetos.

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Sim, você pode explorar o Aspose.Tasks por meio de um teste gratuito disponível no site, permitindo que experimente suas funcionalidades diretamente.

**Última atualização:** 2026-04-30  
**Testado com:** Aspose.Tasks for .NET (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}