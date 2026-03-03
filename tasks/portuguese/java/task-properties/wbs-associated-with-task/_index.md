---
date: 2026-03-03
description: Aprenda a renumerar WBS no Aspose.Tasks para Java, gerencie a estrutura
  de divisão do trabalho e personalize códigos WBS de forma eficiente com exemplos
  passo a passo.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como renumerar WBS no Aspose.Tasks para Java
url: /pt/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Renumerar WBS no Aspose.Tasks para Java

## Introdução
Se você precisa **como renumerar WBS** em um arquivo Microsoft Project usando Aspose.Tasks para Java, está no lugar certo. Este tutorial orienta você a ler os códigos WBS existentes, personalizá‑los e, em seguida, renumerar a hierarquia para que seu projeto permaneça organizado. Seja limpando um cronograma legado ou construindo um novo do zero, dominar estas etapas ajudará você a **gerenciar estruturas de decomposição de trabalho** com confiança.

## Respostas Rápidas
- **O que a renumeração de WBS faz?** Ela recalcula a numeração hierárquica das tarefas para refletir quaisquer alterações estruturais.  
- **Qual classe realiza a renumeração?** `Project.renumberWBSCode`.  
- **Preciso de uma licença para executar o código?** Uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso personalizar o formato do WBS?** Sim—use `Task.set(Tsk.WBS, "...")` para atribuir qualquer string que desejar.  
- **Quais são os pré‑requisitos principais?** Java JDK, biblioteca Aspose.Tasks para Java e um arquivo de projeto válido (.mpp).

## O que é uma Estrutura de Decomposição do Trabalho (WBS)?
Uma Estrutura de Decomposição do Trabalho (WBS) é uma representação hierárquica dos entregáveis e tarefas de um projeto. Cada tarefa recebe um código (por exemplo, 1.2.3) que reflete sua posição na hierarquia. Renumerar torna‑se essencial quando tarefas são adicionadas, removidas ou reordenadas, garantindo que os códigos permaneçam lógicos e fáceis de ler.

## Por que gerenciar a decomposição do trabalho e personalizar códigos WBS?
- **Clareza:** Códigos WBS claros facilitam a localização de tarefas pelos interessados.  
- **Relatórios:** Muitas ferramentas de relatório dependem de numeração consistente.  
- **Flexibilidade:** Códigos personalizados permitem alinhar a estrutura do projeto com padrões internos.  

## Pré‑requisitos
Antes de mergulharmos no código, confirme que você tem o seguinte:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.Tasks para Java adicionada ao seu projeto. Você pode obtê‑la [aqui](https://releases.aspose.com/tasks/java/).  

## Importar Pacotes
Certifique‑se de importar os pacotes necessários para iniciar seu projeto:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Ler Códigos WBS
Primeiro, leremos os códigos WBS existentes para que você possa ver com o que está trabalhando.

### Passo 1: Carregar o Projeto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Passo 2: Coletar Tarefas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Passo 3: Analisar e Personalizar
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

O trecho acima imprime o WBS atual e o nível de cada tarefa, e então demonstra **personalizar códigos wbs** atribuindo uma nova string.

## Renumerar Códigos WBS das Tarefas
Agora vamos realmente renumerar a hierarquia WBS.

### Passo 1: Carregar o Projeto (Exemplo de Renumeração)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Passo 2: Selecionar Todas as Tarefas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Passo 3: Exibir Códigos WBS Iniciais
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Passo 4: Renumerar Códigos WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Passo 5: Exibir Códigos WBS Atualizados
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Seguindo estas etapas, você efetivamente **como renumerar wbs** para qualquer conjunto de tarefas no seu arquivo de projeto.

## Problemas Comuns e Soluções
- **WBS não muda após a chamada `set`:** Certifique‑se de que está trabalhando com a instância correta da tarefa e que o projeto seja salvo após as modificações.  
- **`renumberWBSCode` lança uma exceção:** Verifique se a lista de IDs corresponde ao número de tarefas de nível superior; caso contrário, o método não pode mapear os novos números corretamente.  
- **Valores WBS ausentes:** Algumas tarefas podem ter um WBS `null` se foram importadas de um arquivo que não definiu um. Use um valor padrão antes de imprimir.  

## Perguntas Frequentes

**Q: Onde posso encontrar a documentação do Aspose.Tasks para Java?**  
A: A documentação está disponível [aqui](https://reference.aspose.com/tasks/java/).

**Q: Como posso baixar o Aspose.Tasks para Java?**  
A: Você pode baixá‑lo [aqui](https://releases.aspose.com/tasks/java/).

**Q: Existe uma versão de avaliação gratuita disponível para Aspose.Tasks para Java?**  
A: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso obter suporte para Aspose.Tasks para Java?**  
A: Visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte.

**Q: Posso obter uma licença temporária para Aspose.Tasks para Java?**  
A: Sim, obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Posso renomear o formato do WBS após a renumeração?**  
A: Absolutamente. Após chamar `renumberWBSCode`, você pode iterar sobre as tarefas e aplicar `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` para adequar às suas convenções de nomenclatura.

**Q: A renumeração afeta as dependências das tarefas?**  
A: Não. O método apenas atualiza a string WBS; os vínculos e restrições das tarefas permanecem inalterados.

---

**Última Atualização:** 2026-03-03  
**Testado com:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}