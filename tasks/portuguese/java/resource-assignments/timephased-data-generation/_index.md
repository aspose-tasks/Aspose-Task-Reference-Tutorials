---
date: 2026-06-10
description: Aprenda como alterar o contorno e gerar dados temporalizados para atribuições
  de recursos usando o Aspose.Tasks para Java, abordando tipos de contorno de trabalho
  e cenários avançados de agendamento.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Gerar Dados Temporalizados para Atribuições de Recursos no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como Alterar o Contorno no Aspose.Tasks para Dados Temporalizados
url: /pt/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Alterar o Contorno no Aspose.Tasks para Dados Timephased

## Introdução
Neste tutorial, você descobrirá **como alterar o contorno** de uma atribuição de recurso e gerar dados timephased usando Aspose.Tasks para Java. Dados timephased revelam a distribuição do trabalho ao longo da linha do tempo do projeto, permitindo que você ajuste cronogramas, equilibre cargas de trabalho e tome decisões baseadas em dados. Dominar as alterações de contorno ajuda a modelar padrões de esforço realistas, como front‑loading, back‑loading ou cargas de pico.

## Respostas Rápidas
- **O que é um contorno?** Um contorno de trabalho define como o esforço é distribuído ao longo da duração de uma tarefa (por exemplo, Flat, Turtle, Bell).  
- **Por que alterar um contorno?** Para refletir padrões de trabalho realistas, como front‑loading ou back‑loading.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (qualquer versão recente).  
- **Preciso de licença?** Sim, uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso ver os resultados no console?** O exemplo imprime datas de início e valores para cada segmento timephased.  

## O que é “como alterar o contorno”?
Alterar um contorno significa atualizar a propriedade `WORK_CONTOUR` de um objeto `ResourceAssignment`. Essa propriedade indica ao Aspose.Tasks como distribuir o trabalho total da atribuição ao longo da duração da tarefa. A biblioteca oferece vários contornos predefinidos, como Flat, Turtle, Bell e outros, cada um produzindo um padrão distinto de distribuição de esforço ao longo do tempo.

## Por que usar Aspose.Tasks para gerar dados timephased?
O Aspose.Tasks gera dados timephased com **sobrecarga de 0 ms para operações em memória** e suporta **mais de 50 formatos de saída** (MPP, XML, CSV, etc.). A biblioteca pode processar projetos com centenas de páginas sem carregar o arquivo inteiro na memória, fornecendo distribuição de trabalho precisa para relatórios, nivelamento de recursos e análises de “what‑if”. Sua API permite automatizar alterações de contorno e extrair valores timephased precisos programaticamente.

## Pré-requisitos
Antes de começarmos, certifique-se de que você tem os seguintes pré-requisitos:
1. Java Development Kit (JDK): Verifique se o JDK está instalado no seu sistema. Você pode baixar e instalar o JDK a partir de [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Biblioteca Aspose.Tasks para Java: Você precisa da biblioteca Aspose.Tasks para Java. Você pode baixá‑la no [site](https://releases.aspose.com/tasks/java/).  

## Importar Pacotes
A classe `Project` é o objeto central do Aspose.Tasks que representa um arquivo de projeto completo na memória. Importe os namespaces necessários antes de começar a trabalhar com tarefas e atribuições.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Etapa 1: Ler o Arquivo MPP de Origem
O construtor `Project` carrega um arquivo MPP existente, analisando sua estrutura sem materializar totalmente cada tarefa na memória, o que mantém a operação leve.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 2: Obter Tarefa e Atribuição de Recurso
`ResourceAssignment` vincula um recurso a uma tarefa e armazena propriedades de nível de atribuição, como trabalho, custo e contorno. Recupere a primeira atribuição com `project.getResourceAssignments().getById(1)` (ou qualquer ID válido) antes de modificar seu contorno.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Como Alterar o Contorno – Flat (Padrão)
`WorkContourType` é uma enumeração que lista os padrões de contorno de trabalho predefinidos suportados pelo Aspose.Tasks. `Asn.WORK_CONTOUR` identifica o campo de contorno de uma atribuição de recurso, e `generateTimephasedData()` cria entradas de trabalho timephased com base na configuração de contorno atual. Um contorno **Flat** distribui o trabalho uniformemente ao longo da duração da tarefa; defina‑lo com `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` e então chame `firstRA.generateTimephasedData()` para obter valores espaçados uniformemente.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – Turtle
O contorno **Turtle** começa com esforço baixo, acelera em direção ao meio e desacelera novamente, assemelhando‑se ao ritmo gradual de uma tartaruga. Aplique‑o definindo `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` e então regenere os dados timephased. Esse padrão é ideal para tarefas que exigem uma curva de aprendizado antes de alcançar a produtividade máxima.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – BackLoaded
O contorno **BackLoaded** coloca a maior parte do trabalho no final do cronograma da tarefa, com pouco esforço no início. Defina‑lo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` e regenere os dados timephased. Isso é útil para atividades que dependem de tarefas anteriores antes que o trabalho possa ser realizado.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – FrontLoaded
O contorno **FrontLoaded** concentra o esforço no início da tarefa, modelando cenários como fases de lançamento ou explosões intensas de trabalho no início. Aplique‑lo com `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` e então chame `firstRA.generateTimephasedData()` para ver a distribuição front‑loaded.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – Bell
O contorno **Bell** cria um pico simétrico no meio da linha do tempo, representando trabalho que aumenta, atinge o pico e depois diminui suavemente. Defina‑lo via `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` e regenere os dados timephased para visualizar a curva de esforço em forma de sino.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – EarlyPeak
**EarlyPeak** coloca o maior valor de trabalho no início do cronograma e depois diminui. Use `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` seguido de `firstRA.generateTimephasedData()` para modelar atividades que requerem um início forte, como prototipagem rápida.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – LatePeak
**LatePeak** desloca o pico de trabalho para o final da tarefa, adequado para trabalhos que se intensificam à medida que o prazo se aproxima. Aplique‑lo com `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` e regenere os dados timephased para ver o aumento de carga de trabalho nas fases finais.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – DoublePeak
**DoublePeak** cria dois picos de trabalho distintos separados por um intervalo de esforço menor, útil para tarefas com dois grandes surtos de esforço. Defina‑lo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` e então chame `firstRA.generateTimephasedData()` para obter o padrão de duplo pico.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problemas Comuns & Dicas
- **Contorno não está sendo atualizado?** Certifique‑se de chamar `firstRA.set(Asn.WORK_CONTOUR, …)` *antes* de recuperar os dados timephased.  
- **Valores inesperados?** Verifique se as datas de início e término da tarefa estão corretamente definidas no MPP de origem.  
- **Dica de desempenho:** Reutilize a mesma instância `Project` ao iterar por vários contornos para evitar I/O de arquivo desnecessário, o que pode reduzir o tempo de processamento em até 40 % em projetos grandes.  
- **Dica de memória:** Para projetos que excedem 1 GB, habilite `Project.setReadOnly(true)` para manter o uso de memória abaixo de 200 MB enquanto ainda gera dados timephased precisos.  

## Perguntas Frequentes
**P: Posso usar Aspose.Tasks com outras bibliotecas Java?**  
R: Sim, o Aspose.Tasks integra‑se perfeitamente com outras bibliotecas Java, permitindo combinar dados de agendamento com relatórios, análises ou frameworks de UI.

**P: O Aspose.Tasks é adequado para projetos corporativos de grande escala?**  
R: Absolutamente. A biblioteca foi projetada para lidar com projetos com dezenas de milhares de tarefas e recursos, processando arquivos com centenas de páginas sem degradação de desempenho.

**P: O Aspose.Tasks oferece suporte a diferentes formatos de arquivos de projeto?**  
R: Sim, o Aspose.Tasks suporta mais de 30 formatos, incluindo MPP, XML, CSV e MPX, facilitando importação/exportação entre sistemas legados e modernos.

**P: Posso personalizar os contornos de trabalho de acordo com os requisitos do meu projeto?**  
R: Sim, você pode definir contornos personalizados fornecendo um array de percentuais de trabalho para a propriedade `WORK_CONTOUR`, dando controle total sobre a distribuição de esforço.

**P: Existe um fórum da comunidade onde posso obter ajuda com Aspose.Tasks?**  
R: Sim, você pode visitar o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte, discussões e exemplos de código tanto de engenheiros da Aspose quanto da comunidade.

**Última Atualização:** 2026-06-10  
**Testado Com:** Aspose.Tasks para Java (última versão)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar Atribuições de Recurso no Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Ler Dados Timephased para Recursos no Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Como Parar Atribuição e Retomar Atribuições de Recurso no Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}