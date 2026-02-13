---
date: 2026-02-13
description: Aprenda a gerar relatório de projeto criando um objeto de projeto em
  Java, adicionando atributos estendidos e usando funções de avaliação com Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Gerar Relatório do Projeto – Criar Objeto de Projeto Java
url: /pt/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Suporte a Funções de Avaliação no Aspose.Tasks Formulas

## Introdução
Aspose.Tasks for Java permite que você **gere relatório de projeto** criando um **objeto de projeto** em Java e avaliando funções do Microsoft Project diretamente no seu código. Ao incorporar essas fórmulas, você pode executar cálculos sofisticados, gerar relatórios personalizados e automatizar a análise de projetos sem sair do seu ambiente de desenvolvimento. Neste tutorial, percorreremos a criação de um objeto de projeto, a adição de um atributo estendido e o uso de funções de avaliação para **adicionar dados de campo personalizado de tarefa**.

## Respostas Rápidas
- **O que significa “create project object java”?** Ele cria uma instância `Project` na memória que você pode manipular programaticamente.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java (download do site oficial).  
- **Preciso de uma licença?** Uma licença temporária ou completa do Aspose.Tasks é necessária para uso em produção; uma avaliação gratuita está disponível.  
- **Posso usar campos personalizados?** Sim – você pode **adicionar atributo estendido** às tarefas e tratá-los como campos personalizados.  
- **Isso é compatível com todos os formatos de arquivo do Project?** Aspose.Tasks suporta os formatos MPP, MPT e XML.

## Pré-requisitos
Antes de começar, certifique-se de que você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8+ e uma IDE como IntelliJ IDEA ou Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Baixe e inclua a biblioteca da [página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Adicione o namespace Aspose.Tasks à sua classe Java para que você possa trabalhar com projetos, tarefas e atributos estendidos:

```java
import com.aspose.tasks.*;
```

## Gerar Relatório de Projeto – Criar Objeto de Projeto Java
Instancie um novo objeto `Project`. Ele servirá como contêiner para todas as tarefas, recursos e dados personalizados que você definir.

```java
Project project = new Project();
```

A linha acima **cria project object java** que começa vazia e pronta para personalização.

## Como Adicionar Atributo Estendido
Defina um atributo estendido que armazenará dados numéricos personalizados (por exemplo, um valor seno) para cada tarefa.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aqui nós **adicionamos atributo estendido** do tipo `Number` chamado “Sine” e o associamos às tarefas.

## Adicionar o Atributo Estendido ao Projeto
Registre a definição do atributo no projeto para que cada tarefa possa referenciá-lo.

```java
project.getExtendedAttributes().add(attr);
```

## Criar uma Nova Tarefa
Adicione uma tarefa simples chamada “Task” sob a tarefa raiz do projeto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Associar o Atributo Estendido à Tarefa
Vincule o atributo estendido definido anteriormente à tarefa recém-criada.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Agora a tarefa contém um campo personalizado “Sine” que você pode usar em fórmulas ou cálculos. Isso também é como você **adiciona dados de campo personalizado de tarefa** programaticamente.

## Por que Usar Funções de Avaliação?
Incorporar funções do MS Project nas fórmulas do Aspose.Tasks permite que você:

- Execute cálculos em tempo real (por exemplo, `Sin([Start])`) sem ferramentas externas.  
- Mantenha toda a lógica do projeto dentro de uma única base de código, fácil de manter.  
- Gere relatórios dinâmicos que refletem alterações de dados em tempo real, ajudando você a **gerar relatório de projeto** automaticamente.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **A fórmula retorna `NaN`** | Verifique se o tipo do campo personalizado corresponde ao tipo numérico esperado. |
| **Atributo estendido não visível** | Certifique-se de que a definição do atributo seja adicionada ao projeto **antes** de criar tarefas. |
| **Exceção de licença** | Instale uma licença temporária ou completa do **Aspose.Tasks**; o modo de avaliação pode limitar certos recursos. |
| **Licença temporária ausente** | Obtenha uma **licença temporária Aspose** no site da Aspose. |

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java pode lidar com fórmulas complexas do MS Project?**  
**A:** Sim, o Aspose.Tasks for Java suporta a avaliação de uma ampla variedade de funções do MS Project, permitindo cálculos complexos dentro de aplicações Java.

**Q: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos do Microsoft Project?**  
**A:** Sim, o Aspose.Tasks for Java suporta várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.

**Q: Posso experimentar o Aspose.Tasks for Java antes de comprar?**  
**A:** Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no site [aqui](https://purchase.aspose.com/buy).

**Q: Como posso obter suporte para o Aspose.Tasks for Java?**  
**A:** Você pode obter suporte no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Existe uma licença temporária disponível para o Aspose.Tasks for Java?**  
**A:** Sim, você pode obter uma licença temporária para fins de teste no site da Aspose [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Seguindo estas etapas, você aprendeu como **criar objeto de projeto**, **adicionar atributo estendido** e aproveitar as funções de avaliação para **gerar relatório de projeto** automaticamente. Agora você pode expandir essa base para construir análises de projeto mais avançadas, painéis personalizados ou ferramentas de agendamento automatizado — tudo alimentado pelo Aspose.Tasks for Java.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}