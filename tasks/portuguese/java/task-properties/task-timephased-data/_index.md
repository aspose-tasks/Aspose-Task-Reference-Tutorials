---
title: Dados faseados no tempo da tarefa em Aspose.Tasks
linktitle: Dados faseados no tempo da tarefa em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explore Aspose.Tasks para Java e domine o gerenciamento de dados em fases de tarefas. Baixe a biblioteca, aproveite uma avaliação gratuita e agilize o acompanhamento do seu projeto.
weight: 34
url: /pt/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dados faseados no tempo da tarefa em Aspose.Tasks

## Introdução
No domínio do gerenciamento de projetos, o rastreamento preciso dos dados faseados das tarefas é crucial para a execução eficiente do projeto. Aspose.Tasks for Java surge como uma ferramenta poderosa para agilizar esse processo, oferecendo recursos robustos e flexibilidade. Este tutorial irá guiá-lo na utilização do Aspose.Tasks for Java para gerenciar dados de tarefas em fases de maneira eficaz.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Ambiente de Desenvolvimento Java: Certifique-se de ter o Java instalado em seu sistema.
-  Biblioteca Aspose.Tasks para Java: Baixe e inclua a biblioteca Aspose.Tasks em seu projeto. Você pode encontrar a biblioteca[aqui](https://releases.aspose.com/tasks/java/).
- Diretório de documentos: configure um diretório para os documentos do seu projeto.
## Importar pacotes
No seu projeto Java, importe os pacotes necessários para Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Etapa 1: definir a data de início do projeto
```java
Project project = new Project(dataDir + "project.xml");
// Código adicional para importações de pacotes
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Explicação: Inicialize um objeto calendário, defina a data de início e aplique-a ao projeto.
## Etapa 2: Definir Tarefa e Recurso
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Explicação: Crie uma tarefa e um recurso, definindo taxas para horas extras e padrão.
## Etapa 3: definir a duração da tarefa
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Explicação: Defina a duração da tarefa (por exemplo, 6 dias).
## Etapa 4: Atribuir recurso à tarefa
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Explicação: Designe o recurso à tarefa.
## Passo 5: Configurar Atribuição de Recursos
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Explicação: Configure parâmetros como parada, continuação e contorno de trabalho para a designação de recurso.
## Etapa 6: definir linha de base
```java
project.setBaseline(BaselineType.Baseline);
```
Explicação: Estabeleça uma linha de base para o projeto.
## Etapa 7: atualizar a conclusão da tarefa
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Explicação: Indique a porcentagem de conclusão da tarefa.
## Etapa 8: recuperar dados em fases
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Explicação: Recupere dados divididos em fases para o trabalho restante da atribuição.
## Etapa 9: exibir dados em fases
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Código adicional para exibir outros valores
```
Explicação: Produza e exiba os dados divididos em fases.
## Conclusão
gerenciamento eficaz dos dados faseados das tarefas é indispensável para o sucesso do projeto. Aspose.Tasks for Java simplifica esse processo, fornecendo um conjunto abrangente de funcionalidades. Seguindo este tutorial, você pode integrar perfeitamente o Aspose.Tasks ao seu projeto Java, garantindo controle preciso sobre os cronogramas do projeto e a alocação de recursos.
## perguntas frequentes
### P: Posso usar Aspose.Tasks for Java em qualquer projeto Java?
R: Sim, Aspose.Tasks for Java é compatível com qualquer projeto baseado em Java.
### P: Onde posso encontrar suporte adicional para Aspose.Tasks for Java?
 R: Visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for Java?
 R: Sim, você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).
### P: Como posso obter uma licença temporária para Aspose.Tasks for Java?
 R: Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso comprar o Aspose.Tasks para Java?
 R: Você pode comprar Aspose.Tasks para Java[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
