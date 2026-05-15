---
date: 2026-01-13
description: Aprenda como criar um atributo personalizado, carregar um arquivo do
  Microsoft Project, definir um valor numérico em Java e salvar o projeto como XML
  com o Aspose.Tasks para Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como criar atributo personalizado no MS Project usando Aspose.Tasks
url: /pt/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um atributo personalizado no MS Project usando Aspose.Tasks

## Introdução
Neste tutorial, **você descobrirá como criar um atributo personalizado** para recursos em um arquivo Microsoft Project usando Aspose.Tasks para Java. Vamos percorrer o carregamento de um arquivo Microsoft Project, a definição de um novo atributo numérico, a atribuição de um valor e, finalmente, a gravação do projeto como XML. Ao final, você terá um exemplo claro e prático que pode adaptar às suas próprias soluções de gerenciamento de projetos.

## Respostas rápidas
- **O que significa “atributo personalizado”?**  
  Um campo definido pelo usuário que armazena informações extras (por exemplo, Idade, Nível de Habilidade) para um recurso ou tarefa.  
- **Qual biblioteca lida com isso?**  
  Aspose.Tasks para Java fornece uma API fluente para criar e gerenciar atributos personalizados.  
- **Preciso de uma licença?**  
  Uma licença temporária gratuita funciona para avaliação; uma licença completa é necessária para produção.  
- **Posso definir valores numéricos?**  
  Sim – use `setNumericValue` com um `BigDecimal` (por exemplo, `30.5345`).  
- **Como o projeto é salvo?**  
  O arquivo modificado pode ser salvo como XML usando `SaveFileFormat.Xml`.

## O que é um atributo personalizado?
Um **atributo personalizado** (também chamado de atributo estendido) é uma coluna adicional que você pode adicionar a recursos ou tarefas no Microsoft Project. Ele permite capturar dados que não são cobertos pelos campos incorporados, como idade do funcionário, nível de certificação ou qualquer métrica específica do negócio.

## Por que criar um atributo personalizado no MS Project?
- **Adaptar os dados do projeto** às necessidades da sua organização.  
- **Habilitar relatórios avançados** armazenando valores que podem ser consultados posteriormente.  
- **Manter consistência** entre múltiplos projetos aplicando programaticamente a mesma definição de atributo.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Ambiente de desenvolvimento Java** – JDK 8 ou superior instalado.  
2. **Aspose.Tasks para Java** – Baixe a versão mais recente [aqui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA ou qualquer IDE compatível com Java.  

## Guia passo a passo

### Importar pacotes
Primeiro, importe as classes do Aspose.Tasks que você precisará. Elas fornecem a funcionalidade central para manipular projetos, recursos e atributos estendidos.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Etapa 1: Definir diretório de dados
Defina a pasta onde seu arquivo de projeto de origem está localizado e onde a saída será gravada.

```java
String dataDir = "Your Data Directory";
```

### Etapa 2: Carregar arquivo Microsoft Project
Crie uma instância `Project` carregando o arquivo existente. Esta é a etapa **load Microsoft project file** que lhe dá acesso total ao seu conteúdo.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Etapa 3: Definir o atributo personalizado
Vamos definir um novo atributo numérico chamado **Age**. A API verifica se a definição já existe; caso não exista, ela cria uma nova.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Etapa 4: Definir valor numérico em Java
Crie uma instância do atributo para um recurso específico e atribua um valor numérico usando `setNumericValue`. Isso demonstra **set numeric value java** em ação.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Etapa 5: Adicionar recurso e anexar o atributo personalizado
Adicione um novo recurso chamado **R1** e anexe o atributo personalizado criado anteriormente a ele.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Etapa 6: Salvar projeto como XML
Finalmente, persista as alterações salvando o projeto. Esta é a etapa **save project as xml**, que produz uma representação XML limpa do arquivo atualizado.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Etapa 7: Exibir resultado
Imprima uma confirmação amigável para que você saiba que o processo foi concluído sem erros.

```java
System.out.println("Process completed Successfully");
```

Seguindo estas etapas, você criou com sucesso um **atributo personalizado**, carregou um arquivo Microsoft Project, definiu um valor numérico usando Java e salvou o projeto como XML.

## Problemas comuns e dicas
- **Conflitos de ID de atributo:** Sempre verifique `getById` antes de criar uma nova definição para evitar IDs duplicados.  
- **Manipulação de precisão:** `BigDecimal` preserva a precisão decimal; evite usar `float` ou `double` para valores exatos.  
- **Caminhos de arquivo:** Use caminhos absolutos ou configure o diretório de trabalho da sua IDE para evitar `FileNotFoundException`.  

## Perguntas frequentes

**Q: Posso criar atributos personalizados para tarefas assim como para recursos?**  
A: Sim – use `ExtendedAttributeTask` em vez de `ExtendedAttributeResource` ao definir o atributo.

**Q: É possível adicionar vários atributos personalizados de uma vez?**  
A: Absolutamente. Crie objetos `ExtendedAttributeDefinition` separados para cada atributo e anexe‑os aos recursos ou tarefas desejados.

**Q: Em quais formatos posso salvar o projeto?**  
A: Aspose.Tasks suporta XML, MPP e vários outros formatos como PDF e HTML. Neste exemplo usamos `SaveFileFormat.Xml`.

**Q: Preciso licenciar o Aspose.Tasks para builds de desenvolvimento?**  
A: Uma licença temporária é suficiente para avaliação. Para implantações em produção, uma licença completa é necessária.

**Q: Como ler os valores dos atributos personalizados posteriormente?**  
A: Use `resource.getExtendedAttributes()` para iterar sobre os atributos anexados e recuperar seus valores com `getNumericValue()` ou `getTextValue()`.

## Conclusão
Criar um **atributo personalizado** no Microsoft Project com Aspose.Tasks para Java é simples depois que você entende o fluxo de trabalho: carregar o projeto, definir o atributo, definir seu valor, anexá‑lo a um recurso e salvar o arquivo. Essa abordagem permite estender programaticamente os modelos de dados do projeto, possibilitando relatórios mais ricos e integração mais estreita com seus processos de negócios.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}