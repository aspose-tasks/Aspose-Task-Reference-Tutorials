---
date: 2025-12-07
description: Aprenda a **criar projeto de teste** e **adicionar campo personalizado**
  ao manipular arquivos do Microsoft Project usando o Aspose.Tasks para Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Criar Projeto de Teste e Usar Fórmulas com Aspose.Tasks para Java
url: /pt/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Projeto de Teste e Usar Fórmulas com Aspose.Tasks para Java

## Introdução
Neste tutorial você **criará arquivos de projeto de teste**, adicionará um campo personalizado e trabalhará com fórmulas do MS Project usando a biblioteca Aspose.Tasks para Java. Aspose.Tasks facilita a **manipulação de dados do Microsoft Project** programaticamente — seja para gerar cronogramas, calcular datas ou automatizar relatórios. Ao final do guia você terá um exemplo executável que define um atributo estendido, define um prazo para uma tarefa e salva o projeto como um arquivo MPP.

## Respostas Rápidas
- **O que o tutorial cobre?** Criação de um projeto de teste, adição de um campo personalizado, definição de um atributo estendido e definição de prazo de tarefa com uma fórmula.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (versão mais recente).  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção.  
- **Qual IDE posso usar?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, VS Code) que suporte JDK 8+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para copiar o código e executá‑lo.

## O que é um “Projeto de Teste” no Aspose.Tasks?
Um **projeto de teste** é um arquivo Microsoft Project leve criado programaticamente para demonstrar ou validar funcionalidades. Ele contém um conjunto mínimo de tarefas, recursos e campos personalizados que você pode manipular sem afetar dados de projetos reais.

## Por que usar Aspose.Tasks para Manipular Microsoft Project?
- **Cobertura total da API** – acesso a todas as propriedades de Project, Task e Resource.  
- **Nenhuma instalação do Office necessária** – funciona em servidores, pipelines CI e contêineres Docker.  
- **Multiplataforma** – roda no Windows, Linux e macOS com o mesmo código Java.  
- **Motor de fórmulas robusto** – calcula datas, durações e campos personalizados diretamente dentro do arquivo de projeto.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- **Java Development Kit (JDK) 8+** – faça o download no site da Oracle ou adote o OpenJDK.  
- **Aspose.Tasks para Java** – obtenha o JAR mais recente na [página de download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/) e adicione‑o ao classpath do seu projeto ou às dependências Maven/Gradle.

## Importar Pacotes
Primeiro, importe as classes que usaremos:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guia Passo a Passo

### Etapa 1: Criar um Projeto de Teste com um Campo Personalizado
Começamos **criando o projeto de teste** e adicionando um campo personalizado que mais tarde armazenará o resultado da nossa fórmula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Dica profissional:* `CreateTestProjectWithCustomField()` é um método auxiliar que constrói um cronograma mínimo e registra um atributo estendido pronto para a atribuição da fórmula.

### Etapa 2: Definir um Atributo Estendido (Adicionar Campo Personalizado)
Em seguida, **definimos o atributo estendido** – essencialmente o campo personalizado – e atribuímos um alias amigável. É aqui que adicionamos a lógica do **campo personalizado**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** torna o campo legível no Project.  
- **Fórmula** calcula o número de dias entre a data *Finish* de uma tarefa e sua *Deadline*.

### Etapa 3: Definir Prazo para uma Tarefa (Adicionar Tarefa de Prazo & Definir Prazo da Tarefa)
Agora **adicionamos dados da tarefa de prazo** definindo a propriedade *Deadline* em uma tarefa específica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A instância `Calendar` define o momento exato do prazo.  
- `set(Tsk.DEADLINE, …)` **define o prazo da tarefa** para a tarefa escolhida.

### Etapa 4: Salvar o Projeto (Manipular Arquivo Microsoft Project)
Por fim, **manipulamos o Microsoft Project** persistindo as alterações em um arquivo MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Você pode abrir `SaveFile.mpp` no Microsoft Project para ver o campo personalizado, o resultado da fórmula e o prazo refletidos no cronograma.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **Fórmula não está sendo avaliada** | Verifique se a string `Formula` do atributo usa nomes de campo corretos (ex.: `[Deadline]`, `[Finish]`). |
| **Tarefa não encontrada** | Confirme se o ID da tarefa (`1` no exemplo) existe; use `project.getRootTask().getChildren().size()` para depurar. |
| **Exceção de licença** | Aplique uma licença válida do Aspose.Tasks antes de chamar quaisquer métodos da API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Perguntas Frequentes

**P: Posso usar Aspose.Tasks com outras linguagens de programação?**  
R: Sim, o Aspose.Tasks fornece APIs para .NET, Java e outras plataformas, permitindo que você **manipule arquivos Microsoft Project** na linguagem de sua escolha.

**P: Existe uma avaliação gratuita disponível para Aspose.Tasks?**  
R: Absolutamente. Baixe uma avaliação totalmente funcional na [página de download do Aspose.Tasks](https://releases.aspose.com/).

**P: Onde encontro documentação detalhada do Aspose.Tasks?**  
R: A documentação oficial está hospedada em [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**P: Como obter suporte para Aspose.Tasks?**  
R: Visite o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para fazer perguntas e compartilhar experiências com a comunidade.

**P: Preciso de uma licença temporária para avaliação?**  
R: Uma licença temporária está disponível para testes de curto prazo; você pode solicitá‑la [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2025-12-07  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}