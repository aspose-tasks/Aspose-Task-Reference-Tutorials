---
date: 2026-01-15
description: Aprenda a trabalhar com o custo orçado de trabalho programado em arquivos
  do Microsoft Project usando Aspose.Tasks para Java. Siga nosso guia passo a passo.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: custo orçado do trabalho programado com Aspose.Tasks para Java
url: /pt/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# custo orçado do trabalho programado com Aspose.Tasks for Java

## Introdução

Gerenciar **budgeted cost work scheduled** (BCWS) é essencial para manter um projeto no caminho certo e garantir que a previsão financeira esteja alinhada com o trabalho planejado. No Microsoft Project, BCWS representa a quantia de dinheiro que deveria ter sido gasta para o trabalho programado até uma data específica. Aspose.Tasks for Java fornece controle programático total sobre esses valores, permitindo ler, modificar e relatar custos de recursos sem nunca abrir o arquivo .mpp manualmente. Neste tutorial, percorreremos um exemplo completo que mostra como carregar um projeto, iterar sobre seus recursos e exibir o **budgeted cost work scheduled** ao lado de outras métricas de custo importantes.

## Respostas Rápidas
- **O que significa BCWS?** Budgeted Cost Work Scheduled – o custo planejado para o trabalho programado até a data.  
- **Qual propriedade da API recupera BCWS?** `Rsc.BCWS` em um objeto `Resource`.  
- **Preciso de uma licença para executar o exemplo?** Uma licença de avaliação gratuita funciona para testes; uma licença completa é necessária para produção.  
- **Posso modificar os valores de BCWS?** Sim, você pode definir `Rsc.BCWS` como qualquer outro campo numérico.  
- **Versões de Project suportadas?** Todas as versões do Microsoft Project de 2000 até o formato .mpp mais recente.

## O que é budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** é uma medida de desempenho que reflete o custo que deveria ter sido incorrido para o trabalho planejado até um determinado ponto no tempo. É um alicerce do Earned Value Management (EVM) e ajuda os gerentes de projeto a comparar o planejado com o gasto real.

## Pré-requisitos

Antes de mergulhar no código, certifique‑se de que você tem:

1. Um sólido domínio dos fundamentos de Java.  
2. Aspose.Tasks for Java adicionado ao seu projeto (Maven/Gradle ou JAR).  
3. Um arquivo Microsoft Project (`.mpp`) que contém recursos com dados de custo (por exemplo, *ResourceCosts.mpp*).

## Importar Pacotes

Primeiro, importe as classes Aspose.Tasks necessárias para manipular projetos e recursos:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Etapa 1: Definir o Diretório de Dados

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto ou relativo onde *ResourceCosts.mpp* está localizado.

## Etapa 2: Carregar o Arquivo MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

O construtor `Project` lê o arquivo .mpp e constrói uma representação em memória que você pode consultar.

## Etapa 3: Iterar pelos Recursos

```java
for (Resource res : prj.getResources()) {
```

Este loop percorre cada recurso definido no projeto, proporcionando acesso aos seus campos de custo.

## Etapa 4: Verificar Nome e Custos do Recurso

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Dentro do bloco `if` nós:

* Imprimir o **total cost** (`Rsc.COST`).  
* Imprimir o **actual cost of work performed** (`Rsc.ACWP`).  
* Imprimir o **budgeted cost work scheduled** (`Rsc.BCWS`) – a métrica principal que estamos focando.  
* Imprimir o **budgeted cost work performed** (`Rsc.BCWP`).  

Esses quatro valores fornecem uma visão rápida de onde o projeto está financeiramente.

## Por que monitorar budgeted cost work scheduled é importante

* **Alerta precoce:** Se o BCWS for significativamente maior que o custo real, você pode estar superalocando recursos.  
* **Análise de Valor Ganhado:** BCWS é uma entrada chave para calcular Cost Variance (CV) e Schedule Variance (SV).  
* **Previsão:** Dados precisos de BCWS ajudam a prever necessidades futuras de fluxo de caixa e informam relatórios aos stakeholders.

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| `null` impresso para BCWS | O recurso não tem tabela de taxa de custo definida | Defina uma tabela de taxa de custo para o recurso no Microsoft Project ou configure‑a programaticamente via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` ao iterar recursos | Arquivo .mpp corrompido ou contém entradas de recurso vazias | Valide o arquivo .mpp no Microsoft Project e remova recursos vazios |
| Valores inesperados (ex.: BCWS negativo) | Campos personalizados sobrescrevendo campos de custo padrão | Certifique-se de que está acessando o `Rsc.BCWS` padrão e não um campo personalizado com o mesmo nome |

## Perguntas Frequentes

**P: Posso atualizar o valor de BCWS programaticamente?**  
R: Sim. Use `res.set(Rsc.BCWS, newValue)` e então salve o projeto com `prj.save("Updated.mpp")`.

**P: Aspose.Tasks suporta projetos multi‑moeda?**  
R: Absolutamente. Os campos de custo respeitam as configurações de moeda definidas no arquivo Project.

**P: Existe uma maneira de exportar essas métricas de custo para CSV?**  
R: Você pode iterar sobre os recursos e gravar os valores em um `StringBuilder` ou usar uma biblioteca CSV para gerar o arquivo.

**P: Como o BCWS difere do BCWP?**  
R: BCWS é o custo planejado para o trabalho programado, enquanto BCWP (Budgeted Cost Work Performed) reflete o custo planejado para o trabalho que já foi concluído.

**P: Preciso de uma licença especial para ler dados de custo?**  
R: A licença de avaliação fornece acesso total de leitura/escrita; uma licença comercial é necessária para implantações em produção.

## Conclusão

Ao aproveitar o Aspose.Tasks for Java, você obtém acesso preciso e programático ao **budgeted cost work scheduled** e a outras métricas de custo vitais. Isso permite criar dashboards personalizados, automatizar relatórios de Earned Value e manter seus projetos financeiramente no caminho certo — tudo sem interação manual com o Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose