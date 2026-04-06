---
date: 2026-04-06
description: Aprenda como excluir todas as linhas de base e gerenciar coleções de
  linhas de base no Aspose.Tasks para .NET com exemplos de código passo a passo.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Excluir todas as linhas de base com a coleção de linhas de base do Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Excluir todas as linhas de base usando a coleção de linhas de base do Aspose.Tasks
url: /pt/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Excluir Todas as Linhas de Base com a Coleção de Linhas de Base do Aspose.Tasks

## Introdução

Aspose.Tasks for .NET permite que você manipule arquivos do Microsoft Project diretamente de suas aplicações .NET. Um dos recursos mais poderosos é a capacidade de **excluir todas as linhas de base** para um recurso, o que é essencial quando você precisa redefinir os dados de acompanhamento de um projeto ou iniciar um novo período de linha de base. Neste tutorial, percorreremos todo o processo — desde o carregamento de um arquivo de projeto até a remoção de cada linha de base anexada a um recurso específico — usando explicações claras e conversacionais e código C# pronto‑para‑executar.

## Respostas Rápidas
- **O que faz “excluir todas as linhas de base”?** Remove cada registro de linha de base armazenado para um recurso selecionado, limpando os dados históricos de custo e trabalho.  
- **Por que eu precisaria disso?** Para redefinir o acompanhamento após uma grande mudança no projeto ou quando as linhas de base originais não são mais relevantes.  
- **Qual biblioteca fornece essa capacidade?** Aspose.Tasks for .NET.  
- **Preciso de uma licença?** Uma licença válida do Aspose.Tasks é necessária para uso em produção; uma versão de avaliação gratuita está disponível.  
- **O código é compatível com .NET 6+?** Sim, a API funciona com .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6.

## O que é uma Linha de Base e Por que Excluir Todas as Linhas de Base?

Uma linha de base captura o plano original de custo, trabalho e cronograma em um ponto específico no tempo. Ao longo da vida de um projeto, você pode criar várias linhas de base (Baseline 1, Baseline 2, etc.) para comparar o progresso real com diferentes instantâneos de planejamento. No entanto, há cenários — como uma redefinição de escopo do projeto ou um novo começo — onde manter essas linhas de base históricas se torna confuso. Excluir todas as linhas de base fornece uma tela limpa, permitindo que você defina novas linhas de base que reflitam a realidade atual.

## Pré-requisitos

1. **Visual Studio** – qualquer edição recente (Community, Professional ou Enterprise).  
2. **Aspose.Tasks for .NET** – faça o download a partir do [download link](https://releases.aspose.com/tasks/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável com variáveis, loops e saída de console.  
4. **Um arquivo Microsoft Project** (`.mpp`) – um arquivo de exemplo chamado *WorkWithBaselineCollection.mpp* será usado nos exemplos.

## Importar Namespaces

Primeiro, traga os namespaces necessários para o escopo para que o compilador saiba onde encontrar as classes que usaremos.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Etapa 1: Carregar o Arquivo de Projeto

Começamos carregando um arquivo de Projeto existente. Ajuste `DataDir` para apontar para a pasta que contém seu arquivo `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Etapa 2: Obter o Recurso Alvo

Para demonstração, buscamos o recurso com UID = 1. Em um cenário real, você localizará o recurso por nome ou outro identificador.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Etapa 3: Exibir Informações da Linha de Base Existente

Antes de excluir qualquer coisa, é útil ver quais linhas de base estão atualmente anexadas ao recurso. Isso lhe dá confiança de que está removendo os dados corretos.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Etapa 4: Iterar por Todas as Linhas de Base

Aqui iteramos por cada linha de base, imprimindo métricas chave como custo, trabalho e valor ganho (BCWP/BCWS). Esta etapa é opcional, mas útil para registro ou fins de auditoria.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Excluir Todas as Linhas de Base

Agora executamos a ação principal: **excluir todas as linhas de base** para o recurso selecionado. Primeiro copiamos a coleção para uma lista para evitar modificar a coleção enquanto iteramos, então removemos cada linha de base uma a uma.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Depois que este bloco for executado, `resource.Baselines.Count` será `0`, confirmando que todos os registros de linha de base foram limpos.

## Problemas Comuns e Dicas

- **NullReferenceException** – Certifique-se de que o arquivo de projeto realmente contém o recurso que você está direcionando; caso contrário, `GetByUid` retornará `null`.  
- **Licenciamento** – Sem uma licença válida do Aspose.Tasks, você verá uma marca d'água na saída e funcionalidade limitada.  
- **Desempenho** – Para projetos muito grandes, considere iterar com `Parallel.ForEach` para acelerar o processo de remoção, mas lembre-se de que a coleção subjacente não é segura para threads.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com arquivos de projeto grandes?**  
**A:** Sim, o Aspose.Tasks está otimizado para desempenho e pode processar arquivos `.mpp` de vários gigabytes de forma eficiente.

**Q: A biblioteca é compatível com todas as versões do Microsoft Project?**  
**A:** O Aspose.Tasks suporta o Project 2000 até o Project 2024, abrangendo tanto os formatos `.mpp` mais antigos quanto os arquivos baseados em XML mais recentes.

**Q: Posso personalizar as linhas de base antes de excluí‑las?**  
**A:** Absolutamente. Você pode ler ou modificar qualquer propriedade da linha de base (custo, trabalho, datas) antes de decidir removê‑la.

**Q: O Aspose.Tasks funciona em plataformas de nuvem?**  
**A:** Sim, a API funciona em qualquer ambiente compatível com .NET, incluindo Azure App Service, AWS Lambda (via .NET Core) e contêineres Docker.

**Q: Onde posso pedir ajuda à comunidade?**  
**A:** Visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para conectar-se com outros desenvolvedores e a equipe da Aspose.

## Conclusão

Neste guia demonstramos como **excluir todas as linhas de base** de um recurso usando Aspose.Tasks for .NET. Seguindo o código passo a passo, você pode redefinir os dados de linha de base, manter o acompanhamento do seu projeto limpo e preparar seu cronograma para um novo ciclo de planejamento. Sinta‑se à vontade para experimentar a criação de novas linhas de base após a exclusão para ver como a biblioteca atualiza o arquivo de projeto.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}