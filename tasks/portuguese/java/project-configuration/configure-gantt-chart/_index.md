---
date: 2026-02-13
description: Aprenda como criar uma nova atividade, definir o diretório de dados e
  salvar o projeto como MPP no Aspose.Tasks Java. Este guia passo a passo também aborda
  a personalização dos campos da tabela.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como criar nova atividade e definir diretório de dados Aspose.Tasks
url: /pt/java/project-configuration/configure-gantt-chart/
weight: 10
---

 craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Nova Atividade e Definir Diretório de Dados Aspose.Tasks

## Introdução
Neste tutorial, você aprenderá **como definir o diretório de dados**, como **criar nova atividade** e como **salvar o projeto como MPP** enquanto configura a Visualização de Gráfico de Gantt do MS Project em projetos Aspose.Tasks usando Java. Aspose.Tasks é uma API Java robusta que permite manipular arquivos Microsoft Project programaticamente. Ao final deste guia, você será capaz de **personalizar campos de tabela**, ajustar o diretório de dados e visualizar seu projeto exatamente da maneira que precisar.

## Respostas Rápidas
- **Qual é o primeiro passo?** Defina o caminho do diretório de dados onde seus arquivos de projeto estão armazenados.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (disponível para download no site oficial).  
- **Posso adicionar atributos personalizados?** Sim – você pode definir atributos estendidos e exibí‑los no gráfico de Gantt.  
- **Preciso de uma licença para teste?** Uma licença temporária está disponível para fins de avaliação.  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans) funcionará.

## O que é “definir diretório de dados” e por que isso importa?
Definir o diretório de dados informa ao Aspose.Tasks onde ler e gravar arquivos de projeto. Sem um caminho correto, a API não consegue localizar seus arquivos `.mpp`, resultando em erros FileNotFound. Definir esse diretório no início do seu código torna o restante do fluxo de trabalho limpo e repetível.

## Por que personalizar campos de tabela em um gráfico de Gantt?
Campos de tabela personalizados permitem expor informações adicionais — como atributos personalizados, dados de recursos ou notas específicas do projeto — diretamente na visualização de Gantt. Isso torna o gráfico mais informativo para as partes interessadas e reduz a necessidade de alternar entre vários relatórios.

## Como criar nova atividade?
Criar uma nova atividade (tarefa) é uma das operações principais ao construir ou atualizar um cronograma de projeto. Ao adicionar tarefas programaticamente, você pode automatizar a geração de planos de projeto complexos, integrar dados de outros sistemas ou aplicar alterações em massa sem edição manual.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – qualquer versão recente (8+).  
2. **Aspose.Tasks Library** – faça o download a partir de [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java que você preferir.

## Importar Pacotes
Primeiro, importe o namespace Aspose.Tasks para que você possa trabalhar com suas classes:

```java
import com.aspose.tasks.*;
```

## Guia Passo a Passo

### Passo 1: Configurar Diretório de Dados
Defina a pasta que contém seus arquivos de projeto. Este é o passo de **definir diretório de dados** em que o tutorial se concentra.

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto da pasta onde `project.mpp` está armazenado.

### Passo 2: Carregar Arquivo de Projeto
Crie uma instância `Project` carregando um arquivo Microsoft Project existente.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: Adicionar Nova Atividade
Insira uma nova tarefa (atividade) na raiz do projeto. Isso demonstra **como criar nova atividade** programaticamente.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Passo 4: Definir Atributo Personalizado
Crie uma definição de atributo personalizado que você poderá anexar às tarefas posteriormente.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Passo 5: Adicionar Atributo Personalizado à Tarefa
Atribua o atributo recém‑definido à tarefa que você criou.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Passo 6: Personalizar Tabela – **customize table fields**
Adicione o atributo personalizado como uma coluna na tabela do gráfico de Gantt, especificando largura, título e alinhamento.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Passo 7: Salvar Projeto
Persista as alterações em um novo arquivo que pode ser aberto no Microsoft Project. Este passo **salva o projeto como MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **FileNotFoundException** ao carregar o projeto | O caminho **definir diretório de dados** está incorreto ou falta a barra final. | Verifique se `dataDir` aponta exatamente para a pasta e inclua o separador de arquivos adequado (`/` ou `\\`). |
| Atributo personalizado não visível na visualização de Gantt | O campo da tabela foi adicionado no índice errado ou a largura da coluna está muito pequena. | Garanta que `table.getTableFields().add(3, attrField);` use um índice válido e ajuste `setWidth` conforme necessário. |
| LicenseException ao salvar | Nenhuma licença válida foi aplicada para uso em produção. | Aplique uma licença temporária ou permanente antes de chamar `project.save()`. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, Aspose.Tasks está disponível para várias linguagens, incluindo .NET, Java e C++.

**Q: Existe uma versão de avaliação gratuita disponível para Aspose.Tasks?**  
A: Sim, você pode baixar uma avaliação gratuita a partir de [here](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte para Aspose.Tasks?**  
A: Você pode encontrar suporte e fazer perguntas no [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Como posso comprar uma licença para Aspose.Tasks?**  
A: Você pode comprar uma licença a partir de [here](https://purchase.aspose.com/buy).

**Q: Preciso de uma licença temporária para fins de teste?**  
A: Sim, você pode obter uma licença temporária a partir de [here](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você aprendeu como **definir o diretório de dados**, **criar nova atividade**, definir e anexar um atributo personalizado, e **salvar o projeto como MPP** enquanto **personaliza campos de tabela** em uma visualização de gráfico de Gantt usando Aspose.Tasks para Java. Essas etapas dão controle total sobre como os dados do projeto são exibidos, tornando seus gráficos de Gantt mais informativos e adequados às necessidades das partes interessadas.

---

**Última Atualização:** 2026-02-13  
**Testado com:** Aspose.Tasks Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}