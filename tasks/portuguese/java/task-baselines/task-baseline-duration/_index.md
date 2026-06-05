---
date: 2026-01-23
description: Aprenda como definir a duração da linha de base e criar uma instância
  de projeto usando Aspose.Tasks para Java. Este guia passo a passo ajuda você a gerenciar
  linhas de base de tarefas de forma eficiente.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Como definir a duração da linha de base no Aspose.Tasks para Java
url: /pt/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir a Duração da Linha de Base no Aspose.Tasks para Java

## Introdução
Definir uma linha de base é uma etapa fundamental para acompanhar o progresso do projeto em relação ao plano original. Neste tutorial, você aprenderá **como definir a duração da linha de base** para tarefas no Microsoft Project usando a biblioteca Aspose.Tasks para Java, e verá por que estabelecer uma linha de base cedo pode economizar tempo e dores de cabeça mais tarde.

## Respostas Rápidas
- **O que significa “definir linha de base”?** Ele registra o início, término e duração originais de uma tarefa para que você possa comparar mudanças futuras.  
- **Qual classe do Aspose.Tasks cria um projeto?** A classe `Project` – você também aprenderá como **criar instância de projeto** corretamente.  
- **Preciso de uma licença para executar o código?** Uma licença de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso recuperar linhas de base intermediárias?** Sim, o Aspose.Tasks permite consultar linhas de base intermediárias e seus custos fixos.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendado.

## O que é uma linha de base de tarefa e por que defini‑la?
Uma linha de base de tarefa captura o cronograma planejado (data de início, data de término e duração) em um ponto específico no tempo. Ao definir uma linha de base, você cria um ponto de referência que facilita a identificação de desvios de cronograma, estouros de custos e superalocação de recursos à medida que o projeto evolui.

## Por que usar o Aspose.Tasks para gerenciamento de linhas de base?
- **Compatibilidade total com .mpp** – ler e gravar arquivos nativos do Microsoft Project sem precisar do Office instalado.  
- **API rica** – acessar dados de linha de base, linhas de base intermediárias e informações faseadas no tempo programaticamente.  
- **Multiplataforma** – funciona no Windows, Linux e macOS com qualquer JDK padrão.

## Pré‑requisitos
1. **Ambiente de Desenvolvimento Java** – JDK 8+ instalado e configurado.  
2. **Aspose.Tasks para Java** – baixe a biblioteca [aqui](https://releases.aspose.com/tasks/java/).  
3. **IDE ou ferramenta de build** – Maven, Gradle ou qualquer IDE que preferir.

## Importar Pacotes
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Etapa 1: Criar uma Instância de Projeto
Creating a project instance is the foundation for any further manipulation. This step shows how to **create project instance** using Aspose.Tasks:

```java
Project project = new Project();
```

## Etapa 2: Criar uma Linha de Base de Tarefa
Add a new task to the project’s root and set its baseline. This records the original schedule for the task:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Etapa 3: Exibir Informações da Linha de Base da Tarefa
Retrieve the baseline you just created and print its key properties. This helps you verify that the baseline was set correctly:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Etapa 4: Verificar Linha de Base Intermediária e Custo Fixo
If you’re working with interim baselines, you can query whether the current baseline is interim and any associated fixed cost:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Etapa 5: Imprimir Dados Faseados no Tempo
Time‑phased data shows how the baseline is distributed over time. Loop through the collection to inspect each entry:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Seguindo estas etapas, você pode **definir a duração da linha de base** para qualquer tarefa e recuperar informações detalhadas da linha de base usando o Aspose.Tasks para Java.

## Problemas Comuns e Soluções
- **Linha de base não aparece no MS Project:** Certifique-se de que chamou `project.setBaseline(BaselineType.Baseline)` **depois** de adicionar a tarefa.  
- **NullPointerException em `getBaselines()`:** Verifique se a tarefa foi adicionada ao projeto antes de definir a linha de base.  
- **Incompatibilidade de unidade de tempo:** Use `TimeUnitType` para formatar a duração corretamente, especialmente ao trabalhar com calendários personalizados.

## Perguntas Frequentes
### O que é uma linha de base de tarefa no MS Project?
Uma linha de base de tarefa no MS Project é uma captura do cronograma planejado inicial para uma tarefa, incluindo sua data de início, data de término e duração.

### Por que gerenciar linhas de base de tarefa é importante?
Gerenciar linhas de base de tarefa ajuda a comparar o cronograma planejado com o progresso real do projeto, facilitando um melhor acompanhamento e tomada de decisão.

### Posso modificar uma linha de base de tarefa depois de definida?
Sim, você pode modificar linhas de base de tarefa no MS Project para refletir mudanças no plano do projeto. Contudo, é essencial documentar quaisquer desvios da linha de base original.

### O Aspose.Tasks suporta outras funcionalidades de gerenciamento de projetos?
Sim, o Aspose.Tasks oferece uma ampla gama de recursos para gerenciamento de projetos, incluindo agendamento de tarefas, alocação de recursos e geração de diagramas de Gantt.

### Onde posso encontrar suporte para o Aspose.Tasks?
Você pode encontrar suporte para o Aspose.Tasks no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), onde pode fazer perguntas e interagir com outros usuários.

## Perguntas Frequentes Adicionais
**Q: Preciso chamar `setBaseline` para cada tarefa individualmente?**  
A: Não. Chamar `project.setBaseline(BaselineType.Baseline)` registra a linha de base para todas as tarefas do projeto de uma só vez.

**Q: Como posso definir uma linha de base intermediária para uma tarefa específica?**  
A: Use `project.setBaseline(BaselineType.Baseline1)` (ou Baseline2‑Baseline10) após atualizar o cronograma da tarefa.

**Q: É possível exportar os dados da linha de base para CSV?**  
A: Sim. Itere sobre `task.getBaselines()` e escreva os campos desejados em um arquivo CSV usando I/O padrão do Java.

**Q: Posso ler um arquivo .mpp existente que já contém linhas de base?**  
A: Absolutamente. Carregue o arquivo com `new Project("myproject.mpp")` e então acesse as linhas de base de cada tarefa como mostrado acima.

**Q: O Aspose.Tasks lida com arquivos multi‑projeto?**  
A: O Aspose.Tasks funciona com arquivos .mpp de projeto único. Para cenários multi‑projeto, combine os projetos programaticamente.

---

**Última Atualização:** 2026-01-23  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}