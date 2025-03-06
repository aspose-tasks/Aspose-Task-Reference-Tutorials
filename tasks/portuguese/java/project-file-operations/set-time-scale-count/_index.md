---
title: Dominando a contagem da escala de tempo do MS Project em Aspose.Tasks
linktitle: Definir contagem de escala de tempo em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerenciar com eficácia a contagem da escala de tempo no MS Project usando Aspose.Tasks for Java. Otimize a visualização e o gerenciamento de projetos sem esforço.
weight: 22
url: /pt/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando a contagem da escala de tempo do MS Project em Aspose.Tasks

## Introdução
O gerenciamento da contagem da escala de tempo no MS Project pode afetar significativamente a visualização e o gerenciamento do projeto. Com Aspose.Tasks for Java, uma API poderosa para lidar com tarefas de gerenciamento de projetos de forma programática, você pode manipular com eficiência a contagem da escala de tempo para adaptar as visualizações do projeto às suas necessidades específicas.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte em vigor:
1. Ambiente de Desenvolvimento Java: Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Tasks para Java: Baixe e instale a biblioteca Aspose.Tasks para Java. Você pode obtê-lo de[aqui](https://releases.aspose.com/tasks/java/).
3. Conhecimento básico de programação Java: A familiaridade com a linguagem de programação Java será benéfica.

## Importar pacotes
Importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Etapa 1: definir diretório de dados
Defina o caminho para o diretório de dados onde os arquivos do seu projeto serão armazenados:
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho para o seu diretório de dados.
## Passo 2: Criar Instância do Projeto
 Instanciar um novo`Project` objeto:
```java
Project project = new Project();
```
Isso cria um novo objeto de projeto.
## Etapa 3: configurar a visualização do gráfico de Gantt
 Criar uma`GanttChartView` objeto para configurar a visualização do gráfico de Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Etapa 4: definir a contagem da escala de tempo para a camada inferior
Defina a contagem e a visibilidade dos ticks para o nível inferior da escala de tempo:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Isso especifica a contagem de intervalos e se os ticks devem ser exibidos para a camada inferior.
## Etapa 5: definir a contagem da escala de tempo para a camada intermediária
Da mesma forma, configure a camada de escala de tempo intermediária:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Etapa 6: adicionar visualização ao projeto
Adicione a visualização configurada ao projeto:
```java
project.getViews().add(view);
```
Isso adiciona a visualização personalizada ao projeto.
## Etapa 7: adicionar dados de teste ao projeto
Adicione alguns dados de teste ao projeto para demonstração:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Isso cria duas tarefas com durações especificadas.
## Passo 8: Salvar Projeto como PDF
Salve o projeto como um arquivo PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Isso salva o projeto com as configurações aplicadas em um arquivo PDF.

## Conclusão
O gerenciamento eficaz da contagem da escala de tempo no MS Project usando Aspose.Tasks for Java permite que você personalize as visualizações do projeto para melhor visualização e gerenciamento.
## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com arquivos de projeto em grande escala?
R: Sim, Aspose.Tasks for Java é capaz de lidar com arquivos de projetos em grande escala com eficiência.
### P: O Aspose.Tasks for Java é compatível com diferentes IDEs Java?
R: Sim, Aspose.Tasks for Java funciona perfeitamente com Java Integrated Development Environments (IDEs), como Eclipse e IntelliJ IDEA.
### P: Posso personalizar a aparência dos gráficos de Gantt usando Aspose.Tasks for Java?
R: Com certeza, Aspose.Tasks for Java oferece amplos recursos para personalizar a aparência dos gráficos de Gantt de acordo com seus requisitos.
### P: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode obter uma versão de teste gratuita em[aqui](https://releases.aspose.com/).
### P: Onde posso obter suporte para Aspose.Tasks for Java?
 R: Você pode encontrar suporte e assistência no fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
