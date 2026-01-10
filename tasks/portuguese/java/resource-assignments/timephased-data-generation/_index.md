---
date: 2026-01-10
description: Aprenda a alterar o contorno e gerar dados temporais para atribuições
  de recursos usando Aspose.Tasks para Java, melhorando a eficiência da gestão de
  projetos.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como Alterar o Contorno no Aspose.Tasks para Dados com Fase Temporal
url: /pt/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Alterar o Contorno no Aspose.Tasks para Dados Timephased

## Introdução
Neste tutorial, você descobrirá **como alterar o contorno** para uma atribuição de recurso e gerar dados timephased usando Aspose.Tasks para Java. Dados timephased revelam a distribuição do trabalho ao longo da linha do tempo do projeto, permitindo que você ajuste cronogramas, equilibre cargas de trabalho e tome decisões baseadas em dados.

## Respostas Rápidas
- **O que é um contorno?** Um contorno de trabalho define como o esforço é distribuído ao longo da duração de uma tarefa (por exemplo, Flat, Turtle, Bell).  
- **Por que mudar um contorno?** Para refletir padrões de trabalho realistas, como carregamento frontal ou carregamento traseiro de esforço.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (qualquer versão recente).  
- **Preciso de licença?** Sim, uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso ver os resultados no console?** O exemplo imprime datas de início e valores para cada segmento timephased.

## O que é “como mudar o contorno”?
Mudar um contorno significa atualizar a propriedade `WORK_CONTOUR` de um `ResourceAssignment`. Aspose.Tasks suporta vários contornos predefinidos (Flat, Turtle, Bell, etc.) que influenciam como o trabalho é alocado ao longo do tempo.

## Por que usar o Aspose.Tasks para gerar dados timephased?
- **Relatórios precisos:** Exportar distribuição de trabalho precisa para ferramentas de relatório.  
- **Planejamento de cenários:** Testar diferentes contornos sem alterar o cronograma original.  
- **Automação:** Integrar em pipelines CI para validar a saúde do projeto automaticamente.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:
1. Java Development Kit (JDK): Certifique‑se de que o JDK está instalado no seu sistema. Você pode baixar e instalar o JDK a partir de [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Biblioteca Aspose.Tasks para Java: Você precisa ter a biblioteca Aspose.Tasks para Java. Você pode baixá‑la no [site](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Primeiro, vamos importar os pacotes necessários para trabalhar com Aspose.Tasks:
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 2: Obter Tarefa e Atribuição de Recurso
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Como Alterar o Contorno – Flat (Padrão)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Como Alterar o Contorno – DoublePeak
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
- **Valores inesperados?** Verifique se as datas de início e término da tarefa estão definidas corretamente no MPP de origem.
- **Dica de desempenho:** Reutilize a mesma instância `Project` ao iterar por múltiplos contornos para evitar I/O de arquivos desnecessário.

## Perguntas Frequentes
### Posso usar o Aspose.Tasks com outras bibliotecas Java?
Sim, o Aspose.Tasks pode ser integrado com outras bibliotecas Java para aprimorar as capacidades de gerenciamento de projetos.

### O Aspose.Tasks é adequado para projetos empresariais de grande escala?
Absolutamente, o Aspose.Tasks foi projetado para lidar com projetos de todos os tamanhos, incluindo iniciativas empresariais de grande escala.

### O Aspose.Tasks oferece suporte a diferentes formatos de arquivo de projeto?
Sim, o Aspose.Tasks suporta uma variedade de formatos, como MPP, XML e MPX.

### Posso personalizar os contornos de trabalho de acordo com os requisitos do meu projeto?
Sim, você pode definir contornos de trabalho personalizados para atender a necessidades específicas de agendamento.

### Existe um fórum da comunidade onde eu possa obter assistência com o Aspose.Tasks?
Sim, você pode visitar o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte e discussões.

---

**Última Atualização:** 2026-01-10  
**Testado com:** Aspose.Tasks for Java (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}