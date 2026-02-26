---
date: 2026-02-26
description: Aprenda como retomar e parar tarefas no Aspose.Tasks para Java, incluindo
  a filtragem de tarefas por data para um controle preciso do projeto.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como retomar e parar tarefa no Aspose.Tasks
url: /pt/java/task-properties/stop-resume-task/
weight: 30
---

 and end.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Retomar Tarefa e Parar Tarefa no Aspose.Tasks

## Introdução
Se você está construindo uma solução de gerenciamento de projetos baseada em Java, frequentemente precisará **pausar** uma tarefa temporariamente e depois **continuá‑la**. O Aspose.Tasks para Java facilita isso com propriedades incorporadas para parar e retomar tarefas. Neste tutorial você descobrirá **como retomar tarefa** e **como parar tarefa** programaticamente, e também verá como **filtrar tarefas por data** para trabalhar apenas com os itens relevantes em sua agenda.

## Respostas Rápidas
- **O que significa “parar” uma tarefa?** Define uma data de parada, interrompendo o trabalho após esse ponto.  
- **Como posso retomar uma tarefa parada?** Atribuindo uma data de retomada posterior à data de parada.  
- **Posso limitar a operação a um intervalo de datas?** Sim – use uma data mínima para filtrar tarefas.  
- **Qual versão da biblioteca é necessária?** Qualquer versão recente do Aspose.Tasks para Java (a API permanece estável).  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção.

## O que é “como retomar tarefa” no Aspose.Tasks?
Retomar uma tarefa simplesmente significa fornecer uma data **RESUME** em um objeto `Task`. Quando o mecanismo do projeto processa o cronograma, o trabalho continuará a partir dessa data. Isso é especialmente útil para lidar com interrupções, como indisponibilidade de recursos ou dependências externas.

## Por que usar o recurso de parar/retomar?
- **Controle sobre cronogramas:** Pause o trabalho sem excluir a tarefa.  
- **Relatórios precisos:** Exiba datas de início/fim realistas em diagramas de Gantt.  
- **Automação fácil:** Combine com filtros de data para atualizar muitas tarefas de uma vez.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Um bom domínio dos fundamentos de Java.  
- JDK instalado em sua máquina.  
- A biblioteca Aspose.Tasks para Java adicionada ao seu projeto (faça o download [aqui](https://releases.aspose.com/tasks/java/)).  

## Importar Pacotes
Primeiro, traga as classes necessárias para o escopo para que você possa trabalhar com projetos e tarefas.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Etapa 1: Inicializar o Projeto e o Coletor
Crie uma instância `Project` apontando para seu arquivo MPP e configure um `ChildTasksCollector` para reunir todas as tarefas na hierarquia.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Etapa 2: Definir uma Data Mínima para Filtragem
Se você deseja trabalhar apenas com tarefas que possuam datas de parada ou retomada significativas, defina uma **data mínima**. Esta é a base da técnica de *filtrar tarefas por data*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Etapa 3: Iterar, Verificar e Exibir Valores de Parada/Retomada
Agora percorra as tarefas coletadas, aplique a lógica de **como parar tarefa** e imprima as datas. O código também demonstra **como retomar tarefa** lendo a propriedade `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Dica profissional:** Substitua as chamadas `System.out.println` pela sua própria lógica (por exemplo, atualizando as datas, registrando em um arquivo ou modificando os objetos de tarefa) para realmente *parar* ou *retomar* tarefas conforme necessário.

## Problemas Comuns e Soluções
| Problema | Causa | Correção |
|----------|-------|----------|
| `NullPointerException` em `tsk.get(Tsk.STOP)` | A tarefa não tem data de parada definida. | Verifique se o valor é `null` antes de chamar `.before(minDate)`. |
| Datas aparecem como `NA` mesmo após a definição | Data mínima é muito recente. | Use uma `minDate` mais antiga ou remova o filtro. |
| Alterações não refletidas no MPP salvo | Projeto não foi salvo após as modificações. | Chame `project.save("output.mpp");` após atualizar as tarefas. |

## Perguntas Frequentes

### O Aspose.Tasks para Java é adequado para projetos de grande escala?
Absolutamente! O Aspose.Tasks para Java foi projetado para lidar com projetos de diferentes tamanhos, garantindo eficiência e confiabilidade.

### Posso personalizar a data de parada e retomada das tarefas?
Sim, o exemplo fornecido permite flexibilidade ao definir a data mínima de acordo com os requisitos do seu projeto.

### Onde posso encontrar suporte adicional para o Aspose.Tasks para Java?
Visite o [Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte da comunidade e discussões.

### Existe um teste gratuito disponível para o Aspose.Tasks para Java?
Sim, você pode acessar o [teste gratuito](https://releases.aspose.com/) para explorar os recursos antes de efetuar a compra.

### Como posso obter uma licença temporária para o Aspose.Tasks para Java?
Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.

**Perguntas Adicionais**

**P: Como realmente definir uma nova data de parada para uma tarefa?**  
R: Use `tsk.set(Tsk.STOP, new Date(...));` e depois salve o projeto.

**P: Posso filtrar tarefas por um intervalo específico em vez de apenas uma data mínima?**  
R: Sim—compare tanto `before` quanto `after` com suas datas de início e fim.

**P: A API recalcula automaticamente o cronograma após alterar as datas de parada/retomada?**  
R: Após modificar as datas, chame `project.calculateCriticalPath();` para atualizar o cronograma.

## Conclusão
Neste guia abordamos **como retomar tarefa** e **como parar tarefa** usando o Aspose.Tasks para Java, juntamente com um método prático para **filtrar tarefas por data**. Ao integrar esses trechos ao seu aplicativo, você obtém controle granular sobre os cronogramas do projeto e pode automatizar ajustes de agenda com confiança.

---

**Última atualização:** 2026-02-26  
**Testado com:** Aspose.Tasks para Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}