---
date: 2026-01-28
description: Aprenda a ler atributos de tarefa estendidos usando Aspose.Tasks para
  Java e altere o tipo de campo personalizado de forma eficiente.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Ler atributos de tarefa estendidos com Aspose.Tasks para Java
url: /pt/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Atributos de Tarefa Estendidos com Aspose.Tasks para Java

## Introdução
Neste tutorial abrangente, você descobrirá como **read extended task attributes** de arquivos Microsoft Project usando a biblioteca Aspose.Tasks para Java. Seja construindo uma ferramenta de relatórios, sincronizando dados ou simplesmente precisando de uma visão mais profunda dos campos personalizados, dominar esse recurso permitirá extrair todas as informações armazenadas em um projeto. Percorreremos a configuração necessária, mostraremos como mudar o tipo de campo personalizado ao processar atributos e daremos dicas práticas para evitar armadilhas comuns.

## Respostas Rápidas
- **O que significa “read extended task attributes”?** Refere‑se à extração de valores de campos personalizados que vão além das propriedades padrão de tarefa em um arquivo Project.  
- **Qual classe fornece acesso a esses atributos?** A classe `ExtendedAttribute` no Aspose.Tasks.  
- **Preciso de uma licença para executar o código?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso mudar o tipo do atributo em tempo de execução?** Sim – use a instrução `switch` para **switch custom field type** com base em `CustomFieldType`.  
- **Esta é compatível com Java 8 e posteriores?** Absolutamente, a API suporta JDK 8+.

## O que são read extended task attributes?
Atributos de tarefa estendidos são campos definidos pelo usuário (texto, data, número, bandeira, etc.) que complementam as propriedades padrão de tarefa no Microsoft Project. O Aspose.Tasks os expõe através da coleção `ExtendedAttribute` anexada a cada objeto `Task`, permitindo que você leia ou modifique seus valores programaticamente.

## Por que ler atributos de tarefa estendidos?
- **Visibilidade total:** Obtenha insight sobre os dados personalizados que as partes interessadas adicionaram ao cronograma.  
- **Automação:** Preencha painéis, gere relatórios personalizados ou migre dados para outros sistemas sem exportação manual.  
- **Flexibilidade:** Trabalhe com qualquer tipo de campo personalizado — texto, data, duração, custo, bandeira — tratando cada caso adequadamente.

## Pré‑requisitos
- Conhecimento básico de programação Java.  
- Java Development Kit (JDK) instalado na sua máquina.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  

## Importar Pacotes
Comece importando as classes necessárias para o projeto Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Etapa 1: Acessando Tarefa e Atributos Estendidos
Carregue um arquivo Project e itere por cada tarefa para acessar seus atributos estendidos:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Etapa 2: Recuperando ID do Campo e GUID do Valor
Imprima os identificadores internos que ajudam a entender com qual campo personalizado você está lidando:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Etapa 3: Como mudar o tipo de campo personalizado ao ler atributos de tarefa estendidos
Use uma instrução `switch` em `CustomFieldType` para tratar cada tipo de dado possível corretamente:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Repita estas etapas para cada tarefa em seu projeto para explorar e manipular cada atributo de tarefa estendido.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **Null values returned** | Verifique se o campo personalizado está realmente preenchido no arquivo .mpp de origem. |
| **Incorrect type displayed** | Certifique‑se de que está usando o `CustomFieldType` correto na instrução `switch`; tipos incompatíveis causarão valores padrão. |
| **Performance slowdown on large projects** | Processe tarefas em lotes ou filtre apenas as tarefas necessárias usando `project.getRootTask().getChildren().stream()` com os predicados adequados. |

## Perguntas Frequentes
### Posso modificar atributos de tarefa estendidos programaticamente?
Sim, você pode modificar atributos de tarefa estendidos usando Aspose.Tasks para Java. Consulte a documentação para instruções detalhadas.

### Existe uma versão de avaliação disponível?
Sim, você pode acessar a versão de avaliação gratuita [aqui](https://releases.aspose.com/).

### Onde posso encontrar suporte para Aspose.Tasks para Java?
Para suporte, visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Como posso obter uma licença temporária?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso comprar a versão completa do Aspose.Tasks para Java?
Você pode comprar a versão completa [aqui](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-01-28  
**Testado com:** Aspose.Tasks Java API (última versão estável)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}