---
date: 2025-12-07
description: Aprenda como salvar o arquivo de projeto, escrever e ler fórmulas do
  MS Project e adicionar fórmulas de campos personalizados usando o Aspose.Tasks para
  Java.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salvar arquivo de projeto e escrever fórmulas do MS Project com Aspose.Tasks
url: /pt/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar Arquivo de Projeto e Escrever Fórmulas do MS Project com Aspose.Tasks

## Introdução
No âmbito da gestão de projetos, o manuseio eficaz dos dados é fundamental. Aspose.Tasks for Java é uma solução robusta que facilita a manipulação e extração de dados de arquivos Microsoft Project. Um recurso poderoso que ele oferece é a capacidade de escrever e ler fórmulas do MS Project. **Você também aprenderá como *salvar arquivo de projeto* após aplicar essas fórmulas**, garantindo que suas alterações sejam preservadas para análises futuras. Este tutorial o guiará pelo processo de aproveitamento dessa funcionalidade para melhorar suas tarefas de gestão de projetos.

## Respostas Rápidas
- **O que faz “salvar arquivo de projeto”?** Ele grava todas as alterações em memória de volta para um arquivo .mpp no disco.  
- **Posso adicionar fórmulas de campo personalizado?** Sim – você pode criar um campo personalizado e atribuir uma fórmula como “dobrar custo da tarefa”.  
- **Preciso de licença para executar o código?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilará o exemplo.  
- **A API é compatível com a versão mais recente do MS Project?** Aspose.Tasks suporta todos os formatos .mpp recentes.

## O que é “salvar arquivo de projeto” no Aspose.Tasks?
Salvar um arquivo de projeto significa persistir o estado atual do objeto `Project` — incluindo tarefas, recursos e quaisquer fórmulas personalizadas — em um arquivo físico do Microsoft Project (`.mpp`). Essa operação é essencial após modificar dados, como adicionar um campo personalizado ou alterar custos de tarefas.

## Por que adicionar um campo personalizado e criar uma fórmula de campo personalizado?
Adicionar um campo personalizado oferece um contêiner flexível para informações extras que não são cobertas pelos campos padrão. Ao associar uma fórmula — como uma que **dobra o custo da tarefa** — você automatiza cálculos, reduz erros manuais e mantém os dados do cronograma consistentes.

## Pré-requisitos
Antes de mergulhar neste tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:

1. **Java Development Kit (JDK)** – Java 8 ou superior instalado em sua máquina.  
2. **Aspose.Tasks for Java** – Baixe e instale de [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Escolha sua IDE preferida para desenvolvimento Java (IntelliJ IDEA, Eclipse, VS Code, etc.).  

## Importando Pacotes
Para começar, importe os pacotes necessários ao seu projeto Java:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Etapa 1: Configurar Diretório de Dados
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Defina a pasta onde seus arquivos MS Project estão armazenados. É aqui que você carregará o arquivo fonte e, posteriormente, **salvará o arquivo de projeto**.

## Etapa 2: Carregar Arquivo de Projeto
```java
Project project = new Project(dataDir + "project.mpp");
```
Carregue o arquivo Microsoft Project existente em um objeto `Project` para que você possa ler ou modificar seu conteúdo.

## Etapa 3: Adicionar Campo Personalizado e Criar Fórmula de Campo Personalizado
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
Nesta etapa, **adicionamos o campo personalizado** “Double Costs” e **criamos a fórmula de campo personalizado** que multiplica o `[Cost]` da tarefa por 2, efetivamente **dobrando o custo da tarefa**. O método `setFormula` incorpora o cálculo diretamente no arquivo do projeto.

## Etapa 4: Adicionar Tarefa e Definir Custo
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Crie uma nova tarefa e, em seguida, atribua um custo base de `100`. Quando o projeto for salvo, o campo personalizado exibirá automaticamente `200` devido à fórmula definida anteriormente.

## Etapa 5: Salvar Arquivo de Projeto
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Finalmente, **salve o arquivo de projeto** com todas as modificações. O método `save` grava o projeto atualizado, incluindo o novo campo personalizado e seus valores calculados, em `saved.mpp`.

## Problemas Comuns e Soluções
| Problema | Razão | Solução |
|----------|-------|---------|
| **Fórmula não aplicada** | Campo personalizado não adicionado à coleção `ExtendedAttributes` do projeto. | Certifique‑se de que `project.getExtendedAttributes().add(attr);` seja executado antes de salvar. |
| **Arquivo não encontrado** | Caminho `dataDir` incorreto. | Verifique se a string do diretório termina com um separador de caminho (`/` ou `\\`). |
| **Custo aparece como 0** | Custo da tarefa não definido antes de salvar. | Chame `task.set(Tsk.COST, ...)` antes de `project.save`. |

## Perguntas Frequentes
**Q: O Aspose.Tasks é compatível com todas as versões do MS Project?**  
A: Sim, o Aspose.Tasks suporta uma ampla gama de versões do MS Project, desde formatos .mpp mais antigos até as versões mais recentes.

**Q: Posso integrar o Aspose.Tasks ao meu projeto Java existente?**  
A: Absolutamente. A API foi projetada para integração perfeita; basta adicionar o JAR do Aspose.Tasks ao classpath do seu projeto.

**Q: Existem limitações quanto aos tipos de fórmulas que posso criar?**  
A: A biblioteca suporta a maioria da sintaxe nativa de fórmulas do MS Project, incluindo aritmética, lógica e funções integradas. Funções personalizadas complexas podem exigir soluções alternativas.

**Q: O Aspose.Tasks suporta implantação multiplataforma?**  
A: Sim, a biblioteca funciona em qualquer plataforma que suporte Java, incluindo Windows, Linux e macOS.

**Q: Como posso obter suporte técnico para o Aspose.Tasks?**  
A: Visite o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para ajuda da comunidade ou abra um ticket de suporte se você possuir uma licença comercial.

## Conclusão
Neste tutorial abordamos como **salvar o arquivo de projeto**, **adicionar campo personalizado** e **criar uma fórmula de campo personalizado** que **dobra o custo da tarefa** usando Aspose.Tasks for Java. Seguindo estas etapas, você pode automatizar cálculos, enriquecer os dados do seu projeto e garantir que todas as alterações sejam persistidas para relatórios e análises futuras.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}