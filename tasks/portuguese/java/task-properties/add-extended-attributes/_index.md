---
date: 2026-01-25
description: Aprenda a adicionar atributos às tarefas usando Aspose.Tasks para Java,
  personalizando arquivos do Microsoft Project com atributos estendidos para melhorar
  o controle do projeto.
linktitle: Add Extended Attributes to Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como adicionar atributo – Adicionar atributos estendidos às tarefas no Aspose.Tasks
url: /pt/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Atributo – Adicionar Atributos Estendidos a Tarefas no Aspose.Tasks

## Introdução
Melhorar suas capacidades de gerenciamento de projetos é crucial para o acompanhamento eficiente de tarefas e gerenciamento de recursos. Neste tutorial, **você aprenderá Java, proporcionando a flexibilidade de adaptar arquivos do Microsoft Project às necessidades específicas da sua organização. Percorrer **Pos arquivo são suportados para gravação?** MPP, XML e outros formatos suportados pelo Aspose.Tasks.

## Pré-requisitos-se de que você possui os seguintes pré-requisitos:
- Conhecimento básico de programação Java.  
- Aspose.Tasks for Java library installed. You can download it from the [site](https://releases.aspose.com/tasks/java/).  
- Um Ambiente de Desenvolvimento Integrado (IDE) Java instalado em seu sistema.

## Importar Pacotes
No seu projeto Java, importe os pacotes necessários para acessar as funcionalidades do Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

Agora, vamos dividir cada exemplo em várias etapas:

## Como Adicionar Atributo a uma Tarefa (Exemplo de Texto Simples)

### 1. Definindo o Diretório do Documento
Primeiro, defina a pasta que contém seu arquivo de projeto fonte:
```java
String dataDir = "Your Document Directory";
```

### 2. Carregando o Projeto
Crie uma instância `Project` que aponta para um arquivo `.mpp` existente:
```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. Definindo um Atributo Estendido de Texto Simples
Crie uma definição de atributo do tipo **Text1** – isso armazenará o nome da cidade para cada tarefa:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 4. Adicionando a Definição ao Projeto
Registre a nova definição na coleção de atributos estendidos do projeto:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 5. Criando uma Nova Tarefa
Adicione uma tarefa filha sob a tarefa raiz:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 6. Instanciando o Atributo Estendido
Gere uma instância real do atributo a partir da definição que você criou anteriormente:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 7. Atribuindo um Valor
Defina o valor concreto (por exemplo, a cidade “London”) para o atributo estendido desta tarefa:
```java
taskExtendedAttributeText1.setTextValue("London");
```

### 8. Anexando o Atributo à Tarefa
Adicione o atributo preenchido à coleção da tarefa:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

### 9. Salvando o Projeto Atualizado
Finalmente, persista as alterações em um novo arquivo para que você possa verificar o resultado no Microsoft Project:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Adicionando Atributo de Texto com Opção de Pesquisa
Para criar um atributo de texto que ofereça uma lista predefinida de valores (pesquisa), repita as etapas acima, mas substitua `ExtendedAttributeTask.Text1` por `ExtendedAttributeTask.Text2` e preencha a tabela de pesquisa usando `taskExtendedAttributeText2Definition.getLookupValues().add(...)`. Isso permite que os usuários escolham entre um conjunto fixo de opções ao editar a tarefa.

## Adicionando Atributo de Duração com Opção de Pesquisa
De forma semelhante, para um atributo baseado em duração, use `CustomFieldType.Duration` e `ExtendedAttributeTask.Duration2`. Preencha os valores de pesquisa com intervalos de tempo específicos (por exemplo, “1 day”, “2 weeks”) para padronizar as entradas de duração em todo o seu projeto.

## Por Que Usar Atributos Estendidos?
- **Flexibilidade:** Armazene quaisquer dados personalizados que não sejam cobertos pelos campos padrão do Project.  
- **Padronização:** Tabelas de pesquisa impõem entradas de dados consistentes.  
- **Relatórios:** Campos personalizados podem ser incluídos em relatórios e filtros, proporcionando insights mais profundos.

## Problemas Comuns & Solução de Problemas
- **Caminho Inválido:** Certifique‑se de que `dataDir` termina com um separador de arquivos (`/` ou `\\`) apropriado para o seu SO.  
- **Exceções de Licença:** Sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar marcas d'água.  
- **Pesquisa Não Aparece:** Após definir valores de pesquisa, sempre adicione a definição ao projeto antes de criar atributos de tarefa.

## Perguntas Frequentes
### Q: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?
A: Sim, Aspose.Tasks for Java pode ser integrado perfeitamente aos seus projetos Java, e funciona bem com outras bibliotecas Java.

### Q: O Aspose.Tasks for Java é adequado para aplicações de gerenciamento de projetos em grande escala?
A: Absolutamente, Aspose.Tasks for Java foi projetado para lidar com projetos de diferentes‑se de revisar as informações de licenciamento fornecidas no [site da Aspose.Tasks](https://purchase.aspose.com/buy).

### Q: Como posso obter suporte ou assistência com Aspose.Tasks for Java?
A: Visite o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte da comunidade e discussões.

### Q: Posso experimentar o Aspose.Tasks for Java antes de comprar?
A: Sim, você pode acessar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Perguntas e Respostas Adicionais**

**Q: Posso adicionar múltiplos atributos estendidos a uma única tarefa?**  
A: Sim, basta criar instâncias adicionais de `ExtendedAttribute` e adicionar cada uma à coleção `ExtendedAttributes` da tarefa.

**Q: Os valores de pesquisa suportam localização?**  
A: Os valores de pesquisa são armazenados como strings simples, portanto você pode fornecer texto localizado para cada entrada conforme necessário.

## Conclusão
Seguindo este guia passo a passo, **você aprendeu como adicionar atributo** a tarefas em arquivos Microsoft Project usando Aspose.Tasks for Java. Essa poderosa personalização permite capturar dados específicos do projeto, melhorar os relatórios e manter a consistência nos cronogramas da sua organização.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}