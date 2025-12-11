---
date: 2025-12-09
description: Aprenda a criar objetos de projeto em Java e a suportar funções de avaliação
  nas fórmulas do Aspose.Tasks usando Java. Descubra como criar atributos estendidos
  para tarefas.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Criar objeto de projeto Java – Suporte a funções de avaliação no Aspose.Tasks
url: /pt/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Suporte a Funções de Avaliação em Fórmulas do Aspose.Tasks

## Introdução
Aspose.Tasks for Java permite que você **create project object java** instâncias e avalie funções do Microsoft Project diretamente dentro do seu código Java. Ao incorporar essas fórmulas, você pode executar cálculos sofisticados, gerar relatórios personalizados e automatizar a análise de projetos sem sair do seu ambiente de desenvolvimento. Este tutorial orienta você por todo o processo — desde a configuração do objeto de projeto até a adição de um atributo estendido que pode armazenar dados personalizados.

## Respostas Rápidas
- **O que significa “create project object java”?** Ele cria uma instância `Project` em memória que você pode manipular programaticamente.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java (download no site oficial).  
- **Preciso de licença?** Uma licença temporária ou completa é necessária para uso em produção; há uma versão de avaliação gratuita.  
- **Posso usar campos personalizados?** Sim — você pode definir e anexar atributos estendidos às tarefas.  
- **É compatível com todos os formatos de arquivo do Project?** Aspose.Tasks suporta os formatos MPP, MPT e XML.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8+ e uma IDE como IntelliJ IDEA ou Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Baixe e inclua a biblioteca a partir da [página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Adicione o namespace Aspose.Tasks à sua classe Java para que você possa trabalhar com projetos, tarefas e atributos estendidos:

```java
import com.aspose.tasks.*;
```

## Etapa 1: Create Project Object Java
Instancie um novo objeto `Project`. Ele servirá como contêiner para todas as tarefas, recursos e dados personalizados que você definirá.

```java
Project project = new Project();
```

A linha acima **creates project object java** que começa vazia e pronta para personalização.

## Etapa 2: Como Criar Atributo Estendido
Defina um atributo estendido que armazenará dados numéricos personalizados (por exemplo, um valor seno) para cada tarefa.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aqui nós **create extended attribute** do tipo `Number` chamado “Sine” e o associamos às tarefas.

## Etapa 3: Adicionar o Atributo Estendido ao Projeto
Registre a definição do atributo no projeto para que cada tarefa possa referenciá‑lo.

```java
project.getExtendedAttributes().add(attr);
```

## Etapa 4: Criar uma Nova Tarefa
Adicione uma tarefa simples chamada “Task” sob a tarefa raiz do projeto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Etapa 5: Associar o Atributo Estendido à Tarefa
Vincule o atributo estendido definido anteriormente à tarefa recém‑criada.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Agora a tarefa contém um campo personalizado “Sine” que você pode usar em fórmulas ou cálculos.

## Por Que Usar Funções de Avaliação?
Incorporar funções do MS Project em fórmulas do Aspose.Tasks permite que você:

- Execute cálculos em tempo real (por exemplo, `Sin([Start])`) sem ferramentas externas.  
- Mantenha toda a lógica do projeto dentro de uma única base de código, facilitando a manutenção.  
- Gere relatórios dinâmicos que refletem alterações de dados em tempo real.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **A fórmula retorna `NaN`** | Verifique se o tipo do campo personalizado corresponde ao tipo numérico esperado. |
| **Atributo estendido não visível** | Garanta que a definição do atributo seja adicionada ao projeto **antes** de criar as tarefas. |
| **Exceção de licença** | Instale uma licença temporária ou completa; o modo de avaliação pode limitar certos recursos. |

## Perguntas Frequentes

**P: O Aspose.Tasks for Java pode lidar com fórmulas complexas do MS Project?**  
R: Sim, o Aspose.Tasks for Java suporta a avaliação de uma ampla variedade de funções do MS Project, permitindo cálculos complexos dentro de aplicações Java.

**P: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos do Microsoft Project?**  
R: Sim, o Aspose.Tasks for Java suporta várias versões de arquivos do Microsoft Project, incluindo os formatos MPP, MPT e XML.

**P: Posso experimentar o Aspose.Tasks for Java antes de comprar?**  
R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no site [aqui](https://purchase.aspose.com/buy).

**P: Como obter suporte para o Aspose.Tasks for Java?**  
R: Você pode obter suporte no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**P: Existe uma licença temporária disponível para o Aspose.Tasks for Java?**  
R: Sim, você pode obter uma licença temporária para fins de teste no site da Aspose [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2025-12-09  
**Testado com:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}