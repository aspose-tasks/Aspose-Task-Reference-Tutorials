---
title: Cálculos de porcentagem concluída para tarefas em Aspose.Tasks
linktitle: Cálculos de porcentagem concluída para tarefas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explore Aspose.Tasks para Java e simplifique o acompanhamento do progresso do projeto. Calcule facilmente porcentagens de tarefas para um gerenciamento de projetos eficiente.
weight: 25
url: /pt/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cálculos de porcentagem concluída para tarefas em Aspose.Tasks

## Introdução
Bem-vindo ao nosso guia detalhado sobre como dominar cálculos de porcentagem de tarefas usando Aspose.Tasks for Java. Aspose.Tasks é uma poderosa biblioteca Java projetada para trabalhar com arquivos do Microsoft Project, oferecendo um conjunto robusto de recursos para gerenciamento de projetos. Neste tutorial, focaremos nos cálculos de porcentagem concluída, fornecendo a você o conhecimento para monitorar e analisar com eficácia o progresso do projeto.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:
- Ambiente de Desenvolvimento Java: Certifique-se de ter o Java instalado em seu sistema.
-  Biblioteca Aspose.Tasks: Baixe a biblioteca Aspose.Tasks para Java em[esse link](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Vamos começar importando os pacotes necessários para o seu projeto Aspose.Tasks for Java. Inclua o seguinte snippet de código em seu projeto:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Agora, vamos detalhar cada etapa com explicações detalhadas.
## Etapa 1: Importando Pacotes
Na primeira etapa, importamos os pacotes necessários para configurar nosso projeto Aspose.Tasks.
## Etapa 2: Configurando o diretório de documentos
 Defina o caminho para o diretório do seu documento usando o`dataDir`variável. Certifique-se de que seu arquivo do Microsoft Project, como “Software Development.mpp”, esteja neste diretório.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
```
## Etapa 3: Carregando o Projeto
 Inicialize um novo`Project` objeto e carregue seu arquivo do Microsoft Project na instância do projeto.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Etapa 4: recuperando a coleção de tarefas
 Obtenha a tarefa raiz do projeto e recupere seus filhos como uma coleção usando`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Etapa 5: Porcentagem de impressão concluída
Percorra cada tarefa da coleção e imprima a porcentagem concluída, a porcentagem de trabalho concluído e a porcentagem física concluída.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Repita essas etapas para cada tarefa do seu projeto para obter insights sobre o progresso de cada uma.
## Conclusão
Parabéns! Você dominou com sucesso os cálculos de porcentagem de tarefas usando Aspose.Tasks for Java. Esta poderosa biblioteca permite que os desenvolvedores gerenciem e analisem o progresso do projeto com eficiência.
## Perguntas frequentes
### P: Onde posso encontrar a documentação do Aspose.Tasks?
 A documentação está disponível[aqui](https://reference.aspose.com/tasks/java/).
### P: Como posso baixar a biblioteca Aspose.Tasks para Java?
 Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/java/).
### P: Existe uma avaliação gratuita disponível?
Sim, você pode acessar um teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso obter suporte para Aspose.Tasks?
 Visite o fórum de suporte[aqui](https://forum.aspose.com/c/tasks/15).
### P: Como obtenho uma licença temporária?
 Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
