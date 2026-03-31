---
date: 2026-03-19
description: Aprenda a definir a linha de base do projeto e a gerenciar linhas de
  base de atribuições de forma eficiente com o Aspose.Tasks para .NET, garantindo
  o acompanhamento preciso do progresso do projeto.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Definir Linha de Base do Projeto – Gerenciando a Linha de Base da Atribuição
  no Aspose.Tasks
url: /pt/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Linha de Base do Projeto – Gerenciando Linha de Base de Atribuição no Aspose.Tasks

## Introdução

Ao trabalhar em tarefas de gerenciamento de projetos, **setting a project baseline** é essencial para medir o progresso real em relação ao plano original. Aspose.Tasks for .NET não apenas permite **set project baseline**, mas também oferece controle total sobre linhas de base de atribuição, permitindo um acompanhamento preciso do desempenho. Neste tutorial percorreremos todo o processo — carregar um projeto, definir uma linha de base, ler os dados da linha de base de atribuição e comparar linhas de base — para que você possa monitorar seus projetos com confiança.

## Respostas Rápidas
- **O que significa “set project baseline”?** Ele registra os dados originais de cronograma e custo para comparação posterior com o desempenho real.  
- **Qual método da API define uma linha de base?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **As linhas de base de atribuição requerem uma chamada separada?** Não, elas são armazenadas automaticamente quando você define uma linha de base do projeto.  
- **Quais formatos são suportados?** MPP, XML, MPX e mais via Aspose.Tasks.  
- **É necessária uma licença para produção?** Sim, uma licença comercial é necessária para uso que não seja de avaliação.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem:

- Conhecimento básico de programação em C#.  
- Visual Studio (qualquer versão recente).  
- Biblioteca Aspose.Tasks for .NET adicionada ao seu projeto. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/net/).  
- Acesso a um arquivo de projeto no formato MPP (por exemplo, `AssignmentBaseline2007.mpp`).

## Importar Namespaces

Adicione os namespaces necessários no início do seu arquivo C# para que o compilador saiba onde encontrar as classes do Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Etapa 1: Carregar Projeto e Definir Linha de Base do Projeto

Primeiro, carregue o arquivo MPP existente e então chame `SetBaseline` para **set project baseline** para todo o projeto.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Etapa 2: Ler Informações da Linha de Base de Atribuição

Depois que a linha de base for definida, cada atribuição de recurso contém seus próprios registros de linha de base. O loop abaixo extrai e imprime esses detalhes, incluindo datas de início/fim, custo, trabalho e quaisquer dados faseados no tempo.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Etapa 3: Comparar Linhas de Base de Atribuição

Você pode comparar linhas de base de diferentes atribuições usando os operadores de igualdade e comparação incorporados. Isso é útil quando você precisa detectar alterações de cronograma ou estouros de custo entre tarefas.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Problemas Comuns e Soluções

| Problema | Por que acontece | Solução |
|----------|-------------------|---------|
| **Os dados da linha de base aparecem vazios** | O arquivo de projeto foi aberto em modo somente‑leitura ou a linha de base nunca foi definida. | Chame `project.SetBaseline(BaselineType.Baseline)` antes de ler as linhas de base de atribuição. |
| **`NullReferenceException` on `TimephasedData`** | Nem todas as linhas de base contêm entradas faseadas no tempo. | Sempre verifique `baseline.TimephasedData != null` (conforme mostrado no código). |
| **Recuperação de UID incorreta** | Os valores de UID diferem entre versões de arquivo. | Use `ResourceAssignments.GetByUid` com o UID correto ou itere para encontrar a atribuição que você precisa. |

## Perguntas Frequentes

**P:** O Aspose.Tasks pode lidar com múltiplas linhas de base para uma única atribuição?  
**R:** Sim, o Aspose.Tasks suporta múltiplas linhas de base para cada atribuição, permitindo um acompanhamento abrangente do progresso do projeto ao longo do tempo.

**P:** O Aspose.Tasks é compatível com vários formatos de arquivo de projeto além do MPP?  
**R:** Sim, o Aspose.Tasks suporta uma ampla variedade de formatos de arquivo de projeto, incluindo XML, MPX e MPP, garantindo compatibilidade com diversas ferramentas de gerenciamento de projetos.

**P:** Posso modificar informações de linha de base programaticamente usando o Aspose.Tasks?  
**R:** Absolutamente, o Aspose.Tasks fornece APIs extensas para modificar informações de linha de base dinamicamente de acordo com os requisitos do projeto, oferecendo flexibilidade e controle sobre os processos de gerenciamento de projetos.

**P:** O Aspose.Tasks oferece documentação e recursos de suporte para desenvolvedores?  
**R:** Sim, os desenvolvedores podem acessar documentação abrangente, tutoriais e fóruns no site do Aspose.Tasks, facilitando a integração e a solução de problemas.

**P:** Existe uma versão de avaliação disponível para o Aspose.Tasks for .NET?  
**R:** Sim, os desenvolvedores podem obter uma versão de avaliação gratuita do Aspose.Tasks for .NET [aqui](https://releases.aspose.com/), permitindo avaliar seus recursos e capacidades antes de tomar uma decisão de compra.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-19  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose