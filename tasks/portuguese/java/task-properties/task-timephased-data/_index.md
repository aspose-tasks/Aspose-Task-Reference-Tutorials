---
date: 2026-02-28
description: Aprenda a usar o Aspose.Tasks para Java para gerenciar dados de tarefas
  por período, baixe a biblioteca, experimente gratuitamente e otimize o acompanhamento
  de projetos.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como usar Aspose.Tasks para gerenciar dados de tarefas por fase de tempo (Java)
url: /pt/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Usar Aspose.Tasks para Dados de Tarefas por Fase de Tempo

## Introdução
Se você está procurando **como usar Aspose** para manter um controle rigoroso do cronograma do seu projeto, chegou ao lugar certo. O rastreamento preciso de dados de tarefas por fase de tempo é um alicerce da gestão de projetos bem‑sucedida, e o Aspose.Tasks for Java fornece as ferramentas necessárias para automatizar esse processo. Neste tutorial, percorreremos um exemplo completo, de ponta a ponta, que mostra como usar o Aspose.Tasks para criar um projeto, atribuir recursos, definir linhas de base e, finalmente, recuperar e exibir os dados de fase de tempo.

## Respostas Rápidas
- **O que significa “dados de fase de tempo”?** São dados divididos por intervalos de tempo (dias, semanas, meses) que mostram trabalho, custo ou trabalho restante ao longo da linha do tempo do projeto.  
- **Qual biblioteca fornece essa capacidade?** Aspose.Tasks for Java.  
- **Preciso de licença para executar o exemplo?** Uma avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **Posso exportar os resultados para Excel?** Sim – você pode iterar a coleção `TimephasedData` e gravar os valores no formato que precisar.

## O que são Dados de Tarefas por Fase de Tempo?
Os dados de fase de tempo de uma tarefa representam a quantidade de trabalho (ou custo) programada para a tarefa em cada fatia de tempo do calendário do projeto. Eles permitem visualizar como o trabalho está distribuído, identificar sobrecarga e comparar o planejado com o real.

## Por que Usar Aspose.Tasks para Gerenciar Dados de Fase de Tempo?
- **Controle total** – crie, modifique e consulte informações de fase de tempo programaticamente sem abrir o Microsoft Project.  
- **Multiplataforma** – funciona em qualquer SO que suporte Java.  
- **Sem dependências COM** – ideal para automação no servidor.  
- **API rica** – oferece suporte a linhas de base, contornos de trabalho e campos personalizados prontamente.

## Pré‑requisitos
Antes de mergulhar no código, certifique‑se de que você tem:

- **Ambiente de Desenvolvimento Java** – JDK 8+ instalado e `JAVA_HOME` configurado.  
- **Biblioteca Aspose.Tasks for Java** – Baixe e inclua a biblioteca Aspose.Tasks no seu projeto. Você pode encontrar a biblioteca [aqui](https://releases.aspose.com/tasks/java/).  
- **Diretório de Documentos** – Uma pasta na sua máquina onde o arquivo de projeto de exemplo (`project.xml`) será lido e gravado.

## Importar Pacotes
No seu projeto Java, importe as classes necessárias do Aspose.Tasks:

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

## Etapa 1: Definir a Data de Início do Projeto
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explicação:* Criamos uma instância `Project`, inicializamos um `Calendar` com a data de início desejada e a atribuímos à propriedade `START_DATE` do projeto.

## Etapa 2: Definir Tarefa e Recurso
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explicação:* Uma nova tarefa chamada **Task** é adicionada sob a tarefa raiz. Também criamos um recurso chamado **Rsc** e definimos suas tarifas padrão e de hora extra.

## Etapa 3: Definir Duração da Tarefa
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explicação:* A tarefa é programada para uma duração de **6 dias**.

## Etapa 4: Atribuir Recurso à Tarefa
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explicação:* O recurso definido anteriormente é vinculado à tarefa por meio de um `ResourceAssignment`.

## Etapa 5: Configurar Atribuição de Recurso
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explicação:* Definimos as datas de parada e retomada da atribuição (usando um valor placeholder) e aplicamos um contorno de trabalho **Back‑Loaded**, que desloca mais trabalho para o final da atribuição.

## Etapa 6: Definir Linha de Base
```java
project.setBaseline(BaselineType.Baseline);
```
*Explicação:* Capturar uma linha de base permite comparar valores planejados com os reais posteriormente.

## Etapa 7: Atualizar Conclusão da Tarefa
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explicação:* A tarefa é marcada como **50 % concluída**, o que afetará os cálculos de trabalho restante.

## Etapa 8: Recuperar Dados de Fase de Tempo
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explicação:* Esta chamada obtém o **trabalho restante** da atribuição, dividido pelos intervalos de tempo do projeto.

## Etapa 9: Exibir Dados de Fase de Tempo
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explicação:* Simplesmente imprimimos o número de entradas de fase de tempo e o valor da primeira entrada. Em um cenário real, você iteraria a lista e exportaria os dados para um relatório ou interface de usuário.

## Problemas Comuns e Soluções
- **NullPointerException em `getTimephasedData`** – Certifique‑se de que as datas `START` e `FINISH` da atribuição estejam definidas antes de chamar o método.  
- **Contorno de trabalho incorreto** – Verifique se o `WorkContourType` escolhido corresponde à sua estratégia de agendamento; `BackLoaded` é apenas uma das várias opções.  
- **Linha de base não refletindo alterações** – Lembre‑se de chamar `project.setBaseline` *depois* de definir tarefas, recursos e atribuições.

## Perguntas Frequentes
### Q: Posso usar Aspose.Tasks for Java em qualquer projeto Java?
A: Sim, o Aspose.Tasks for Java é compatível com qualquer projeto baseado em Java.

### Q: Onde posso encontrar suporte adicional para Aspose.Tasks for Java?
A: Visite o [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) para suporte e discussões.

### Q: Existe uma avaliação gratuita disponível para Aspose.Tasks for Java?
A: Sim, você pode explorar uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q: Como posso obter uma licença temporária para Aspose.Tasks for Java?
A: Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q: Onde posso comprar Aspose.Tasks for Java?
A: Você pode comprar Aspose.Tasks for Java [aqui](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-02-28  
**Testado com:** Aspose.Tasks for Java 24.12 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}